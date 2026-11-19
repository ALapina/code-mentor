# code-mentor

A Claude Code plugin that turns Claude into a programming mentor. It gives hints, explains and reviews; you write the solution. It works across stacks: Java and Spring Boot, Python, Node.js services in TypeScript, Next.js and React.

## What's inside

- `output-styles/mentor.md`: the mentor style. A hint ladder, explanations pitched to your level on each topic, and finished code only after you say "show solution".
- `skills/learn-init/stacks/`: one profile per stack with versions, test command, test framework, docs, and which folders are yours or open to AI. Add a file here to support a new stack.
- Commands:
  - `/code-mentor:learn-init exercises` or `portfolio` connects the mentor to a project and detects its stacks, including repos with several, e.g. `backend/` and `web/`, and pnpm or npm workspace packages such as `apps/rides`. In portfolio projects it also locks repo-wide files that are hers: Compose, `infra/`, CI workflows, `DESIGN.md`, ADRs, README and `LEARNING.md`;
  - `/code-mentor:review` reviews your code without writing the fix;
  - `/code-mentor:compare` compares your finished solution with an idiomatic one;
  - `/code-mentor:exercise <topic>` creates an exercise with failing tests;
  - `/code-mentor:teachback <topic>` checks your explanation of a topic in your own words.

## Install on this Mac

The plugin is linked from `~/.claude/skills/code-mentor` to this folder. Changes here are picked up in the next session or after `/reload-plugins`.

```bash
ln -s ../../learning/code-mentor ~/.claude/skills/code-mentor
```

The commands are visible in every project but run only when you call them. The style and the edit ban apply only in projects where you ran `learn-init`.

## New learning project

1. Create the project, e.g. with start.spring.io or `create-next-app`.
2. Open a Claude Code session in it and run `/code-mentor:learn-init exercises` or `/code-mentor:learn-init portfolio`.
3. Commit `.claude/settings.json` and `CLAUDE.md`.
4. Start a new session so the edit ban takes effect.

## Limits

- The style is an instruction, not a lock. The deny rules in `.claude/settings.json` block the built-in edit tools but not terminal commands. If you see Claude get around them, the next step is a PreToolUse hook.
- The Java portfolio profile assumes Gradle and `java-test-fixtures`. The Python profile assumes the `src/` layout. The Node backend profile assumes `src/`, `test/` and `migrations/` in each service.
- Projects connected before version 0.3.0 keep their old deny rules. Run `learn-init` again to get the workspace packages and repo-wide files.
- Your level per topic lives in the style. Update it as you learn.
