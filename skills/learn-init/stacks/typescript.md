# Stack: typescript

Detect: `package.json` with `react`, `next` or `vite` in its dependencies. Covers Next.js and React frontends; Node.js services use `node-backend.md`.

- **Versions**: from `package.json`: Next.js, React, TypeScript, Node.
- **Test command**: the `test` script from `package.json` with the project's package manager, e.g. `pnpm test`. End-to-end: the Playwright script if there is one.
- **Test framework**: Vitest and Testing Library; Playwright for end-to-end.
- **Docs**: https://nextjs.org/docs , https://react.dev/reference/react , https://www.typescriptlang.org/docs/

| Type | Hers, edits denied | Open to AI |
|---|---|---|
| exercises | `src/`, `app/` | `tests/exercises/` for exercise tests; her solutions go in `src/exercises/` |
| portfolio | `src/`, `app/`, `tests/`, `e2e/` | `mocks/` for MSW handlers and fake APIs, `fixtures/` for test data, `dev/` for scripts and seeds |
