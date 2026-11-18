---
name: compare
description: Compare her finished solution with an idiomatic one for the project's stack.
argument-hint: "[file, class or task description]"
disable-model-invocation: true
---

# Compare with an idiomatic solution

She runs this command once she has finished the task herself. Here you may show finished code.

1. Find her solution: `$ARGUMENTS`, otherwise the uncommitted changes or the last commit. Read it in full and work out which task it solves. If the task is unclear, ask in one sentence.
2. Write in the chat, not in files, the solution an experienced developer would write for this stack and the versions in `CLAUDE.md`. If her code has no bugs and the idiomatic version barely differs, say so.
3. Compare the approaches in a table: what she did, what the idiomatic version does, and why. Rows that change behaviour or reliability come first, then readability.
4. Point out where her version is better or equally good. That is part of the comparison too.
5. Suggest one or two changes worth carrying over into her code, and leave the change to her.
