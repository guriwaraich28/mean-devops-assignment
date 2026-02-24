# 🚀 MEAN Stack DevOps CI/CD Deployment

A complete end-to-end DevOps project that demonstrates how to **containerize, automate, and deploy** a full-stack **MEAN (MongoDB, Express, Angular, Node.js)** application using **Docker, Jenkins CI/CD, Nginx, and AWS EC2**.

This project was built as part of a DevOps internship assignment.

---

# 📌 Project Highlights

✔ Containerized full-stack MEAN application  
✔ Docker Compose multi-container deployment  
✔ Jenkins CI/CD pipeline (build → push → deploy)  
✔ DockerHub image registry integration  
✔ AWS EC2 production deployment  
✔ Nginx reverse proxy on port 80  
✔ Automatic redeployment on code changes  

---

# 🏗️ Architecture Diagram

Developer → GitHub → Jenkins → DockerHub → AWS EC2 → Docker Compose → Nginx → Browser

---

# ⚙️ Tech Stack

## 🖥️ Application
- Angular 15 (Frontend)
- Node.js + Express (Backend API)
- MongoDB (Database)

## 🛠️ DevOps & Cloud
- Docker
- Docker Compose (v2)
- Jenkins CI/CD
- AWS EC2 (Ubuntu)
- Nginx Reverse Proxy
- DockerHub Registry

---

# 📂 Project Structure


mean-devops-assignment/
│
├── backend/
│ ├── Dockerfile
│ ├── package.json
│ └── Node.js Express API
│
├── frontend/
│ ├── Dockerfile
│ ├── angular.json
│ └── Angular App
│
├── nginx.conf
├── docker-compose.yml
└── Jenkinsfile


---

# 🐳 Docker Images

| Service | Image |
|---|---|
| Backend | `guriwaraich/mean-backend:latest` |
| Frontend | `guriwaraich/mean-frontend:latest` |
| MongoDB | `mongo:latest` |
| Nginx | `nginx:alpine` |

---

# 🔁 Jenkins CI/CD Pipeline

## Pipeline Flow

When code is pushed to GitHub:

### 1️⃣ Clone Repository
Jenkins pulls latest source code.

### 2️⃣ Build Backend Image
docker build -t guriwaraich/mean-backend ./backend

### 3️⃣ Push Backend Image
docker push guriwaraich/mean-backend

### 4️⃣ Build Frontend Image
docker build -t guriwaraich/mean-frontend ./frontend

### 5️⃣ Push Frontend Image
docker push guriwaraich/mean-frontend

### 6️⃣ Deploy to AWS EC2 via SSH
docker compose pull
docker compose up -d

Containers restart automatically with latest images.

---

### 🌐 Application Deployment

The entire application is exposed through Nginx reverse proxy.

Access URL
http://54.159.49.45/

Runs on port 80.

---

### 🎯 DevOps Concepts Demonstrated

CI/CD Automation

Containerization with Docker

Multi-container deployment

Reverse proxy configuration

Secure credential management

Cloud deployment on AWS

Continuous delivery pipeline

---

### 👨‍💻 Author

Gurwinder Singh
DevOps & Cloud Enthusiast

### 🏁 Final Status

✅ Application Dockerized
✅ CI/CD Pipeline Implemented
✅ Successfully Deployed on AWS
✅ Production-style Architecture