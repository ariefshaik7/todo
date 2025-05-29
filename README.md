# 📝 Todo App - Spring Boot + Thymeleaf + MySQL

A simple and clean Todo List application built with **Java Spring Boot**, **MySQL**, **JPA**, **Thymeleaf**, and **Lombok**. Users can create, view, complete, and delete tasks from a beautiful web UI.

---

## 🚀 Features

- Add new tasks
- View all tasks
- Mark tasks as completed
- Delete tasks
- Persistent storage using MySQL
- Simple and responsive UI with Thymeleaf & Bootstrap

---

## ⚙️ Technologies Used

- Java 17+
- Spring Boot
- Spring MVC
- Spring Data JPA
- MySQL
- Thymeleaf
- Lombok
- Bootstrap 5
- Docker + Docker Compose

---

## 🧰 Requirements

- Java 17 or higher
- Maven
- MySQL Server (if not using Docker)
- Docker & Docker Compose (for containerized setup)
- An IDE (like IntelliJ IDEA, Eclipse, or VS Code)

---

## 🖥️ How to Run (Locally)

1. Clone the project:
   ```bash
   git clone https://github.com/your-username/todo-app.git
   cd todo-app
   ```

2. Create a MySQL database named `todo-app`.

3. Configure your `application.properties` or `.yml` with the correct database credentials.

4. Run the application:
   ```bash
   ./mvnw spring-boot:run
   ```

5. Visit the app at: [http://localhost:8080](http://localhost:8080)

---

## 🐳 How to Run with Docker

This project is Dockerized for easier setup and deployment.

### 📁 Files Included

- `Dockerfile` — Defines the Spring Boot app container.
- `docker-compose.yml` — Sets up the Spring Boot app and MySQL database as services.

### ▶️ Steps to Run

1. **Build and start the containers**:
   ```bash
   docker-compose up --build
   ```

2. **Access the app** in your browser:
   ```
   http://localhost:8080
   ```

3. **Stop the containers**:
   ```bash
   docker-compose down
   ```

### 🗃️ MySQL Configuration (Docker)

- **Service Name**: `mysql`
- **Username**: `root`
- **Password**: `password`
- **Database**: `todo-app`
- The database is automatically created via environment variables in the `docker-compose.yml`.

---

## 📂 Project Structure

```
todo-app/
│
├── src/                      # Source files
├── Dockerfile                # Docker image instructions
├── docker-compose.yml        # Docker Compose services
├── pom.xml                   # Maven dependencies
└── README.md
```

---
