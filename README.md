# Hewlett Packard Enterprise - Software Engineering Project

## Overview

This project is a RESTful web service built using **Java Spring Boot** designed to manage employee data. The service supports HTTP **GET** requests to retrieve employee information and HTTP **POST** requests to add new employees dynamically. The employee data includes fields such as employee ID, first name, last name, email, and job title.

The application was developed as part of a software engineering program with a focus on backend development, RESTful API design, and unit testing using frameworks like **JUnit** and **Mockito**.

---

## Features

- **Retrieve Employees:** Supports HTTP GET requests at `/employees` endpoint to fetch the full list of employees in JSON format.
- **Add Employees:** Supports HTTP POST requests at `/employees` to add a new employee to the system via JSON payload.
- **Data Management:** Employee data is initially hardcoded and stored in-memory, demonstrating core backend RESTful service concepts.
- **Unit Testing:** Comprehensive unit tests implemented using JUnit and Mockito frameworks to validate service functionality.
- **Build & Run:** Uses Gradle as the build tool for compiling, testing, and running the application.

---

## Technologies Used

- Java 21
- Spring Boot 3.5.3
- Gradle 9.0.0
- JUnit 5
- Mockito
- Git & GitHub

---

## Getting Started

### Prerequisites

- Java Development Kit (JDK) 17 or higher installed
- Gradle installed (or use Gradle wrapper included)
- Git installed
- Internet connection for cloning this repository

### Installation and Setup

1. **Clone the repository:**

   ```
   git clone https://github.com/KibutuJr/Hewlett-Packard-Enterprise---Software-Engineering-Project.git
   cd Hewlett-Packard-Enterprise---Software-Engineering-Project
   ```

2. **Build the project:**

   Using Gradle wrapper (recommended):

   ```
   ./gradlew build
   ```

   Or using installed Gradle:

   ```
   gradle build
   ```

3. **Run the application:**

   ```
   ./gradlew bootRun
   ```

   The server will start on `http://localhost:8080`.

---

## Usage

### Fetch All Employees

Send an HTTP GET request to:

```
http://localhost:8080/employees
```

Example response:

```
{
  "employeeList": [
    {
      "employee_id": "E001",
      "first_name": "John",
      "last_name": "Doe",
      "email": "john.doe@example.com",
      "title": "Software Engineer"
    },
    {
      "employee_id": "E002",
      "first_name": "Jane",
      "last_name": "Smith",
      "email": "jane.smith@example.com",
      "title": "Project Manager"
    }
    // more employees...
  ]
}
```

### Add a New Employee

Send an HTTP POST request to:

```
http://localhost:8080/employees
```

With JSON body:

```json
{
  "employee_id": "E005",
  "first_name": "Michael",
  "last_name": "Scott",
  "email": "michael.scott@dundermifflin.com",
  "title": "Regional Manager"
}
```

The employee will be added to the in-memory list and retrievable via GET requests.

---

## Testing

Unit tests are located in the `src/test/java` directory and cover core service functionalities.

To run tests:

```bash
./gradlew test
```

Test reports will be generated in `build/reports/tests/test/index.html`.

---

## Project Structure

```
src/
├── main/
│   ├── java/com/example/restservice/
│   │   ├── Employee.java          # Employee data model with getters/setters
│   │   ├── Employees.java         # Manages list of Employee objects
│   │   ├── EmployeeManager.java   # Initializes employees, handles additions
│   │   ├── EmployeeController.java # REST controller for GET and POST requests
│   │   └── RestServiceApplication.java # Spring Boot main application class
│   └── resources/
│       └── application.properties # Application config
└── test/
    └── java/com/example/restservice/
        └── EmployeeManagerTest
        └── EmployeeControllerTest
```

---

## Notes

* Employee data is currently stored in-memory and resets on server restart.
* No database is connected in this version; can be extended for persistent storage.
* Future work can include DELETE and UPDATE endpoints, authentication, and integration with cloud storage.

---

## Author

Fred Kibutu

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

## Contact

For questions or support, please reach out via GitHub issues or email: \[[kibutujr@gmail.com](mailto:kibutujr@gmail.com)]

---
