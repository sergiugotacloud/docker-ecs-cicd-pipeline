# CI/CD Pipeline on AWS (Docker + ECS + GitHub Actions)

## Overview

This project demonstrates a **fully automated CI/CD pipeline for deploying containerized applications on AWS**.

A simple web application is containerized with **Docker**, stored in **Amazon ECR**, and deployed automatically to **Amazon ECS Fargate** whenever new code is pushed to the GitHub repository.

The deployment process is automated using **GitHub Actions**, enabling continuous integration and continuous delivery.

This project simulates a **real-world production deployment workflow** used by modern cloud engineering teams.

---

## Architecture

The deployment pipeline follows this architecture:

Developer → GitHub Repository → GitHub Actions (CI/CD) → Docker Build → Amazon ECR → Amazon ECS Fargate → Application Load Balancer → End Users

AWS resources are deployed in the **eu-central-1 region** inside a **VPC (10.0.0.0/16)**.

---

## Architecture Diagram

![Architecture](screenshots/00-architecture-diagram.png)

---

## Technologies Used

* AWS ECS Fargate
* AWS ECR
* AWS Application Load Balancer
* AWS VPC
* Docker
* GitHub Actions
* Linux
* Git

---

## Project Structure

```
docker-ecs-cicd-pipeline
│
├── .github
│   └── workflows
│       └── deploy.yml
│
├── app
│   └── index.html
│
├── screenshots
│   ├── 00-architecture-diagram.png
│   ├── 01-github-repository-structure.png
│   ├── 02-ecr-image-pushed.png
│   ├── 03-ecs-task-definition.png
│   ├── 04-ecs-cluster-service-running.png
│   ├── 05-github-actions-pipeline-success.png
│   └── 06-live-application-alb.png
│
├── Dockerfile
├── task-definition.json
└── README.md
```

---

## CI/CD Pipeline Workflow

The deployment pipeline performs the following steps automatically:

1. Developer pushes code to GitHub
2. GitHub Actions pipeline starts
3. Docker image is built
4. Image is pushed to Amazon ECR
5. ECS service pulls the new container image
6. ECS deploys a new task revision
7. Application Load Balancer exposes the application

This creates a **fully automated container deployment pipeline**.

---

## Application Deployment

The application runs inside an **Amazon ECS Fargate service** behind an **Application Load Balancer**.

The ALB distributes incoming HTTP requests to the running container tasks.

End users access the application through the **ALB public endpoint**.

---

## Screenshots

### GitHub Repository Structure

![Repository](screenshots/01-github-repository-structure.png)

---

### Docker Image Stored in Amazon ECR

![ECR](screenshots/02-ecr-image-pushed.png)

---

### ECS Task Definition

![Task Definition](screenshots/03-ecs-task-definition.png)

---

### ECS Cluster and Service Running

![Cluster](screenshots/04-ecs-cluster-service-running.png)

---

### GitHub Actions CI/CD Pipeline

![Pipeline](screenshots/05-github-actions-pipeline-success.png)

---

### Live Application via Application Load Balancer

![Application](screenshots/06-live-application-alb.png)

---

## Key Concepts Demonstrated

* Containerization with Docker
* Container registry with Amazon ECR
* Container orchestration using Amazon ECS Fargate
* Infrastructure networking using VPC
* Load balancing with Application Load Balancer
* CI/CD automation using GitHub Actions
* Secure deployment using IAM roles

---

## Learning Outcomes

Through this project I practiced:

* Building containerized applications
* Designing CI/CD pipelines
* Deploying applications on ECS Fargate
* Integrating GitHub Actions with AWS
* Managing container images with Amazon ECR
* Deploying scalable web services behind load balancers

---

## Author

Sergiu Gota

AWS Certified Solutions Architect – Associate
AWS Certified Cloud Practitioner

GitHub: https://github.com/sergiugotacloud
