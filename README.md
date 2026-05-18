# DevOps CI/CD Project

## 🎯 Objective
Automate website deployment using Jenkins, GitHub, and AWS EC2.

## 🛠️ Tools & Technologies
- Git & GitHub
- Jenkins (CI/CD)
- AWS EC2, S3, VPC, IAM
- Apache Web Server

## 📁 Project Structure
devops-web-project/
├── src/           → Website source files
├── Jenkinsfile    → CI/CD pipeline definition
└── README.md      → Project documentation

## 🔄 CI/CD Pipeline Flow
GitHub Push → Jenkins Trigger → Build → Test → Deploy to EC2

## 🌐 Deployment
Application runs on AWS EC2 via Apache server.
Automated using Jenkins pipeline on every code push.