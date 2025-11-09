# Student Management REST API

This project provides a simple REST API for managing students using Spring Boot 3+, Spring Data JPA, and H2 in-memory database.

## Features
- Add student (POST `/api/students`)
- Get all students (GET `/api/students`)
- Get student by ID (GET `/api/students/{id}`)
- Update student (PUT `/api/students/{id}`)
- Delete student (DELETE `/api/students/{id}`)
- Field validation with clear error messages (email format, non-null, age > 18)
- Global Exception Handling
- Swagger UI documentation for easy testing

## Prerequisites
- Java 17 or +
- Maven 3.6+
- (Optional) Any REST client like Postman or simply use Swagger UI

## Run the Application
1. Clone the repository.
2. Navigate to the project directory.
3. Build the project: