

# ERP Management System

This project is an **Enterprise Resource Planning (ERP)** system built using **Spring Boot**. It covers various modules such as employee management, client handling, inventory tracking, and more.

## Project Structure

### **Project Architecture:**

Here's a common **layered architecture** you can follow for the ERP Management System:

```
com.example.erpmanagement
├── controller            # REST controllers to handle requests
├── service               # Business logic layer
├── repository            # Data access layer (using Spring Data JPA)
├── entity                # JPA entities representing database tables
├── dto                   # Data Transfer Objects (optional, for cleaner API responses)
├── config                # Configuration files (e.g., security, email)
└── exception             # Custom exceptions and handlers
```

### **Project Folder Structure**:

```
src/
├── main/
│   ├── java/
│   │   └── com/example/erpmanagement
│   │       ├── controller/
│   │       ├── service/
│   │       ├── repository/
│   │       ├── entity/
│   │       ├── dto/
│   │       ├── config/
│   │       └── exception/
│   └── resources/
│       ├── application.properties
│       └── templates/        # Optional: For email templates
└── test/
    └── java/
        └── com/example/erpmanagement
```

### **Component Overview**:
1. **Controller Layer**:
   - Handles incoming HTTP requests.
   - Example: `EmployeeController.java` for managing employee-related requests.

2. **Service Layer**:
   - Contains business logic.
   - Example: `EmployeeService.java` for employee-related operations.

3. **Repository Layer**:
   - Handles database interaction, typically using **Spring Data JPA**.
   - Example: `EmployeeRepository.java`.

4. **Entity Layer**:
   - Represents the database structure using JPA entities.
   - Example: `Employee.java`.

5. **DTO Layer** (Optional):
   - Used to expose only necessary data to the clients, avoiding direct entity exposure.

6. **Configuration Layer**:
   - Contains configurations such as security settings, email setup, etc.
   - Example: `SecurityConfig.java`.

7. **Exception Layer**:
   - Handles custom exceptions and error handling.
   - Example: `GlobalExceptionHandler.java`.

---


The project follows a layered architecture:

```
com.example.erpmanagement
├── controller            # REST controllers to handle requests
├── service               # Business logic layer
├── repository            # Data access layer (using Spring Data JPA)
├── entity                # JPA entities representing database tables
├── dto                   # Data Transfer Objects
├── config                # Configuration files (e.g., security, email)
└── exception             # Custom exceptions and handlers
```

## Features

- **Employee Management**: Add, update, and delete employee records.
- **Client Handling**: Manage client information and interaction.
- **Inventory Tracking**: Track stock and products in inventory.
- **Email Notification**: Send email notifications for various actions (uses Spring Boot Mail).
- **User Authentication & Authorization**: Secure endpoints using **Spring Security**.

## Technologies Used

- **Java 17**
- **Spring Boot**
- **Spring Data JPA**
- **Spring Security**
- **Spring Boot Starter Mail**
- **Hibernate**
- **MySQL** (or any relational database)
- **Maven** (for project build)
- **JUnit 5** and **Mockito** (for testing)

## How to Run

### Prerequisites

- Java 17
- Maven
- MySQL (or any other database of choice)

### Steps to Run:

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/erp-management-system.git
   cd erp-management-system
   ```

2. Configure the database:

   Update the `src/main/resources/application.properties` file with your database details:

   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/erp_db
   spring.datasource.username=root
   spring.datasource.password=yourpassword

   spring.jpa.hibernate.ddl-auto=update
   ```

3. Build the project using Maven:

   ```bash
   mvn clean install
   ```

4. Run the application:

   ```bash
   mvn spring-boot:run
   ```

5. The application will be running on `http://localhost:8080`.

### API Endpoints

#### Employee Management

- **GET /api/employees** - Get all employees
- **POST /api/employees** - Add a new employee
- **PUT /api/employees/{id}** - Update an employee
- **DELETE /api/employees/{id}** - Delete an employee

#### Client Management

- **GET /api/clients** - Get all clients
- **POST /api/clients** - Add a new client
- **PUT /api/clients/{id}** - Update a client
- **DELETE /api/clients/{id}** - Delete a client

## Running Tests

You can run unit tests using Maven:

```bash
mvn test
```

The test suite includes unit tests using **JUnit 5** and mock-based testing with **Mockito**.

## Contribution

Feel free to fork this repository and submit pull requests for any improvements or new features.

