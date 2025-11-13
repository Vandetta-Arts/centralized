-> I would like to create a ultra-automated git repository based on claude code agents (in .claude/agents) and github actions
-> I would like to base this automation on test-driven development framework

technically, 3 important folders for this automation
- .claude/agents to store prompts defining agents
- .github for workflow definitions
- ./.automation/open/{issue-name}/ for issue-specific data, like
    - 1_INITIAL_ISSUE_CONTENTS.md
    - 2_REQUEST_FOR_DETAILS.md
    - 3_USER_DETAILS.md
    - 4_COMPLETE_INSTRUCTIONS.md
    - 5_SCENARIOS.md
    - 6_SCENARIOS_TESTS_IMPLEMENTATION_PLAN.md
    - 7_IMPLEMENTATION_PLAN.md
    - 8_REFACTORING_PLAN.md

globally, the workflow would look something like that:

a. User creates an issue tagging @claude_issue_initializer
b. This creates a branch, claude reads the issue contents, analyses the repo, creates `./.automation/open/{issue-name}/` and asks the user to specify his request (basically asking him details needed for implementation). This ask for details is posted as a comment under the issue using gh. This agent also creates the `1_INITIAL_ISSUE_CONTENTS.md` file, ans well as the `2_REQUEST_FOR_DETAILS.md`
c. The user answers, providing `3_USER_DETAILS` and tags @claude_scenarii.
d. This triggers the @claude_scenarii which
    - analyses messages and human answers
    - analyses the codebase
    - writes the `4_COMPLETE_INSTRUCTIONS.md`, which basically contains a ultra detailed and specified version of the initial issue, with NO grey area both in terms of behaviour or implementation. posts it under the issue
    - writes the `5_SCENARIOS.md`, posts it under the issue, tagging @claude_test_implementor, basically a big list
e. @claude_test_implementor `6_SCENARIOS_TESTS_IMPLEMENTATION_PLAN.md`. In ultrathink plan mode best model. Then implements it. All new tests should fail. When this is done, tag @claude_implementor
f. @claude_implementor plans in ultrathink mode best model and creates `7_IMPLEMENTATION_PLAN.md`, then implementes it and pushes the changes. All tests should pass. Then, tags @claude_refactoror. Code edits don't have to be very clean. Focus should be on making tests pass. Forbidden to touch the tests
g. @claude_refactoror plans in ultrathink mode best model and creates `8_REFACTORING_PLAN.md`, then implements it. After implementing this reformating, it either decides code is clean enough, or decides to go for a new loop of refactoring, by re-tagging @claude_refactoror in the issues

I would like you to help me set this up by coding the necessary agents and github action workflows.