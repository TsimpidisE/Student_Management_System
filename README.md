# Student Management System

A Spring Boot application providing a RESTful API for managing students, courses, and enrollments in an educational institution. Demonstrates key Spring Boot features such as RESTful services, Spring Data JPA, validation, and error handling.

## Table of Contents
- [Features](#features)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

## Features
- CRUD operations for Students, Courses, and Enrollments
- Input validation and global exception handling
- Pagination and sorting for list endpoints
- In-memory H2 database with option to switch to MySQL

## Project Structure

```
Student_Management_System/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/tsimpidise/sms/
│   │   │       ├── config/         # Configuration (Swagger, CORS)
│   │   │       ├── controller/     # REST controllers for Students, Courses, Enrollments
│   │   │       ├── dto/            # Data Transfer Objects for API payloads
│   │   │       ├── exception/      # Custom exceptions and exception handlers
│   │   │       ├── model/          # JPA entities (Student, Course, Enrollment)
│   │   │       ├── repository/     # Spring Data JPA repositories
│   │   │       └── service/        # Business logic and transaction management
│   │   └── resources/
│   │       ├── application.properties  # Database and app configs
│   │       └── data.sql                # Sample seed data
│   └── test/
│       └── java/
│           └── com/tsimpidise/sms/      # Unit and integration tests
├── mvnw                                  # Maven wrapper
├── pom.xml                               # Maven build and dependencies
└── README.md                             # Project documentation
```

## Prerequisites
- Java 8 or higher
- Maven 3.6+
- (Optional) MySQL database if switching from H2

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/TsimpidisE/Student_Management_System.git
   cd Student_Management_System
   ```
2. Build the project:
   ```bash
   ./mvnw clean install
   ```

## Configuration
By default, the app uses an in-memory H2 database. To use MySQL, update `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/sms_db
spring.datasource.username=<username>
spring.datasource.password=<password>
spring.jpa.hibernate.ddl-auto=update
```

## Usage
Start the application:
```bash
./mvnw spring-boot:run
```
Access the API at `http://localhost:8080/api`.

## API Endpoints
| Method | Endpoint                  | Description                         |
| ------ | ------------------------- | ----------------------------------- |
| GET    | /api/students             | List all students                   |
| POST   | /api/students             | Create a new student                |
| GET    | /api/students/{id}        | Get student details by ID           |
| PUT    | /api/students/{id}        | Update student information          |
| DELETE | /api/students/{id}        | Delete a student                    |
| GET    | /api/courses              | List all courses                    |
| POST   | /api/courses              | Create a new course                 |
| GET    | /api/enrollments          | List all enrollments                |
| POST   | /api/enrollments          | Enroll a student in a course        |

## Contributing
Contributions are welcome! Fork the repo, make changes, and submit a pull request.

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Author
Efthymios Tsimpidis  
GitHub: https://github.com/TsimpidisE
