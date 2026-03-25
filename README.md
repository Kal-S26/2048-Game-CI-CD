# 🎮 2048 Game CI/CD Deployment using AWS ECS (Fargate)

## 📌 Overview
This project demonstrates deploying a containerized 2048 web application using AWS ECS (Fargate) with a fully automated CI/CD pipeline.

The goal of this project is to simulate a real-world DevOps workflow where every code change triggers an automated build and deployment process.

---

## 🏗️ Architecture

User → Load Balancer → ECS (Fargate) → ECR  
                 ↑  
         CodePipeline (CI/CD) <img width="1357" height="540" alt="Build a CI:CD Pipeline for the 2048 Game" src="https://github.com/user-attachments/assets/e4182fbb-78d8-4d68-9b8e-c71f8563919e" />



---

## ⚙️ Tech Stack

- AWS ECS (Fargate)
- Amazon ECR
- AWS CodePipeline
- AWS CodeBuild
- Docker
- Amazon CloudWatch

---

## 🚀 CI/CD Workflow

1. Code pushed to GitHub repository
2. Pipeline triggered via AWS CodePipeline
3. Docker image built using CodeBuild
4. Image pushed to Amazon ECR
5. ECS service updated with new task definition
6. Application deployed automatically

---

## 📸 Project Proof (Screenshots)

- ECS service with running tasks<img width="1075" height="664" alt="ECS Service with running task" src="https://github.com/user-attachments/assets/a0828b2b-a03e-482d-a149-7d3d4a88646e" />

- CodePipeline successful execution<img width="1362" height="675" alt="CodePipeline successful execution" src="https://github.com/user-attachments/assets/f0364906-5b68-4a43-98c7-fc45bcb32b71" />

- ECR repository with image<img width="1075" height="534" alt="ECR repository with image" src="https://github.com/user-attachments/assets/74ef9725-477d-4e4b-921d-3b94445a5ed8" />

- Application UI (2048 game running)<img width="1362" height="760" alt="Application UI - 2048" src="https://github.com/user-attachments/assets/1ea5ece4-278c-4cfe-9baa-f78947566c85" />



---

## 🧠 Challenges & Fixes

### ❌ Issue: ECS Task Failed to Pull Image
- Error: Unable to pull from ECR
- Root Cause: Incorrect region (`us-easte-1` typo)

✅ Fix:
- Updated region to `us-east-1` in pipeline and configuration

---

### ❌ Issue: Deployment Rollback (Circuit Breaker)
- Cause: Tasks failed repeatedly during deployment

✅ Fix:
- Debugged ECS logs and identified CI/CD misconfiguration

---

### ❌ Issue: Pipeline Overwriting Task Definition
- Cause: CodePipeline created new revisions with incorrect config

✅ Fix:
- Updated buildspec and image definitions

---

## 📊 Key Learnings

- End-to-end CI/CD pipeline implementation on AWS
- Debugging real-world cloud deployment issues
- ECS task lifecycle and deployment strategies
- Docker image management with ECR

---

## 🧹 Cost Optimization

All AWS resources were terminated after testing to avoid unnecessary costs.

---

## 📌 Future Improvements

- Add HTTPS using ACM
- Implement auto-scaling
- Add monitoring alerts

---

## 👨‍💻 BY

Kal S
