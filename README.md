This is a Spring Boot application for managing a school library system. It includes functionality for managing students, books, and loan records.

## Prerequisites

Ensure you have the following installed on your system:

- Java 21
- MySQL 8.0 or higher

## Setup Instructions

### 1. Clone the Repository

```bash
git clone <repository-url>
cd school-library
```

### 2. Configure the Database

1. Create a MySQL database named `school`:
   ```sql
   CREATE DATABASE school;
   ```
2. Update the database connection details in `src/main/resources/application.yml` if necessary:
   ```yaml
   spring:
     datasource:
       url: jdbc:mysql://localhost:3306/school
       username: root
       password: password
   ```

### 3. Run Database Migrations

The project uses Flyway for database migrations. The migrations are located in `src/main/resources/db/migration`. Flyway will automatically run the migrations when the application starts.

### 4. Build and Run the Application

Use Maven to build and run the application:

```bash
mvn clean install
mvn spring-boot:run
```

### 5. Access the Application

The application will start on `http://localhost:8080`. You can configure the port in `application.yml` if needed.

## Additional Notes

- The database schema is automatically created and updated using Flyway and Hibernate.
- To view SQL queries executed by Hibernate, `spring.jpa.show-sql` is enabled in `application.yml`.

## Troubleshooting

- Ensure the MySQL service is running and accessible.
- Verify the database credentials in `application.yml` are correct.
- Check the logs for any errors during startup.