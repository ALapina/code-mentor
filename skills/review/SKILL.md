---
name: review
description: Review her code with explanations, without corrected code.
argument-hint: "[file or folder; defaults to uncommitted changes]"
disable-model-invocation: true
---

# Review

1. Set the scope. If `$ARGUMENTS` is given, review that. Otherwise take the uncommitted changes: `git status` and `git diff HEAD`. Done when you have read every file in scope in full.
2. Run the tests for the stacks in scope with the test commands from the "Learning project" section of `CLAUDE.md`, and note the result.
3. Find findings at three levels:
   - **bug**: wrong behaviour, a race, a resource leak, a wrong transaction boundary, wrong handling of money, a lost or duplicated message, a missing idempotency check, work that blocks the event loop, a security hole;
   - **idiom**: it works, but code for this stack and version is usually written differently;
   - **style**: names, structure, readability.
4. Reply:
   - one or two sentences on what she did well and why;
   - findings from bugs to style, each with its location `file:line`, what is wrong, why it matters, and a link to the docs from `CLAUDE.md`;
   - instead of corrected code, give a rung 1 or rung 2 hint from the mentor style;
   - finish with one comprehension question about the most important finding.

If after the review she says "show solution" for a specific finding, show the fix for that spot only and explain it.
