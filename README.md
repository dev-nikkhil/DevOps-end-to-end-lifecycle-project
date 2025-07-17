# Project Name: DevOps-end-to-end-lifecycle-project

## 📄 Project Overview
This project demonstrates the implementation of a complete DevOps lifecycle, transforming a monolithic architecture into a modern CI/CD pipeline using Jenkins, Docker, Kubernetes, and AWS with Terraform. The goal is to automate deployment, and operations of containerized applications.

---

## 🏗️ Architecture Diagram

![Project-Architecture (1)](https://github.com/user-attachments/assets/99d46034-d796-4516-a1ce-c05198ed3239)

---

## ✅ Tasks to Perform

### 🔹 **Version Control & Git Workflow**
- Use GitHub for source code management.
- Implement GitFlow suitable for a monolithic project.

### 🔹 **CI/CD Pipeline**
- Configure Jenkins for automation.
- Trigger AWS CodeBuild on master branch commits.
- Automate Docker image build and push to DockerHub on every commit.
- Write Jenkins pipeline as `Jenkinsfile`.

### 🔹 **Containerization**
- Create a Dockerfile to build the application container.
- Push the custom Docker image to DockerHub.

### 🔹 **Orchestration with Kubernetes**
- Deploy containerized applications on Kubernetes (AWS EC2).
- Use 2 replicas.
- Expose via NodePort `30008`.

### 🔹 **Infrastructure as Code (IaC)**
- Use Terraform to provision AWS resources.
- Separate resources for Jenkins, Docker, Kubernetes.

### 🔹 **Configuration Management**
- Install and configure:
  - Worker 1: Jenkins, Java
  - Worker 2: Docker, Kubernetes
  - Worker 3: Java, Docker, Kubernetes
  - Worker 4: Docker, Kubernetes

---

## ⚙️ Tech Stack
| Tool        | Purpose                  |
|-------------|---------------------------|
| **GitHub**  | Source Control             |
| **Jenkins** | CI/CD                      |
| **Docker**  | Containerization           |
| **Kubernetes** | Orchestration          |
| **Terraform** | Infrastructure as Code  |
| **AWS EC2** | Cloud Infrastructure       |

---
