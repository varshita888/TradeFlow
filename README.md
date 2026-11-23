# TradeFlow — Trade Settlement & Reconciliation Management System

## Overview

TradeFlow is a full-stack financial trade settlement and reconciliation management system built using Java, JavaFX, Spring Boot, and PostgreSQL.

The application aims to manage financial trades, track settlement lifecycles, reconcile transaction records, detect mismatches, and maintain exception and audit records.

**Current status:** Spring Boot backend initialized with a working health-check REST API and automated tests. Core trade management, database integration, and JavaFX frontend development are planned for later checkpoints.

## Technology Stack

- **Language:** Java 21
- **Backend:** Spring Boot 4.0.10, Spring Web MVC
- **Frontend (Planned):** JavaFX
- **Database (Planned):** PostgreSQL 17
- **Persistence (Planned):** Spring Data JPA, Hibernate, JDBC
- **Build Tool:** Maven Wrapper 3.10.1
- **Testing:** JUnit 5, Spring MVC Test, MockMvc
- **Monitoring:** Spring Boot Actuator
- **Deployment (Planned):** Docker
- **Version Control:** Git and GitHub

## Planned Features

1. Trade creation, viewing, updating, and deletion
2. Trade lifecycle and settlement status tracking
3. Settlement record management
4. CSV-based transaction reconciliation
5. Mismatch and missing-record detection
6. Exception tracking and audit logging
7. Transaction search, filtering, and reporting
8. Database query optimization
9. Unit and integration testing
10. Containerization and deployment

## Architecture

The following represents the planned application architecture:

```text
JavaFX Desktop Application
           |
           | REST API
           v
    Spring Boot Backend
           |
           | JPA / JDBC
           v
    PostgreSQL Database
```

Currently, only the Spring Boot backend foundation and health-check endpoints have been implemented.

## Project Structure

```text
TradeFlow/
├── backend/       # Spring Boot REST API
├── frontend/      # JavaFX desktop application (planned)
├── database/      # Database scripts and migrations (planned)
├── docs/          # Technical documentation
├── scripts/       # Development and deployment scripts
├── tests/         # Integration and end-to-end tests (planned)
├── .gitignore
└── README.md
```

### Backend Package Structure

```text
com.tradeflow.backend
├── controller/     # REST controllers
├── service/        # Business logic (planned)
├── repository/     # Database access (planned)
├── entity/         # Persistence entities (planned)
├── dto/            # API data transfer objects (planned)
├── exception/      # Exception handling (planned)
├── config/         # Application configuration (planned)
└── TradeflowBackendApplication.java
```

Empty package directories may not appear in Git until Java files are added.

## Getting Started

### Prerequisites

- Java JDK 21
- Windows PowerShell
- Git
- Internet connection for initial Maven dependency downloads

A separate Maven installation is not required because the project includes Maven Wrapper.

### 1. Clone the Repository

```powershell
git clone https://github.com/varshita888/TradeFlow.git
cd TradeFlow
```

### 2. Navigate to Backend

```powershell
cd backend
```

### 3. Run the Application

```powershell
.\mvnw.cmd spring-boot:run
```

The backend runs on:

```text
http://localhost:8080
```

### 4. Test the Health-Check REST API

```powershell
Invoke-RestMethod -Uri "http://localhost:8080/api/health"
```

Expected JSON response:

```json
{
  "status": "UP",
  "application": "TradeFlow Backend"
}
```

### 5. Test Spring Boot Actuator

```powershell
Invoke-RestMethod -Uri "http://localhost:8080/actuator/health"
```

The endpoint reports application health.

### 6. Run Automated Tests

```powershell
.\mvnw.cmd clean test
```

Latest verified result:

```text
Tests run: 2, Failures: 0, Errors: 0, Skipped: 0
BUILD SUCCESS
```

### 7. Build the Application

```powershell
.\mvnw.cmd clean verify
```

The Maven build packages the Spring Boot application into an executable JAR inside `backend/target/`.

## Implemented Features

### Spring Boot Backend Initialization

- Spring Boot 4.0.10 project generated
- Java 21 configured
- Maven Wrapper configured
- Backend package structure established
- Application properties configured

### REST API

**Endpoint:** `GET /api/health`

Returns HTTP 200 and a JSON response containing the application name and health status.

### Monitoring

**Endpoint:** `GET /actuator/health`

Provides Spring Boot Actuator health information.

### Automated Testing

- Spring Boot application context test
- Health controller test using MockMvc
- Two tests passed with zero failures or errors

## Development Progress

| Checkpoint | Description | Status |
|---|---|---|
| 0 | Environment Setup and Git Initialization | Completed |
| 1 | Requirements Analysis and System Architecture | Deferred |
| 2 | Spring Boot Backend Setup and Initialization | In Progress — Final Documentation and Git Verification |
| 3 | Next Implementation Checkpoint | Not Started |

Checkpoint 1's detailed requirements and architecture have not been formally finalized.

## Known Limitations

- PostgreSQL connectivity has not yet been verified.
- No trade management or settlement business logic has been implemented.
- No JavaFX frontend has been implemented.
- No reconciliation functionality has been implemented.
- Docker deployment has not been configured.
- Current health checks do not validate database connectivity.

## Documentation

Checkpoint progress and implementation details will be maintained in:

`docs/checkpoint-log.md`

## License

License to be determined.
