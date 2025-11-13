The idea is to trigger multiple workflows in ./.github, each workflow implementing part ot th TDD below:
1. List scenarios for the new feature
    List the expected variants in the new behavior. "There's the basic case & then what-if this service times out & what-if the key isn't in the database yet &…" The developer can discover these specifications by asking about use cases and user stories. A key benefit of TDD is that it makes the developer focus on requirements before writing code. This is in contrast with the usual practice, where unit tests are only written after code.
1. Would for instance trigger when an issue is created.

2. Write a test for an item on the list
    Write an automated test that would pass if the variant in the new behavior is met.

3. Run all tests. The new test should fail – for expected reasons
    This shows that new code is actually needed for the desired feature. It validates that the test harness is working correctly. It rules out the possibility that the new test is flawed and will always pass.
4. Write the simplest code that passes the new test
    Inelegant code and hard coding is acceptable. The code will be honed in Step 6. No code should be added beyond the tested functionality.
5. All tests should now pass
    If any fail, fix failing tests with minimal changes until all pass.
6. Refactor as needed while ensuring all tests continue to pass
    Code is refactored for readability and maintainability. In particular, hard-coded test data should be removed from the production code. Running the test suite after each refactor ensures that no existing functionality is broken. Examples of refactoring:

        moving code to where it most logically belongs
        removing duplicate code
        making names self-documenting
        splitting methods into smaller pieces
        re-arranging inheritance hierarchies

Repeat
    Repeat the process, starting at step 2, with each test on the list until all tests are implemented and passing.



Dénomination 	Traduction française 	Version originale 	Note d'interprétation
Loi no 1 	Vous ne pouvez pas écrire de code de production tant que vous n'avez pas écrit un test unitaire qui échoue. 	"You may not write production code until you have written a failing unit test." 	C'est-à-dire qu'il n'est permis d'écrire du code de production que si un test unitaire est en échec.
Loi no 2 	Vous ne pouvez pas écrire plus de code de test qu'il n'en faut pour qu'un test unitaire échoue, et ne pas compiler revient à échouer. 	"You may not write more of a unit test than is sufficient to fail, and not compiling is failing." 	C'est-à-dire qu'il n'est permis d'écrire qu'un nouveau test unitaire en échec à la fois, et un test unitaire qui ne compile pas est déjà un test en échec.
Loi no 3 	Vous ne pouvez pas écrire plus de code de production que nécessaire pour que le test unitaire actuellement en échec réussisse. 	"You may not write more production code than is sufficient to pass the currently failing test." 	C'est-à-dire qu'il n'est permis d'écrire que du code de production permettant directement de faire passer le test unitaire précédent, ni plus ni moins. 