# Automated TDD Repository with Claude Agents

This repository implements a fully automated Test-Driven Development (TDD) system using Claude AI agents and GitHub Actions. The system handles the complete development lifecycle from issue creation to pull request, following strict TDD principles.

## 🚀 Overview

The automation system transforms GitHub issues into fully implemented, tested, and refactored code through a series of AI-powered agents that collaborate via issue comments and GitHub Actions workflows.

### Key Features

- **Full TDD Cycle**: Implements Red-Green-Refactor methodology automatically
- **Multi-Agent System**: Specialized Claude agents for each development phase
- **GitHub Integration**: Seamless workflow through issues, comments, and PRs
- **Language Agnostic**: Works with JavaScript, Python, Java, Go, and more
- **Quality Assurance**: Automated testing, refactoring, and code quality checks
- **Documentation**: Comprehensive documentation at every step

## 📋 How It Works

### The TDD Process

1. **RED Phase**: Write failing tests that define requirements
2. **GREEN Phase**: Write minimal code to make tests pass
3. **REFACTOR Phase**: Improve code quality while maintaining test success

### Agent Workflow

```mermaid
graph LR
    A[User Creates Issue] --> B[@claude_issue_initializer]
    B --> C[Request Clarifications]
    C --> D[User Provides Details]
    D --> E[@claude_scenarii]
    E --> F[Generate Test Scenarios]
    F --> G[@claude_test_implementor]
    G --> H[Write Failing Tests]
    H --> I[@claude_implementor]
    I --> J[Write Production Code]
    J --> K[@claude_refactoror]
    K --> L[Improve Code Quality]
    L --> M[@claude_pr_creator]
    M --> N[Create Pull Request]
```

## 🤖 Claude Agents

### 1. Issue Initializer (`@claude_issue_initializer`)
- **Purpose**: Analyzes new issues and requests clarifications
- **Trigger**: Tagged in issue description
- **Output**: Clarifying questions for complete requirements

### 2. Scenario Generator (`@claude_scenarii`)
- **Purpose**: Creates comprehensive test scenarios
- **Trigger**: Tagged after user provides details
- **Output**: Complete specifications and test scenarios

### 3. Test Implementor (`@claude_test_implementor`)
- **Purpose**: Writes failing tests (RED phase)
- **Trigger**: Tagged after scenarios are generated
- **Output**: Executable test code that fails initially

### 4. Code Implementor (`@claude_implementor`)
- **Purpose**: Writes minimal production code (GREEN phase)
- **Trigger**: Tagged after tests are written
- **Output**: Code that makes all tests pass

### 5. Refactorer (`@claude_refactoror`)
- **Purpose**: Improves code quality (REFACTOR phase)
- **Trigger**: Tagged after implementation
- **Output**: Refactored code with tests still passing

### 6. PR Creator (`@claude_pr_creator`)
- **Purpose**: Creates pull request with all changes
- **Trigger**: Tagged after refactoring complete
- **Output**: Pull request linking to original issue

## 🚦 Getting Started

### Prerequisites

1. **GitHub Repository** with Actions enabled
2. **Anthropic API Key** for Claude AI
3. **Test Framework** installed (Jest, pytest, etc.)

### Setup Instructions

1. **Add GitHub Secrets**:
   ```
   ANTHROPIC_API_KEY: Your Claude API key
   GH_PAT: GitHub Personal Access Token (optional)
   ```

2. **Configure Settings**:
   Edit `.claude/settings.json` to customize:
   - Test coverage thresholds
   - Refactoring cycles
   - Model preferences
   - Quality metrics

3. **Create an Issue**:
   ```markdown
   Title: Add user authentication feature

   @claude_issue_initializer

   I need a user authentication system with login and logout functionality.
   ```

4. **Follow the Flow**:
   - Answer clarification questions
   - Tag `@claude_scenarii` when ready
   - Watch automation proceed through all phases
   - Review and merge the generated PR

## 📁 Repository Structure

```
.github/
├── workflows/
│   ├── issue-initializer.yml
│   ├── scenario-generator.yml
│   ├── test-implementor.yml
│   ├── code-implementor.yml
│   ├── refactorer.yml
│   └── pr-creator.yml
.claude/
├── agents/
│   ├── issue-initializer.md
│   ├── scenarii.md
│   ├── test-implementor.md
│   ├── implementor.md
│   └── refactoror.md
└── settings.json
.automation/
├── open/           # Active issue documentation
├── closed/         # Completed issue archives
└── templates/      # Document templates
```

## 📊 Documentation Generated

For each issue, the system creates:

1. **1_INITIAL_ISSUE_CONTENTS.md** - Original issue text
2. **2_REQUEST_FOR_DETAILS.md** - Clarification questions
3. **3_USER_DETAILS.md** - User responses
4. **4_COMPLETE_INSTRUCTIONS.md** - Detailed specifications
5. **5_SCENARIOS.md** - Test scenarios
6. **6_SCENARIOS_TESTS_IMPLEMENTATION_PLAN.md** - Test plan
7. **7_IMPLEMENTATION_PLAN.md** - Implementation approach
8. **8_REFACTORING_PLAN.md** - Refactoring strategy

## ⚙️ Configuration

### Test Settings
```json
{
  "tdd": {
    "coverage_threshold": 80,
    "max_refactoring_cycles": 3,
    "test_timeout": 300
  }
}
```

### Agent Models
```json
{
  "agents": {
    "model_preferences": {
      "issue_initializer": "claude-3-sonnet",
      "scenarii": "claude-3-opus-latest",
      "test_implementor": "claude-3-opus-latest"
    }
  }
}
```

## 🧪 Supported Test Frameworks

- **JavaScript/TypeScript**: Jest, Mocha, Jasmine
- **Python**: pytest, unittest, nose
- **Java**: JUnit, TestNG
- **Go**: testing package
- **Ruby**: RSpec, Minitest

## 📈 Metrics and Quality

The system tracks:
- Test coverage percentage
- Cyclomatic complexity
- Code duplication
- Method/function length
- Response times
- Build success rates

## 🔒 Security

- No access to secrets or credentials
- Sandboxed execution environment
- Input sanitization
- Branch protection rules
- Code review requirements

## 🛠️ Troubleshooting

### Common Issues

1. **Tests Not Failing Initially**
   - Ensure functionality doesn't exist yet
   - Check test expectations are correct

2. **Agent Not Responding**
   - Verify API key is set correctly
   - Check workflow permissions
   - Review action logs

3. **Refactoring Loop**
   - Maximum 3 cycles enforced
   - Manual intervention if needed

### Manual Controls

- Trigger workflows manually via GitHub UI
- Skip agents by tagging next in chain
- Cancel workflows if needed
- Override automation with manual PR

## 🤝 Contributing

To improve the automation system:

1. Test changes in a separate branch
2. Update agent prompts in `.claude/agents/`
3. Modify workflows in `.github/workflows/`
4. Update documentation
5. Create PR with changes

## 📝 Best Practices

1. **Clear Issue Descriptions**: Provide detailed requirements
2. **Answer Thoroughly**: Respond completely to clarifications
3. **Review Generated Code**: Check PR before merging
4. **Monitor Metrics**: Track quality improvements
5. **Iterate**: Refine agent prompts based on results

## 🎯 Use Cases

Perfect for:
- New feature development
- Bug fixes with test coverage
- Refactoring existing code
- API endpoint creation
- Database schema changes
- UI component development

## 📚 Additional Resources

- [TDD Principles](https://en.wikipedia.org/wiki/Test-driven_development)
- [Claude AI Documentation](https://docs.anthropic.com)
- [GitHub Actions Guide](https://docs.github.com/actions)
- [Clean Code Practices](https://github.com/ryanmcdermott/clean-code-javascript)

## 📄 License

This automation system is available for use in your projects. Customize agent prompts and workflows to match your team's needs.

## 🙏 Acknowledgments

Built with:
- Claude AI by Anthropic
- GitHub Actions
- Test-Driven Development methodology

---

**Note**: This is an experimental automation system. Always review generated code before merging to production.