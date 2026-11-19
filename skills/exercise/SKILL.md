---
name: exercise
description: An exercise on a topic where AI writes failing tests and she writes the solution.
argument-hint: "<topic, e.g. records, Server Actions, pytest fixtures>"
disable-model-invocation: true
---

# Exercise with tests

1. Read the "Learning project" section of `CLAUDE.md`. If the type is "portfolio", she writes the tests, so give her the task and a list of cases worth testing instead of tests. If the repo has several stacks, pick the one the topic belongs to, or ask.
2. Take the topic from `$ARGUMENTS`. If there is no argument, suggest three topics for this stack that fit her level from the mentor style.
3. Design a 30 to 60 minute task that trains one topic. Take the domain from the project, e.g. rides and pricing in a scooter service; if the project has none, use fintech: money, accounts, payments, limits.
4. Write tests with the stack's test framework in the exercise tests folder from `CLAUDE.md`, under a subfolder named after the topic. The tests check behaviour through the public API, from simple cases to edge cases. Leave the solution code for her to create.
5. Run the tests and confirm they fail. A compile or import error because her code is missing also counts.
6. Reply with:
   - the task statement;
   - the names, signatures and paths of what she needs to create;
   - the command to run only these tests;
   - one rung 1 hint on where to start.
