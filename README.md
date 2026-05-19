# 🚀 NexTask — Smart Productivity Hub

A full-featured productivity web app built as a DevOps CI/CD project.
Automatically deployed using **Jenkins + GitHub + AWS EC2**.

---

## 🌐 Live Features

| Feature | Description |
|---|---|
| 📊 Dashboard | Live stats, activity chart, task progress |
| ✅ Task Manager | Add, filter, prioritize & complete tasks |
| 🍅 Pomodoro Timer | 25/5 focus-break timer with session tracking |
| 📝 Notes | Color-coded sticky notes, persistent storage |
| 🧮 Calculator | Full calculator with keyboard support |
| 🌤️ Weather | 7-day forecast for Ludhiana |

---

## 🛠️ Tech Stack

- **Frontend:** HTML5, CSS3, Vanilla JavaScript
- **CI/CD:** Jenkins (Declarative Pipeline)
- **Version Control:** Git & GitHub
- **Cloud:** AWS EC2, S3, VPC, IAM
- **Web Server:** Apache2

---

## 📁 Project Structure

```
devops-web-project/
├── src/
│   └── index.html       ← Full web application
├── Jenkinsfile          ← CI/CD pipeline
└── README.md            ← This file
```

---

## 🔄 CI/CD Pipeline Stages

```
GitHub Push
    ↓
Jenkins Trigger (Webhook)
    ↓
Stage 1: Clone Repository
    ↓
Stage 2: Verify Files
    ↓
Stage 3: Test (file existence checks)
    ↓
Stage 4: Deploy → /var/www/html/
    ↓
Stage 5: Verify Deployment
    ↓
✅ Live on EC2
```

---

## 🚀 Setup Instructions

### 1. Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/devops-web-project.git
cd devops-web-project
```

### 2. Run locally
```bash
# Just open in browser
open src/index.html
```

### 3. Deploy via Jenkins
- Connect this repo in Jenkins → New Pipeline
- Set branch to `main`
- Click **Build Now**

---

## 🌿 Git Branching Strategy

```
main       ← production-ready code
  └── dev  ← development branch
        └── feature/xyz  ← individual features
```

---

## ☁️ AWS Infrastructure

- **EC2:** Ubuntu instance running Apache + Jenkins
- **VPC:** Custom VPC with public/private subnets
- **IAM:** Least-privilege user for Jenkins deployments
- **S3:** Artifact storage and backup

---

## 👨‍💻 Author

Made as part of DevOps coursework — CI/CD pipeline project.
