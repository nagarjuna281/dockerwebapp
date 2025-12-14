
# DevOps CI/CD Pipeline Project 🚀

## 📌 Overview
This project demonstrates a complete CI/CD pipeline setup on an **AWS EC2 server** using **Jenkins**.  
The application code was **taken from an existing GitHub repository**, then integrated into this pipeline for automated build, test, and deployment.

The pipeline automates the following:
- Pulling code from **GitHub**
- Performing **code quality analysis** with **SonarQube**
- Building the application with **Maven**
- Creating **Docker images** for both the application and database
- Running **Trivy security scans** on images
- Pushing images to **DockerHub**
- Deploying services with **Docker Compose**, where the app depends on the database

---

## ⚙️ Architecture Flow
1. **EC2 Server Setup**  
   - Jenkins, Docker, SonarQube, and Trivy installed and configured.

2. **Jenkins Pipeline**  
   - **Stage 1:** Checkout code from GitHub  
   - **Stage 2:** Code quality analysis via SonarQube Scanner  
   - **Stage 3:** Build application using Maven  
   - **Stage 4:** Build Docker images (App + DB)  
   - **Stage 5:** Scan images with Trivy  
   - **Stage 6:** Push images to DockerHub  
   - **Stage 7:** Deploy using Docker Compose (App depends on DB)

3. **Docker Compose Deployment**  
   - `app` service configured with `depends_on` for `db` service  
   - Ensures DB container starts before the application container

---

## 🛠️ Jenkins Plugins Installed
- **Docker Pipeline** – for building and publishing Docker images  
- **Eclipse Temurin Installer** – installs Java (Temurin JDK) for Maven builds  
- **SonarQube Scanner** – integrates SonarQube analysis into pipeline  
- **Pipeline Stage View** – provides visual representation of pipeline stages  
- **NodeJS** – manages Node.js installations if required by the project  

---

## 🚀 Deployment Instructions
1. **Clone  Repository**
   ```bash
   git clone <repo-url>
   cd <project-folder>
   ```

2. **Configure Jenkins Pipeline**
   - Add GitHub repo in Jenkins pipeline configuration
   - Set SonarQube server details in Jenkins global configuration
   - Add DockerHub credentials in Jenkins

3. **Run Pipeline**
   - Trigger build → Jenkins executes all stages automatically

4. **Deploy with Docker Compose**
   ```bash
   docker-compose up -d
   ```

---

## 🔒 Security
- **Trivy** scans both app and db images for vulnerabilities before pushing to DockerHub.  
- Ensures secure and compliant container images.

---

## ✅ Outcome
- Fully automated CI/CD pipeline from **code commit → quality check → build → security scan → deployment**.  
- Application and database run as containers orchestrated by Docker Compose.

---

## 📖 Notes
- Ensure EC2 instance has sufficient resources (CPU/RAM) for Jenkins, SonarQube, and Docker.  
- SonarQube requires Java; Eclipse Temurin plugin ensures compatibility.  
- DockerHub credentials must be securely stored in Jenkins credentials manager.

