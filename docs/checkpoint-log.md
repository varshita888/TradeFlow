# TradeFlow — Checkpoint Progress Log

## Checkpoint 0 — Environment Setup and Git Initialization

**Status:** Completed

### Verified Environment

- Windows 11
- VS Code with PowerShell
- Java JDK 21.0.1 LTS
- Maven Wrapper 3.10.1
- PostgreSQL CLI 17.12
- Git 2.55.0

### Completed Work

- Initialized the TradeFlow repository.
- Created the initial project directory structure.
- Configured Git and GitHub.
- Established the `main` branch.
- Verified GitHub repository connectivity.

**GitHub:** https://github.com/varshita888/TradeFlow

**Previously verified commit:** `24645e5`

---

## Checkpoint 1 — Requirements Analysis and System Architecture

**Status:** Deferred

The detailed conceptual activities and documentation have been postponed to prioritize implementation.

Requirements, architecture, and database design have not been formally finalized.

---

## Checkpoint 2 — Spring Boot Backend Setup and Project Initialization

**Status:** In Progress — Documentation and Git verification remaining

### 1. Completed Implementation Tasks

- Generated a Spring Boot 4.0.10 Maven project.
- Configured Java 21.
- Verified Maven Wrapper 3.10.1.
- Organized the backend source directory.
- Created backend package directories.
- Configured `application.properties`.
- Implemented `HealthController.java`.
- Verified the REST health-check endpoint.
- Verified Spring Boot Actuator health.
- Implemented automated controller testing.
- Executed Maven tests successfully.
- Updated the project README.

### 2. Technologies Used

- Java 21
- Spring Boot 4.0.10
- Spring Web MVC
- Spring Boot Actuator
- Maven Wrapper
- JUnit 5
- MockMvc
- Git

### 3. Backend Structure

```text
backend/
├── src/
│   ├── main/
│   │   ├── java/com/tradeflow/backend/
│   │   │   ├── controller/
│   │   │   │   └── HealthController.java
│   │   │   └── TradeflowBackendApplication.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
│       └── java/com/tradeflow/backend/
│           ├── controller/
│           │   └── HealthControllerTest.java
│           └── TradeflowBackendApplicationTests.java
├── pom.xml
├── mvnw
└── mvnw.cmd
```

Additional empty package directories exist locally for future implementation.

### 4. Configuration

- Application name: `tradeflow-backend`
- HTTP port: `8080`
- Default logging level: `INFO`
- Application package logging level: `DEBUG`
- Exposed Actuator endpoints: `health`, `info`

### 5. Implemented Endpoints

**Custom health endpoint**

`GET /api/health`

Verified HTTP response:

```json
{
  "status": "UP",
  "application": "TradeFlow Backend"
}
```

HTTP status: `200 OK`

**Actuator health endpoint**

`GET /actuator/health`

Verified response:

```json
{
  "groups": ["liveness", "readiness"],
  "status": "UP"
}
```

HTTP status: `200 OK`

### 6. Verified Tests

**Maven compilation**

Command:

```powershell
.\mvnw.cmd clean compile
```

Result: `BUILD SUCCESS`

Two application source files compiled successfully at the time of verification.

**JUnit tests**

Command:

```powershell
.\mvnw.cmd clean test
```

Results:

```text
Tests run: 2
Failures: 0
Errors: 0
Skipped: 0
BUILD SUCCESS
```

### 7. Errors Encountered and Resolutions

**Nested Spring Boot directory**

The generated project was initially extracted into `backend/tradeflow-backend/`.

Resolution: Moved generated files directly into `backend/` and verified the directory structure.

**Maven command not recognized**

The global `mvn` command was unavailable in PowerShell.

Resolution: Used the project's Maven Wrapper, `mvnw.cmd`.

**PowerShell HTTP parsing warning**

`Invoke-WebRequest` displayed a script execution warning.

Resolution: Used `-UseBasicParsing` or `Invoke-RestMethod`.

**JUnit compilation errors**

A duplicate test file was placed under `src/main/java`, where test-scoped dependencies are unavailable.

Resolution: Removed the misplaced copy and retained the test file under `src/test/java`.

**Empty test file**

The correctly located JUnit test file initially contained no code.

Resolution: Added the controller test implementation and verified the Maven test suite passed.

### 8. Remaining Limitations

- PostgreSQL server connectivity not verified.
- Database persistence not implemented.
- Trade management functionality not implemented.
- Settlement and reconciliation functionality not implemented.
- JavaFX frontend not implemented.
- Docker deployment not configured.
- Final Git commit and push pending.
- Final post-documentation build verification pending.

### 9. Next Steps

- Complete documentation verification.
- Run final Maven build and tests.
- Review Git changes and ignore rules.
- Commit and push Checkpoint 2 implementation.
- Record final commit hash and Git status.
- Confirm Checkpoint 2 completion before beginning Checkpoint 3.
