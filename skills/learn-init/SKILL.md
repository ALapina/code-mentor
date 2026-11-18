---
name: learn-init
description: Connects the mentor to a learning project. Adds the style, the edit ban and the CLAUDE.md section.
argument-hint: "<exercises | portfolio>"
disable-model-invocation: true
---

# Connect the mentor to a project

Stack profiles live in `${CLAUDE_SKILL_DIR}/stacks/`: `java.md`, `python.md`, `typescript.md`. Each gives detection files, versions, test command, test framework, docs, and which folders are hers or open to AI per project type.

1. **Type.** Take it from `$ARGUMENTS`: `exercises` means AI writes exercise tests, `portfolio` means she writes all tests. If there is no argument, ask.
2. **Stacks.** Find every stack in the repo by its detection files, at the root and one level down, e.g. `backend/build.gradle.kts` and `web/package.json`. Each match is a stack root. Show her the list of stack roots with their stacks and ask her to confirm or correct it. For an empty folder, ask which stack she will use.
3. **Deny rules.** For each stack root, take the "Hers, edits denied" folders for the type and turn each into `Edit(/<stack root>/<folder>**)`, leaving out `<stack root>/` for the repo root. Example: `Edit(/backend/src/main/**)`, `Edit(/src/**)`.
4. **Settings.** Write `.claude/settings.json` in the repo root with `"outputStyle": "code-mentor:mentor"` and the rules under `permissions.deny`. If the file exists, add these and keep everything else unchanged.
5. **CLAUDE.md.** Write a `## Learning project` section in the root `CLAUDE.md`:
   - first line: `Type: <type>. The code-mentor plugin is active: she writes the solution, AI gives hints, explanations and reviews.`;
   - one subsection per stack root with its versions, test command, test framework, docs, the folders that are hers, and the folders open to AI with what goes there;
   - the line `Files in her folders change only by her hand, terminal included: shell commands such as echo, sed or cp leave them alone.`;
   - for portfolio: `AI-written code goes in its own commits marked [ai]; the README section "What I wrote and where AI helped" is built from them.`;
   - the command list: `/code-mentor:review`, `/code-mentor:compare`, `/code-mentor:teachback`, plus `/code-mentor:exercise` for exercises.
   If the file has a `## Learning project` section, replace it; if the file has no such section, append it; if there is no file, create it.
6. **Report.** Show her the resulting `.claude/settings.json` and the `CLAUDE.md` section. Tell her the mentor style starts with the next message and the edit ban starts in the next session in this project. Suggest committing both files, and leave the commit to her.

Done when both files are written, every confirmed stack root has its deny rules and its subsection, and she has seen the contents.
