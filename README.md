# Microservice store management

A REST API built with Spring Boot around 1 JPA entity, using PostgreSQL.

## Tech stack

- Java 19, built with Maven
- Spring Boot 2.7.4
- Spring Web (REST controllers)
- Spring Data JPA (Hibernate)
- Spring Data REST
- Spring Boot Actuator
- Lombok
- PostgreSQL driver
- Database: PostgreSQL (`productdb` in `application.properties`)

## Data model

| Entity | Fields |
|---|---|
| `Product` | id, name, price, fabricationDate, expirationDate, description, stock |

## REST endpoints

Found in the controllers (`ProductController`):

| Method | Path |
|---|---|
| GET | `/all` |
| GET | `/product/{id}` |
| POST | `/add` |
| GET | `/expired` |
| DELETE | `/delete/{id}` |
| PUT | `/update/{id}` |

## Project structure

- `tn.esb.siad.productApi`: ProductApiApplication
- `tn.esb.siad.productApi.Entities`: Product
- `tn.esb.siad.productApi.Repositories`: ProductRepository
- `tn.esb.siad.productApi.Services`: ProductService
- `tn.esb.siad.productApi.Web`: ProductController
- Tests: 1 test class

## How to run

Requirements: a JDK 19+ and Maven (or the included Maven wrapper).
Create the `productdb` database and set your own username and password in `src/main/resources/application.properties`.

```bash
./mvnw spring-boot:run
```

The API then listens on `http://localhost:8080`.

---

Author: [Chaouki Bayoudhi](https://github.com/ChaoukiBayoudhi)
