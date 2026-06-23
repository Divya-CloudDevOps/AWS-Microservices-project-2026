# AWS-Microservices-project-2026 

## Overview
This project demonstrates the deployment of a containerized microservices application on AWS using modern DevOps practices.

The application is built using microservices architecture and deployed on Amazon EKS using Kubernetes. Infrastructure is provisioned using Terraform and CI/CD is automated using Jenkins.

## Technologies Used

- AWS EKS
- AWS RDS
- Docker
- Kubernetes
- Terraform
- Jenkins
- Node.js
- MySQL
- GitHub

## Architecture

Developer → GitHub → Jenkins Pipeline → Docker Build → AWS ECR → Amazon EKS → Application

Database: Amazon RDS (MySQL)

## Project Structure

```text
AWS-Microservices-project-2026/
│
├── Backend/
├── client/
├── eks-terraform/
├── Jenkins-Pipeline/
├── kubernetes-files/
├── mysql/
├── rds/
└── terraform_main/

##Features##

* Microservices-based architecture
* Containerized using Docker
* Kubernetes deployment on EKS
* Infrastructure as Code using Terraform
* Automated CI/CD with Jenkins
* Managed database using Amazon RDS

##Prerequisites##

* AWS Account
* Docker
* kubectl
* Terraform
* Jenkins
* Git

##Deployment Steps##

Clone Repository
1. git clone https://github.com/Divya-CloudDevOps/AWS-Microservices-project-2026.git
2. cd AWS-Microservices-project-2026

##Create Infrastructure##
---bash---
1. terraform init
2. terraform plan
3. terraform apply

##Configure Kubernetes##
1. aws eks update-kubeconfig --region <region> --name <cluster-name>

##Deploy Application##
---bash---
1. kubectl get pods 
2. kubectl get services

##Author##
KALAVAKUNTA DIVYA SREE
AWS DevOps Engineer
