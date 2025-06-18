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
- Jenkins (CI/CD)

---

## 🧰 Requirements

- Java 17 or higher  
- Maven  
- MySQL Server (if not using Docker)  
- Docker & Docker Compose  
- An IDE (like IntelliJ IDEA, Eclipse, or VS Code)  
- Jenkins (for automation and CI/CD)

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

## ⚙️ Jenkins Integration (CI/CD)

The project includes a `Jenkinsfile` to automate build and deployment using Docker Compose.

### 📜 Jenkinsfile Overview

\`\`\`groovy
pipeline {
    agent any

    stages {
        stage('Cloning the repository') {
            steps {
                git credentialsId: 'github-token', url: 'https://github.com/ariefshaik114/todo.git'
            }
        }
        stage('Build and run application using Docker Compose') {
            steps {
                sh 'docker compose up -d'
            }
        }
    }

    post {
        always {
            echo "Cleaning up containers..."
            sh 'docker-compose down'
        }
    }
}
\`\`\`

### 🛠 How It Works

- Jenkins pulls the source code from GitHub using a secure token.
- The app is built and deployed in containers using Docker Compose.
- After execution, it tears down containers to ensure a clean state.

---

## 📂 Project Structure

```
todo-app/
│
├── src/                      # Source files
├── Dockerfile                # Docker image instructions
├── docker-compose.yml        # Docker Compose services
├── Jenkinsfile               # Jenkins CI/CD pipeline
├── pom.xml                   # Maven dependencies
└── README.md
```

---
---

## 🔄 GitHub Actions CI/CD Pipeline

This project also includes a GitHub Actions workflow for CI/CD automation.

### 📁 Workflow Location

```bash
.github/workflows/ci-cd.yml
```

### 🚀 Workflow Features

- **On push to main branch**:
  - Checks out code
  - Builds and tests the application
  - Builds Docker images
---

## ☁️ Cloud Deployment (Azure & AWS)

This project can be deployed to both **Azure** and **AWS**, with secure network configurations.

### 🛠 Prerequisites

- Docker installed on VM/EC2 instance
- SSH access enabled
- Environment variables securely set
- Optional: Use of GitHub Secrets for deployment credentials

### 🔧 Deployment Process

- GitHub Actions or Jenkins triggers remote deployment scripts
- Docker Compose runs on cloud VM (Azure/AWS)
- Exposed only necessary ports via firewall/VPC rules

### 🌐 Access

- Once deployed, access the app via the public IP or domain of the Azure VM or AWS EC2 instance:
  ```
  http://<your-cloud-instance-ip>:8080
  ```

