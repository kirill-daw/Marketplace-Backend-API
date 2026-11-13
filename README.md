# Marketplace Backend API

Backend application for a marketplace-style service where users can publish advertisements, manage profiles and communicate through comments.

The project was developed as the final project of the **SkyPro Java Developer program** and demonstrates the development of a complete REST API using the Spring ecosystem.

---

## About the project

The application implements the backend of an online marketplace similar to a classifieds platform.

Users can register, authenticate, publish advertisements, upload images, manage their profile and leave comments.

The application also implements role-based access control with separate permissions for regular users and administrators.

---

## Features

### Authentication and authorization

- user registration;
- authentication;
- role-based access control;
- `USER` and `ADMIN` roles;
- protection of restricted endpoints with Spring Security.

### Advertisements

- view all advertisements;
- view advertisement details;
- create advertisements;
- edit own advertisements;
- delete own advertisements;
- administrator access to manage all advertisements.

### Comments

- create comments;
- edit own comments;
- delete own comments;
- administrator access to manage comments.

### User profile

- view profile information;
- update personal information;
- change password;
- upload and retrieve user avatar.

### Images

- upload advertisement images;
- retrieve stored images;
- upload profile avatars.

### API documentation

REST endpoints are documented using Swagger / OpenAPI.

---

## Tech stack

| Area | Technology |
|---|---|
| Language | Java 11 |
| Framework | Spring Boot 2.7.15 |
| REST API | Spring Web |
| Security | Spring Security |
| Database | PostgreSQL |
| ORM | Spring Data JPA / Hibernate |
| Database migrations | Liquibase |
| Mapping | MapStruct |
| Validation | Spring Validation |
| Documentation | Springdoc OpenAPI / Swagger |
| Testing | JUnit, MockMvc, Spring Security Test, H2 |
| Build system | Maven |
| Boilerplate reduction | Lombok |

---

## Architecture

The application follows a layered backend architecture:

```text
com.skypro/
├── controller/       REST controllers
├── service/          business logic
├── repository/       Spring Data repositories
├── entity/           database entities
├── dto/              request and response models
├── mapper/           Entity ↔ DTO mapping
├── config/           application and security configuration
├── exception/        exception handling
└── filter/           web filters
```

The separation between controller, service and persistence layers makes the application easier to maintain and extend.

---

## Running the project

### Requirements

Before running the application, install:

- Java 11
- Maven
- Docker

---

### 1. Start the frontend

The frontend used with the project is distributed as a Docker image:

```bash
docker run -p 3000:3000 --rm ghcr.io/dmitry-bizin/front-react-avito:v1.21
```

The frontend will be available at:

```text
http://localhost:3000
```

---

### 2. Start PostgreSQL

```bash
docker run \
  --name postgres-avito \
  -e POSTGRES_PASSWORD=postgres \
  -e POSTGRES_DB=shop_db \
  -p 5433:5432 \
  -d postgres:15
```

Database configuration:

```text
Host: localhost
Port: 5433
Database: shop_db
User: postgres
Password: postgres
```

---

### 3. Build the backend

```bash
mvn clean install
```

---

### 4. Run the application

```bash
mvn spring-boot:run
```

The backend starts on port:

```text
8080
```

---

## Swagger

After starting the application, Swagger UI is available at:

```text
http://localhost:8080/swagger-ui/index.html
```

Swagger can be used to inspect and test the REST API without a separate API client.

---

## Testing

Run tests with:

```bash
mvn test
```

The project contains tests for important application scenarios, including:

- public endpoint access;
- authentication;
- authorization;
- resource ownership;
- administrator permissions.

---

## What this project demonstrates

This project demonstrates practical experience with:

- Java backend development;
- REST API design;
- Spring Boot architecture;
- authentication and authorization;
- role-based permissions;
- PostgreSQL integration;
- JPA and Hibernate;
- database migrations;
- DTO mapping;
- validation;
- API documentation;
- backend testing.

---

## Future improvements

Possible improvements include:

- Docker Compose for backend and database;
- JWT authentication;
- cloud deployment;
- CI/CD pipeline;
- extended integration tests;
- object storage for uploaded images;
- monitoring and logging.

---

## Author

**Kirill Davydov**

GitHub: https://github.com/kirill-daw
