# TaskManagement Backend (Spring Boot)

Backend service for a task management system built with **Spring Boot 3.5.x**, **Java 17**, **Spring Security + JWT**, **Spring Data JPA (MySQL)**, and **OpenFeign**.

> Workspace project: `Taskmanagement/`

## What’s in this backend

- REST APIs under `/api/**`
- Authentication & authorization using **JWT**
- Persistence using **MySQL** via **Spring Data JPA**
- Integrations via **Spring Cloud OpenFeign**
- Optional integrations:
  - Email via Spring Mail
  - File/image hosting via Cloudinary
  - PDF generation (iText)

## Tech stack

- Java **17**
- Spring Boot **3.5.6**
- Spring Security
- Spring Data JPA
- MySQL connector
- Spring Cloud OpenFeign (BOM `2024.0.0`)
- JWT (jjwt 0.11.5)

## Project structure (high level)

- `src/main/java/com/TaskManagement/Controller` – REST controllers
- `src/main/java/com/TaskManagement/Service` – business logic
- `src/main/java/com/TaskManagement/Repository` – JPA repositories
- `src/main/java/com/TaskManagement/Security` – JWT/security config
- `src/main/resources/application.properties` – runtime configuration
- `src/main/resources/application.properties.example` – template

## Prerequisites

- **Java 17** installed
- **Maven** (or use the included Maven Wrapper `mvnw.cmd`)
- **MySQL** running and accessible

## Configuration

### 1) Create your local `application.properties`

This repo contains an example file:

- `src/main/resources/application.properties.example`

Copy it to `application.properties` and edit values:

```bat
copy src\main\resources\application.properties.example src\main\resources\application.properties
```

### 2) Required settings

At minimum you must set:

- `spring.datasource.url`
- `spring.datasource.username`
- `spring.datasource.password`
- `jwt.secret`

Example (do not use in production):

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/taskmanagement
spring.datasource.username=root
spring.datasource.password=your_password
server.port=8081

jwt.secret=change_me_to_a_long_random_secret
jwt.expiration=86400000
```

### 3) Optional service-to-service URLs (Feign)

If your system has other services running:

```properties
issue.service.url=http://localhost:8082
user.service.url=http://localhost:8083
```

### 4) Cloudinary (optional)

```properties
cloudinary.cloud_name=
cloudinary.api_key=
cloudinary.api_secret=
```

### 5) Email (optional)

Uncomment & configure in `application.properties`:

```properties
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=your-email@gmail.com
spring.mail.password=your-app-password
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true
```

## Run the backend (Windows / cmd)

From the project folder `Taskmanagement`:

### Option A: Maven Wrapper (recommended)

```bat
mvnw.cmd clean spring-boot:run
```

### Option B: Installed Maven

```bat
mvn clean spring-boot:run
```

The app runs on:

- `http://localhost:8081` (as configured by `server.port`)

## Build

```bat
mvnw.cmd clean package
```

## Test

```bat
mvnw.cmd test
```

## API quick check

A simple health-ish endpoint exists:

- `GET /api/userAuthentication/welcome`

Authentication endpoints:

- `POST /api/userAuthentication/register`
- `POST /api/userAuthentication/login`

> Additional endpoints are available under controllers in `src/main/java/com/TaskManagement/Controller`.

## Notes / Security

- Don’t commit real secrets (DB password, JWT secret, Cloudinary keys).
- Prefer environment variables or a `application-local.properties` that’s ignored by Git.

## Troubleshooting

- **Port already in use**: change `server.port` in `application.properties`.
- **DB connection errors**: confirm MySQL is running and the database exists, and credentials are correct.
- **401/403 errors**: ensure you’re sending the JWT token in the `Authorization: Bearer <token>` header for secured endpoints.