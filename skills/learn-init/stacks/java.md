# Stack: java

Detect: `build.gradle`, `build.gradle.kts` or `pom.xml`.

- **Versions**: Java 21, Spring Boot 3.
- **Test command**: `./gradlew test`, or `./mvnw test` for Maven. One class: `./gradlew test --tests '<Class>'`.
- **Test framework**: JUnit 5 and AssertJ; Testcontainers for PostgreSQL and Kafka.
- **Docs**: https://docs.oracle.com/en/java/javase/21/ , https://docs.spring.io/spring-boot/ , https://www.postgresql.org/docs/current/

| Type | Learner's, edits denied | Open to AI |
|---|---|---|
| exercises | `src/main/` | `src/test/java/exercises/` for exercise tests, `src/test/resources/` for test data |
| portfolio | `src/main/`, `src/test/` | `src/testFixtures/` for fakes, stubs and data generators through the Gradle `java-test-fixtures` plugin, `dev/` for external-service stubs, scripts and seeds |
