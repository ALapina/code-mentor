---
name: learn-init
description: Connects the mentor to a learning project. Adds the style, the edit ban and the CLAUDE.md section.
argument-hint: "<exercises | portfolio>"
disable-model-invocation: true
---

# Connect the mentor to a project

Stack profiles live in `${CLAUDE_SKILL_DIR}/stacks/`: `java.md`, `python.md`, `typescript.md` for frontend TypeScript, `node-backend.md` for Node.js services and shared packages. Each gives detection files, versions, test command, test framework, docs, and which folders are hers or open to AI per project type.

1. **Type.** Take it from `$ARGUMENTS`: `exercises` means AI writes exercise tests, `portfolio` means she writes all tests. If there is no argument, ask.
2. **Stacks.** Find every stack root:
   - the repo root and every folder one level down that has a profile's detection file, e.g. `backend/build.gradle.kts` and `web/package.json`;
   - every workspace package: expand the globs in `pnpm-workspace.yaml` under `packages`, or in the `workspaces` field of the root `package.json`, e.g. `apps/*` gives `apps/rides` and `apps/web`.
   For a `package.json`, pick the profile by its dependencies as each profile's Detect line says. A workspace root whose `package.json` only holds scripts and dev tools is not a stack root. Show her the list of stack roots with their stacks and ask her to confirm or correct it. For an empty folder, ask which stacks and folders she will use.
3. **Deny rules.**
   - For each stack root, take the "Hers, edits denied" folders for the type and turn each into `Edit(/<stack root>/<folder>**)`, leaving out `<stack root>/` for the repo root. Example: `Edit(/backend/src/main/**)`, `Edit(/apps/rides/src/**)`, `Edit(/src/**)`.
   - For portfolio, also deny her repo-wide files from the table below, whether they exist yet or not. Show her this list in the same message as the stack roots and let her add or remove paths.

   | Repo-wide, hers in portfolio | Rules |
   |---|---|
   | Infrastructure | `Edit(/compose.yaml)`, `Edit(/compose.yml)`, `Edit(/docker-compose.yaml)`, `Edit(/docker-compose.yml)`, `Edit(/infra/**)` |
   | CI | `Edit(/.github/workflows/**)` |
   | Design and write-up | `Edit(/DESIGN.md)`, `Edit(/docs/adr/**)`, `Edit(/README.md)`, `Edit(/LEARNING.md)` |

4. **Settings.** Write `.claude/settings.json` in the repo root with `"outputStyle": "code-mentor:mentor"` and the rules under `permissions.deny`. If the file exists, add these and keep everything else unchanged.
5. **CLAUDE.md.** Write a `## Learning project` section in the root `CLAUDE.md`:
   - first line: `Type: <type>. The code-mentor plugin is active: she writes the solution, AI gives hints, explanations and reviews.`;
   - one subsection per stack root with its versions, test command, test framework, docs, the folders that are hers, and the folders open to AI with what goes there;
   - for portfolio, a subsection with the repo-wide files that are hers;
   - the line `Files in her folders change only by her hand, terminal included: shell commands such as echo, sed or cp leave them alone.`;
   - for portfolio: `AI-written code goes in its own commits with a Co-Authored-By trailer naming the model; the README section "What I wrote and where AI helped" is built from them.`;
   - the command list: `/code-mentor:review`, `/code-mentor:compare`, `/code-mentor:teachback`, plus `/code-mentor:exercise` for exercises.
   If the file has a `## Learning project` section, replace it; if the file has no such section, append it; if there is no file, create it.
6. **Report.** Show her the resulting `.claude/settings.json` and the `CLAUDE.md` section. Tell her the mentor style starts with the next message and the edit ban starts in the next session in this project. Suggest committing both files, and leave the commit to her.

Done when both files are written, every confirmed stack root has its deny rules and its subsection, for portfolio the repo-wide rules are in place, and she has seen the contents.
