# End-to-End-DevOps-Deployment-Pipeline
A comprehensive DevOps project demonstrating end-to-end deployment of a React application on AWS EC2 using modern DevOps practices including CI/CD pipelines, containerization, reverse proxy configuration, and security hardening.
# 🚀 DevOps Engineer Challenge - React App Deployment

![fabb3181-76e5-4b1b-a21c-8c10d557b3f0](https://github.com/user-attachments/assets/de5f3dd7-28c8-4dc6-a0a4-540fa1031edc)
[Israr_A_Khan_DevOps Engineer Challenge.pdf](https://github.com/user-attachments/files/23849937/Israr_A_Khan_DevOps.Engineer.Challenge.pdf)


![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![Deployment](https://img.shields.io/badge/deployment-active-success)
![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Docker](https://img.shields.io/badge/docker-ready-blue)
![Jenkins](https://img.shields.io/badge/Jenkins-CI%2FCD-red)

A comprehensive DevOps project demonstrating end-to-end deployment of a React application on AWS EC2 using modern DevOps practices including CI/CD pipelines, containerization, reverse proxy configuration, and security hardening.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation & Setup](#installation--setup)
  - [Part 1: User Management](#part-1-user-management)
  - [Part 2: React App Deployment](#part-2-react-app-deployment)
  - [Part 3: Nginx Configuration](#part-3-nginx-configuration)
  - [Part 4: Jenkins CI/CD Pipeline](#part-4-jenkins-cicd-pipeline)
  - [Part 5: Docker Containerization](#part-5-docker-containerization)
- [Project Structure](#project-structure)
- [CI/CD Pipeline](#cicd-pipeline)
- [Security](#security)
- [Monitoring & Logs](#monitoring--logs)
- [Troubleshooting](#troubleshooting)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## 🎯 Overview

This project showcases a complete DevOps workflow for deploying a React-based internationalization (i18n) chat application. The implementation covers:

- **Linux System Administration**: User management, permissions, and security configurations
- **Application Build & Deployment**: Node.js/React build process with PM2 process management
- **Web Server Configuration**: Nginx as reverse proxy for production deployment
- **CI/CD Automation**: Jenkins pipeline for automated builds and deployments
- **Containerization**: Docker and Docker Compose for portable deployments
- **Cloud Infrastructure**: AWS EC2 instance setup and configuration
- **Security Hardening**: UFW firewall configuration and port management

---

## 🛠️ Tech Stack

### **Cloud & Infrastructure**
![AWS](https://img.shields.io/badge/AWS-EC2-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)

### **Frontend & Build Tools**
![React](https://img.shields.io/badge/React-18.x-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-5.0-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-18.20.8-339933?style=for-the-badge&logo=node.js&logoColor=white)
![npm](https://img.shields.io/badge/npm-10.8.2-CB3837?style=for-the-badge&logo=npm&logoColor=white)

### **DevOps & Automation**
![Jenkins](https://img.shields.io/badge/Jenkins-2.528.2-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-latest-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Docker Compose](https://img.shields.io/badge/Docker_Compose-3.8-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-latest-009639?style=for-the-badge&logo=nginx&logoColor=white)

### **Process Management & Security**
![PM2](https://img.shields.io/badge/PM2-latest-2B037A?style=for-the-badge&logo=pm2&logoColor=white)
![UFW](https://img.shields.io/badge/UFW-Firewall-orange?style=for-the-badge)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

### **Cloud Services**
![AWS S3](https://img.shields.io/badge/AWS_S3-Storage-569A31?style=for-the-badge&logo=amazon-s3&logoColor=white)

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                        AWS EC2 Instance                      │
│                      (Ubuntu 22.04 LTS)                      │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  ┌──────────────┐         ┌──────────────┐                  │
│  │   Nginx      │────────▶│  React App   │                  │
│  │  (Port 80)   │         │   (PM2)      │                  │
│  │ Reverse Proxy│         │              │                  │
│  └──────────────┘         └──────────────┘                  │
│         │                                                     │
│         │                 ┌──────────────┐                  │
│         │                 │  Docker      │                  │
│         └────────────────▶│  Container   │                  │
│                           │  (Port 3000) │                  │
│                           └──────────────┘                  │
│                                                               │
│  ┌──────────────────────────────────────┐                   │
│  │        Jenkins CI/CD Pipeline        │                   │
│  │  - Build Automation                  │                   │
│  │  - Deployment Automation             │                   │
│  │  - S3 Upload Integration             │                   │
│  └──────────────────────────────────────┘                   │
│                                                               │
│  ┌──────────────────────────────────────┐                   │
│  │         UFW Firewall                 │                   │
│  │  Allowed: 22, 80, 443, 3000, 8080   │                   │
│  └──────────────────────────────────────┘                   │
└─────────────────────────────────────────────────────────────┘
                          │
                          ▼
                   ┌─────────────┐
                   │   AWS S3    │
                   │   Bucket    │
                   └─────────────┘
```

---

## ✨ Features

- ✅ **Automated CI/CD Pipeline**: Jenkins pipeline for continuous integration and deployment
- ✅ **Containerized Deployment**: Docker and Docker Compose for consistent environments
- ✅ **Process Management**: PM2 for zero-downtime deployments and auto-restart
- ✅ **Reverse Proxy Configuration**: Nginx for production-grade serving
- ✅ **Security Hardening**: UFW firewall with restricted port access
- ✅ **Cloud Storage Integration**: AWS S3 for artifact storage
- ✅ **Multi-language Support**: i18n implementation for internationalization
- ✅ **Build Optimization**: Vite for fast builds and HMR

---

## 📦 Prerequisites

Before you begin, ensure you have:

- AWS account with EC2 access
- Ubuntu 22.04 LTS EC2 instance (t2.micro or higher)
- SSH key pair for EC2 access
- Basic knowledge of Linux commands
- Git installed
- Domain name (optional, for production)

---

## 🚀 Installation & Setup

### Part 1: User Management

#### 1.1 Create Sudo User

```bash
# Switch to root or use sudo
sudo su

# Create new user 'DevOps'
adduser DevOps

# Add user to sudo group
usermod -aG sudo DevOps

# Verify user creation
id DevOps

# Switch to DevOps user
su - DevOps
```

---

### Part 2: React App Deployment

#### 2.1 Install Node.js and npm

```bash
# Update system packages
sudo apt update && sudo apt upgrade -y

# Install Node.js (v18.x)
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs

# Verify installation
node --version  # v18.20.8
npm --version   # 10.8.2
```

#### 2.2 Clone Repository

```bash
# Create checkout directory
sudo mkdir -p /opt/checkout
cd /opt/checkout

# Clone the project
sudo git clone https://github.com/riyanuddin17/DevOps-Challenge.git
cd DevOps-Challenge

# List project files
ls -la
```

#### 2.3 Build React Application

```bash
# Install dependencies
sudo npm install

# Build the project
sudo npm run build

# Verify dist folder creation
ls -la dist/
```

**Build Output:**
- `dist/index.html` (0.48 kB)
- `dist/assets/index-xzd4obSc.css` (0.59 kB)
- `dist/assets/index-vNmJavtl.js` (230.53 kB)

#### 2.4 Deploy to Production Directory

```bash
# Create deployment directory
sudo mkdir -p /opt/deployment/react
sudo chown -R DevOps:DevOps /opt/deployment

# Copy dist files to deployment location
sudo cp -r /opt/checkout/DevOps-Challenge/dist/* /opt/deployment/react/

# Verify deployment
ls -la /opt/deployment/react/
```

#### 2.5 Deploy with PM2

```bash
# Install PM2 globally
sudo npm install -g pm2

# Navigate to deployment directory
cd /opt/deployment/react

# Start application with PM2
sudo pm2 serve /opt/deployment/react 8080 --name "DevOps-Challenge"

# Save PM2 configuration
sudo pm2 save

# Configure PM2 to start on boot
sudo pm2 startup systemd

# Verify PM2 status
sudo pm2 status
```

---

### Part 3: Nginx Configuration

#### 3.1 Install and Configure Nginx

```bash
# Install Nginx
sudo apt install nginx -y

# Start and enable Nginx
sudo systemctl start nginx
sudo systemctl enable nginx

# Verify Nginx status
sudo systemctl status nginx
```

#### 3.2 Configure Nginx as Reverse Proxy

```bash
# Create Nginx configuration
sudo nano /etc/nginx/sites-available/react-app

# Add the following configuration:
```

**Nginx Configuration:**

```nginx
server {
    listen 80;
    server_name your_domain_or_ip;

    root /opt/deployment/react;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }

    # Optional: Proxy to PM2 if needed
    # location / {
    #     proxy_pass http://localhost:8080;
    #     proxy_http_version 1.1;
    #     proxy_set_header Upgrade $http_upgrade;
    #     proxy_set_header Connection 'upgrade';
    #     proxy_set_header Host $host;
    #     proxy_cache_bypass $http_upgrade;
    # }

    error_page 404 /404.html;
    error_page 500 502 503 504 /50x.html;
}
```

```bash
# Enable the site
sudo ln -s /etc/nginx/sites-available/react-app /etc/nginx/sites-enabled/

# Test Nginx configuration
sudo nginx -t

# Reload Nginx
sudo systemctl reload nginx
```

#### 3.3 Configure Firewall (UFW)

```bash
# Install UFW (if not installed)
sudo apt install ufw -y

# Set default policies
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Allow required ports
sudo ufw allow 22/tcp    # SSH
sudo ufw allow 80/tcp    # HTTP
sudo ufw allow 443/tcp   # HTTPS
sudo ufw allow 3000/tcp  # Docker container
sudo ufw allow 8080/tcp  # Jenkins

# Enable firewall
sudo ufw enable

# Verify firewall status
sudo ufw status verbose
```

---

### Part 4: Jenkins CI/CD Pipeline

#### 4.1 Install Java (Jenkins Requirement)

```bash
# Install OpenJDK 11
sudo apt update
sudo apt install openjdk-11-jdk -y

# Verify Java installation
java --version
```

#### 4.2 Install Jenkins

```bash
# Add Jenkins repository key
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

# Add Jenkins repository
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

# Update package list and install Jenkins
sudo apt update
sudo apt install jenkins -y

# Start and enable Jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins

# Check Jenkins status
sudo systemctl status jenkins
```

#### 4.3 Access Jenkins

```bash
# Get initial admin password
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

**Access Jenkins:**
- URL: `http://<your-ec2-ip>:8080`
- Paste the initial admin password
- Install suggested plugins
- Create admin user

#### 4.4 Configure Jenkins for PM2 and Git

```bash
# Grant Jenkins sudo access for specific commands
sudo visudo

# Add the following line at the end:
jenkins ALL=(ALL) NOPASSWD: /usr/bin/pm2, /usr/bin/git, /usr/bin/npm
```

#### 4.5 Install Jenkins Plugins

1. Navigate to **Manage Jenkins** → **Manage Plugins**
2. Install the following plugins:
   - **Amazon Web Services SDK :: S3** (for S3 uploads)
   - **Git Plugin** (for repository integration)
   - **Pipeline Plugin** (for pipeline jobs)
   - **NodeJS Plugin** (for Node.js builds)

#### 4.6 Create Jenkins Pipeline

**Jenkinsfile:**

```groovy
pipeline {
    agent any
    
    environment {
        APP_DIR = '/opt/deployment/react'
        CHECKOUT_DIR = '/opt/checkout/DevOps-Challenge'
    }
    
    stages {
        stage('Stop Running Deployment') {
            steps {
                script {
                    sh 'sudo pm2 delete DevOps-Challenge || true'
                }
            }
        }
        
        stage('Pull Fresh Code') {
            steps {
                script {
                    sh '''
                        cd ${CHECKOUT_DIR}
                        sudo git pull origin main
                    '''
                }
            }
        }
        
        stage('Build Application') {
            steps {
                script {
                    sh '''
                        cd ${CHECKOUT_DIR}
                        sudo npm install
                        sudo npm run build
                    '''
                }
            }
        }
        
        stage('Deploy to Production') {
            steps {
                script {
                    sh '''
                        sudo cp -r ${CHECKOUT_DIR}/dist/* ${APP_DIR}/
                        cd ${APP_DIR}
                        sudo pm2 serve ${APP_DIR} 8080 --name "DevOps-Challenge"
                        sudo pm2 save
                    '''
                }
            }
        }
        
        stage('Upload to S3') {
            steps {
                script {
                    sh '''
                        aws s3 sync ${APP_DIR} s3://your-bucket-name/deployments/$(date +%Y%m%d-%H%M%S)/ \
                        --region your-region
                    '''
                }
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs for details.'
        }
    }
}
```

**Create Pipeline Job:**

1. Click **New Item** → Enter name → Select **Pipeline**
2. Under **Pipeline** section:
   - Definition: **Pipeline script from SCM**
   - SCM: **Git**
   - Repository URL: `https://github.com/riyanuddin17/DevOps-Challenge.git`
   - Branch: `*/main`
   - Script Path: `Jenkinsfile`
3. Save and **Build Now**

---

### Part 5: Docker Containerization

#### 5.1 Install Docker

```bash
# Add Docker repository
sudo apt install -y ca-certificates curl gnupg lsb-release

# Add Docker's official GPG key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
  sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Set up stable repository
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] \
  https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install Docker Engine
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y

# Verify Docker installation
docker --version
docker compose version

# Add user to docker group
sudo usermod -aG docker $USER
newgrp docker
```

#### 5.2 Create Dockerfile

```bash
cd /opt/checkout/DevOps-Challenge
nano Dockerfile
```

**Dockerfile:**

```dockerfile
# Use official Nginx Alpine image
FROM nginx:alpine

# Remove default Nginx configuration
RUN rm /etc/nginx/conf.d/default.conf

# Copy custom Nginx configuration
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copy built React app (dist folder)
COPY dist/ /usr/share/nginx/html/

# Expose port 3000
EXPOSE 3000

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
```

#### 5.3 Create Nginx Configuration for Docker

```bash
nano nginx.conf
```

**nginx.conf:**

```nginx
server {
    listen 3000;
    server_name _;

    root /usr/share/nginx/html;
    index index.html index.htm;

    location / {
        try_files $uri /index.html;
    }

    error_page 404 /index.html;
}
```

#### 5.4 Build Docker Image

```bash
# Build Docker image
sudo docker build -t chat-app:latest .

# Verify image creation
sudo docker images
```

#### 5.5 Create Docker Compose File

```bash
nano docker-compose.yml
```

**docker-compose.yml:**

```yaml
version: '3.8'

services:
  chat-app:
    image: chat-app:latest
    container_name: chat-app-container
    ports:
      - "3000:3000"
    restart: always
```

#### 5.6 Deploy with Docker Compose

```bash
# Start container
sudo docker-compose up -d

# Verify container is running
sudo docker ps

# View container logs
sudo docker logs chat-app-container

# Stop container (when needed)
sudo docker-compose down
```

---

## 📁 Project Structure

```
/opt/checkout/DevOps-Challenge/
├── Acornfile
├── README.md
├── index.html
├── package.json
├── package-lock.json
├── vite.config.js
├── yarn.lock
├── Dockerfile                    # Docker configuration
├── docker-compose.yml            # Docker Compose file
├── nginx.conf                    # Nginx config for Docker
├── Jenkinsfile                   # CI/CD pipeline definition
├── public/                       # Public assets
│   └── locales/                  # i18n translation files
├── src/                          # React source code
│   ├── components/
│   ├── App.jsx
│   └── main.jsx
└── dist/                         # Production build output
    ├── index.html
    ├── assets/
    │   ├── index-xzd4obSc.css
    │   └── index-vNmJavtl.js
    └── locales/

/opt/deployment/react/
└── (Production deployment files)
```

---

## 🔄 CI/CD Pipeline

The Jenkins pipeline automates the following workflow:

1. **Stop Running Deployment**: Gracefully stops the existing PM2 process
2. **Pull Fresh Code**: Fetches latest code from GitHub repository
3. **Build Application**: Installs dependencies and builds production assets
4. **Deploy to Production**: Copies build artifacts and starts PM2 process
5. **Upload to S3**: Archives deployment to AWS S3 for backup and versioning

**Pipeline Status:** ✅ **SUCCESS**

---

## 🔒 Security

### Firewall Configuration

| Port | Service | Access |
|------|---------|--------|
| 22 | SSH | Restricted to admin IPs |
| 80 | HTTP | Public |
| 443 | HTTPS | Public |
| 3000 | Docker App | Public |
| 8080 | Jenkins | Restricted |

### Security Best Practices Implemented

- ✅ Dedicated sudo user with limited privileges
- ✅ UFW firewall with default deny policy
- ✅ Jenkins access restricted to specific commands via sudoers
- ✅ SSH key-based authentication
- ✅ Regular security updates (`apt update && apt upgrade`)
- ✅ Nginx security headers (can be enhanced)

---

## 📊 Monitoring & Logs

### PM2 Monitoring

```bash
# View PM2 status
pm2 status

# View application logs
pm2 logs DevOps-Challenge

# Monitor in real-time
pm2 monit

# View PM2 dashboard
pm2 plus
```

### Docker Monitoring

```bash
# View container logs
docker logs -f chat-app-container

# Monitor container stats
docker stats chat-app-container

# Inspect container
docker inspect chat-app-container
```

### Nginx Logs

```bash
# Access logs
sudo tail -f /var/log/nginx/access.log

# Error logs
sudo tail -f /var/log/nginx/error.log
```

### Jenkins Logs

```bash
# Jenkins system logs
sudo journalctl -u jenkins -f

# Job-specific logs
# Available in Jenkins UI → Job → Console Output
```

---

## 🐛 Troubleshooting

### Common Issues and Solutions

#### Issue 1: PM2 Process Not Starting

```bash
# Check PM2 logs
pm2 logs

# Delete and restart process
pm2 delete DevOps-Challenge
pm2 serve /opt/deployment/react 8080 --name "DevOps-Challenge"
pm2 save
```

#### Issue 2: Nginx 502 Bad Gateway

```bash
# Check Nginx error logs
sudo tail -f /var/log/nginx/error.log

# Verify backend service is running
pm2 status
sudo netstat -tulpn | grep :8080

# Restart Nginx
sudo systemctl restart nginx
```

#### Issue 3: Docker Container Not Accessible

```bash
# Check container status
docker ps -a

# View container logs
docker logs chat-app-container

# Restart container
docker-compose restart

# Check firewall
sudo ufw status
```

#### Issue 4: Jenkins Build Failures

```bash
# Check Jenkins service
sudo systemctl status jenkins

# Verify Node.js installation
node --version

# Check Jenkins permissions
ls -la /var/lib/jenkins/workspace/

# Review sudoers configuration
sudo visudo
```

---

## 🚀 Future Enhancements

- [ ] Implement SSL/TLS with Let's Encrypt
- [ ] Add Prometheus + Grafana monitoring
- [ ] Implement automated backups to S3
- [ ] Add integration tests in CI/CD pipeline
- [ ] Implement blue-green deployment strategy
- [ ] Add container orchestration with Kubernetes
- [ ] Implement centralized logging with ELK stack
- [ ] Add automated security scanning (Trivy, SonarQube)
- [ ] Implement infrastructure as code with Terraform
- [ ] Add CDN integration (CloudFront)
- [ ] Implement database integration
- [ ] Add API gateway and microservices architecture

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📞 Contact

**Israr Ahemad Khan**

- 📧 Email: ik427094@gmail.com
- 📱 Mobile: +91-8888337050
- 💼 LinkedIn: [linkedin.com/in/israr-khan](https://linkedin.com/in/israr-khan)
- 🐙 GitHub: [@israr-khan](https://github.com/israr-khan)

---

## 🙏 Acknowledgments

- Original React app repository: https://github.com/israrakhan/DevOps-Challenge.git
- RoadsideCoder YouTube Channel for i18n tutorial
- AWS for cloud infrastructure
- Open-source community for amazing tools

---

## 📈 Project Stats

![GitHub last commit](https://img.shields.io/github/last-commit/your-username/DevOps-Challenge)
![GitHub repo size](https://img.shields.io/github/repo-size/your-username/DevOps-Challenge)
![GitHub contributors](https://img.shields.io/github/contributors/your-username/DevOps-Challenge)
![GitHub stars](https://img.shields.io/github/stars/your-username/DevOps-Challenge?style=social)

---

<div align="center">

**⭐ Star this repository if you found it helpful!**

Made with ❤️ by Israr Ahemad Khan

</div>
