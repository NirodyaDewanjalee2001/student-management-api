### **Student Management REST API**

This is a simple REST API for managing students, built with Spring Boot 3+, Spring Data JPA, 
and H2 in-memory database. It includes CRUD operations, field validation, global exception handling, 
proper HTTP status codes, and bonus features like Swagger UI for testing, pagination/sorting, 
and search functionality.

# Features

**CRUD Operations**: Add, retrieve, update, and delete students.
**Field Validation**: Email format, non-null fields, age > 18.
**Global Exception Handling**: Returns appropriate HTTP status codes (e.g., 400 for bad requests, 404 for not found).
**Service Layer Architecture**: Controllers call services, which interact with repositories.
**Swagger UI**: Interactive API documentation and testing at http://localhost:8080/swagger-ui.html.
**Pagination & Sorting**: GET all students supports page, size, and sort query parameters (e.g., ?page=0&size=5&sort=name,asc).
**Search**: Filter students by name or course (e.g., ?name=John&course=CS).
**Database**: H2 in-memory 

# Prerequisites

* Java 17+
* Maven 3.6+
* (Optional) Postman for API testing

# Steps to Run

1. Clone or download the project.
2. Navigate to the project root directory.
3. Build the project: mvn clean install
4. Run the Spring Boot application: mvn spring-boot:run
5. The API will be available at http://localhost:8080/api/students
6. Swagger UI: Visit http://localhost:8080/swagger-ui.html for interactive API documentation and testing.
   H2 Console: Access at http://localhost:8080/h2-console (JDBC URL: jdbc:h2:mem:testdb, Username: sa, Password: empty).

# API Endpoints

Add Student -> POST -> /api/students -> Create a new student (returns 201 Created).

Get All Students -> GET -> /api/students -> Retrieve all students with optional pagination, sorting, and search (returns 200 OK).

Get Student By ID -> GET -> /api/students/{id} ->Retrieve a student by ID (returns 200 OK or 404 Not Found).

Update Student -> PUT -> /api/students/{id} ->Update a student by ID (returns 200 OK or 404 Not Found).

Delete Student -> DELETE -> /api/students/{id} -> Delete a student by ID (returns 204 No Content or 404 Not Found).


## Query Parameters for GET All Students

page (default: 0): Page number (0-based).
size (default: 10): Number of students per page.
sort (default: id,asc): Sort field and direction (e.g., name,desc).
name (optional): Search by name (partial match, case-insensitive).
course (optional): Search by course (partial match, case-insensitive).  

# Testing with Postman or Swagger UI

## Swagger UI: 

The easiest way—visit http://localhost:8080/swagger-ui.html, expand endpoints, enter parameters, and click "Try it out" for live testing.

## Postman: 

Import the endpoints above. Set headers (e.g., Content-Type: application/json for POST/PUT). 
Use query params for GET requests.

Validation Examples:
Invalid email: Returns 400 with {"email": "Invalid email format"}.
Age < 19: Returns 400 with {"age": "Age must be greater than 18"}.
Invalid ID (e.g., /api/students/abc): Returns 400 with "Invalid path parameter: The 'id' must be a valid number.".
Malformed JSON: Returns 400 with custom message.

