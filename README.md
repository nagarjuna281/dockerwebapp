# CI/CD Pipeline Project with Jenkins, Docker, and SonarQube

## 📌 Project Overview
This project demonstrates a complete CI/CD pipeline setup on an AWS EC2 instance (t2.large).  
The pipeline automates code fetching, quality analysis, building, containerization, security scanning, and deployment.

---

## ⚙️ Infrastructure
- **AWS EC2 Instance:** t2.large
- **Operating System:** Amazon Linux 2

---

## 🔧 Jenkins Setup
Installed the following plugins:
- Docker Pipeline
- Pipeline Stage View
- NodeJS
- Eclipse Temurin Installer
- SonarQube Scanner

---

## 🚀 Pipeline Stages
1. **Workspace Cleanup**  
   - `cleanws()` ensures a fresh environment for each build.

2. **Source Code Management**  
   - Fetching code directly from GitHub repository.

3. **Code Quality Analysis**  
   - Integrated **SonarQube** for static code analysis.

4. **Build Stage**  
   - Compiled and packaged application using **Maven**.

5. **Docker Image Build**  
   - Created Docker images for both **App** and **Database** using separate Dockerfiles.

6. **Security Scan**  
   - Scanned both images with **Trivy** to detect vulnerabilities.

7. **Push to DockerHub**  
   - Successfully pushed app and db images to DockerHub registry.

8. **Deployment**  
   - Deployed using **Docker Compose**.  
   - Application container depends on the database container.  
   - Verified application accessibility after deployment.

---

## ✅ Outcomes
- Automated CI/CD pipeline from source to deployment.
- Improved code quality and security with SonarQube + Trivy.
- Containerized application with dependency management.
- Deployment simplified using Docker Compose.

---

## 🛠️ Tech Stack
- **AWS EC2**
- **Jenkins**
- **SonarQube**
- **Maven**
- **Docker & Docker Compose**
- **Trivy**
- **GitHub**

---

## 📚 Learnings
- End-to-end CI/CD automation
- Integration of security and quality checks in pipelines
- Containerization best practices
- Cloud-based deployment using AWS

---

## 🔗 Future Enhancements
- Add Kubernetes deployment for scalability
- Integrate monitoring with Prometheus/Grafana
- Automate infrastructure provisioning with Terraform
