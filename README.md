# Spring Boot Student App 📚

A simple Spring Boot application that demonstrates how to interact with a PostgreSQL database using JPA.

## Features ✨
- Spring Boot with JPA for database interaction.
- PostgreSQL setup using Docker 🐳.
- Saves a sample student on app startup.
- Runs with basic PostgreSQL configuration.

## Getting Started 🚀

### 1. Run PostgreSQL in Docker 🐳

Run PostgreSQL container with:

```bash
docker run --name student-db1 -p 5432:5432 -d -e POSTGRES_PASSWORD=postgres -e POSTGRES_USER=postgres -e POSTGRES_DB=student postgres
```

### 2. Configure Application ⚙️

In `application.properties`:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/student
spring.datasource.username=postgres
spring.datasource.password=postgres
spring.jpa.hibernate.ddl-auto=create-drop
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.properties.hibernate.format_sql=true
```

### 3. Build and Run 🏃‍♂️

1. Clone/download the project.
2. Build with Maven:

   ```bash
   mvn clean install
   ```

3. Run the app:

   ```bash
   mvn spring-boot:run
   ```

The app will save a sample student to the database.

### 4. Check Database 🔍

Connect to PostgreSQL and verify the data:

```bash
psql -U postgres -d student
```

## Dependencies 📦

- `spring-boot-starter-data-jpa`
- `spring-boot-starter-web`
- `postgresql` (JDBC driver)

