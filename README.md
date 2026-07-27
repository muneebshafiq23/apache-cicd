````markdown
# Automated CI/CD Pipeline for Game Website using GitHub Actions, Docker & AWS EC2


## 📌 Project Overview

This project demonstrates a complete **CI/CD (Continuous Integration and Continuous Deployment)** pipeline for deploying a premium Apache-based HTML game website.

Whenever code is pushed to the **main** branch, GitHub Actions automatically:

1. Builds a Docker image.
2. Pushes the image to Docker Hub.
3. Connects to an AWS EC2 instance via SSH.
4. Pulls the latest Docker image.
5. Replaces the old container.
6. Launches the updated website automatically.

The entire deployment process is fully automated.

---

# 🏗️ Architecture

```
Developer
    │
    ▼
Git Push
    │
    ▼
GitHub Repository
    │
    ▼
GitHub Actions
    │
    ├── Checkout Source Code
    ├── Build Docker Image
    ├── Push Image to Docker Hub
    └── SSH into AWS EC2
                │
                ▼
         Pull Latest Image
                │
                ▼
       Stop Old Container
                │
                ▼
      Remove Old Container
                │
                ▼
       Run New Container
                │
                ▼
      Apache Web Server
                │
                ▼
         Live Game Website
```

---

# 🛠️ Technologies Used

- HTML5
- Apache2
- Docker
- Docker Hub
- Git
- GitHub
- GitHub Actions
- AWS EC2
- Ubuntu Linux
- SSH

---

# 📂 Project Structure

```
.
├── index.html
├── Dockerfile
├── README.md
└── .github
    └── workflows
        └── deploy.yml
```

---

# ⚙️ GitHub Actions Workflow

The pipeline automatically performs the following steps:

- Checkout Repository
- Login to Docker Hub
- Build Docker Image
- Push Image to Docker Hub
- SSH into AWS EC2
- Pull Latest Docker Image
- Stop Previous Container
- Remove Previous Container
- Deploy New Container

---

# 🔐 GitHub Secrets

The following repository secrets are required:

| Secret | Description |
|----------|-------------|
| DOCKER_USERNAME | Docker Hub username |
| DOCKER_PASSWORD | Docker Hub Access Token |
| EC2_HOST | Public IP of EC2 instance |
| EC2_USERNAME | EC2 username (ubuntu) |
| EC2_SSH_KEY | Private SSH key (.pem file content) |

---

# ☁️ AWS EC2 Configuration

The EC2 instance should have:

- Ubuntu Server
- Docker Installed
- SSH Enabled
- Port 80 Open
- Port 22 Open

Security Group:

| Port | Purpose |
|-------|----------|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS (Optional) |

---

# 🚀 Deployment Workflow

```
Code Change
      │
      ▼
git add .
      │
git commit
      │
git push origin main
      │
      ▼
GitHub Actions Triggered
      │
      ▼
Docker Build
      │
      ▼
Docker Push
      │
      ▼
Deploy to EC2
      │
      ▼
Website Updated Automatically
```

---

# ▶️ Running Locally

Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

Navigate into the project

```bash
cd YOUR_REPOSITORY
```

Build Docker image

```bash
docker build -t game-website .
```

Run the container

```bash
docker run -d -p 80:80 game-website
```

Open:

```
http://localhost
```


---

# 📈 CI/CD Pipeline Benefits

- Fully Automated Deployment
- Zero Manual Deployment
- Faster Release Cycle
- Reproducible Docker Images
- Cloud Deployment
- Infrastructure Ready
- Scalable Architecture
- Easy Rollback
- Consistent Deployment Process

---

# 🔮 Future Improvements

- HTTPS using Let's Encrypt
- Custom Domain
- Nginx Reverse Proxy
- Multi-stage Docker Build
- Docker Compose
- Kubernetes Deployment
- AWS ECS Deployment
- Terraform Infrastructure
- Monitoring with Prometheus & Grafana
- GitHub Actions Testing Stage

---

# 👨‍💻 Author

**Muhammad Muneeb**

Cloud & DevOps Engineer

GitHub:
https://github.com/muneebshafiq23

LinkedIn:
https://www.linkedin.com/in/muneebshafiq23

---

# ⭐ If you found this project useful

Please consider giving this repository a ⭐ on GitHub.
````
