# Stack: node-backend

Detect: `package.json` with a server framework in `dependencies` (`fastify`, `express`, `@nestjs/core`, `koa`, `hono`), or a workspace package with neither a server framework nor `react`, `next` or `vite`, such as a shared contracts or platform package.

- **Versions**: from `package.json` and `.nvmrc`: Node.js, TypeScript, the server framework, the database client and query builder.
- **Test command**: the `test` script from `package.json` with the project's package manager, e.g. `pnpm test`; one file: `pnpm vitest run <path>`. Tests with Testcontainers need Docker running.
- **Test framework**: Vitest; Testcontainers for MySQL, PostgreSQL, Kafka and Elasticsearch; the framework's own injection, e.g. Fastify `inject()`, for HTTP.
- **Docs**: https://nodejs.org/docs/latest/api/ , https://www.typescriptlang.org/docs/ , plus the docs of what `package.json` uses, e.g. https://fastify.dev/docs/latest/ , https://kysely.dev/docs/intro , https://node.testcontainers.org/ . For the database, broker and search engine, link the docs for the versions in `compose.yaml`.

| Type | Learner's, edits denied | Open to AI |
|---|---|---|
| exercises | `src/`, `migrations/` | `test/exercises/` for exercise tests, `fixtures/` for test data |
| portfolio | `src/`, `test/`, `tests/`, `migrations/` | `fixtures/` for fakes, stubs and test data, `seeds/` for seed data and seed scripts that call the learner's code, `dev/` for local scripts |
