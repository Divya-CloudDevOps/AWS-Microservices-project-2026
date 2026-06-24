# AWS-Microservices-project-2026 

## 📌 Project Overview
This project demonstrates end-to-end cloud infrastructure automation — from provisioning AWS resources with Terraform, to containerizing microservices with Docker, deploying them on Kubernetes (EKS), and monitoring with Prometheus and Grafana. CI/CD is fully automated using Jenkins pipelines.

##  Architecture
┌─────────────────────────────────────────┐
                        │               AWS Cloud                  │
                        │                                          │
  User Request  ──────► │  ALB  ──►  NGINX Ingress  ──►  EKS     │
                        │                              (Node.js    │
                        │                              Services)   │
                        │                                  │       │
                        │                              MySQL/RDS   │
                        │                                          │
                        │                   │
                        └─────────────────────────────────────────┘
                                          ▲
                        Jenkins CI/CD Pipeline
                        (Build → Scan → Push ECR → Deploy) 

## 🛠️ Tech Stack
---------------------------------------------------------------------------------------------------
Category                                     Tools
---------------------------------------------------------------------------------------------------
Cloud                                       AWS (EC2,VPC,S3,IAM,ECR,ALB,Route53,NAT Gateway
Infrastructure as Code                      Terraform
Containers                                  Docker, Amazon ECR
Orchestration                               Kubernetes (EKS)
CI/CD                                       Jenkins                                  
Database                                    MySQL, AWS RDS
Scripting                                   Bash
Version Control                             GitHUB

## 📁 Repository Structure

├── Backend/                  # Node.js backend microservice
├── client/                   # Frontend application
├── Jenkins-Pipeline-code/    # Jenkinsfiles for CI/CD pipelines
├── eks-terraform/            # Terraform code for EKS cluster
├── terraform_main_ec2/       # Terraform code for EC2, VPC, networking
├── kubernetes-files/         # Kubernetes manifests (Deployments, Services, Ingress)
├── mysql/                    # MySQL configuration files
├── rds/                      # AWS RDS Terraform configuration
└── README.md

## 🚀 What I Built

1. AWS Infrastructure (Terraform)
 • Provisioned a VPC with public and private subnets across multiple Availability Zones
 • Set up NAT Gateway and Internet Gateway for secure, controlled traffic flow
 • Configured AWS ALB with host-based and path-based routing rules
 • Used Terraform modules to keep infrastructure code reusable and consistent

2. CI/CD Pipeline (Jenkins)
 • Built end-to-end Jenkins pipelines that automate:
 • Source code checkout from GitHub
 • Docker image build
 • Vulnerability scanning before pushing
 • Image push to Amazon ECR
 • Kubernetes deployment to EKS
 • Added image versioning so every build is traceable

3. Kubernetes (EKS)
 • Deployed Node.js microservices on Amazon EKS
 • Managed workloads using Deployments, ConfigMaps, and Secrets
 • Set up NGINX Ingress Controller for traffic routing and zero-downtime deployments

4. Security
 • All sensitive values stored in Kubernetes Secrets and IAM roles — no hardcoded credentials
 • Production workloads isolated in private subnets
 • Vulnerability scanning integrated directly into the CI/CD pipeline
 • Terraform resource tagging applied for ownership and cost tracking

## ⚙️ How to Deploy

Prerequisites
 • AWS account with IAM permissions
 • Terraform >= 1.3 installed
 • kubectl installed
 • AWS CLI configured (aws configure)
 • Docker installed
 
Step 1 — Provision Infrastructure
bash----
cd terraform_main_ec2
terraform init
terraform plan
terraform apply

Step 2 — Create EKS Cluste
bash----
cd eks-terraform
terraform init
terraform apply
aws eks update-kubeconfig --region <your-region> --name <cluster-name>

Step 3 — Deploy Application
bash----
cd kubernetes-files
kubectl apply -f .

Step 4 — Run Jenkins Pipeline
• Open Jenkins → New Pipeline → point to Jenkins-Pipeline-code/Jenkinsfile
• Trigger build — pipeline handles Docker build, ECR push, and EKS deployment automatically

## 📝 Key Learnings
 • How to design a multi-AZ, highly available AWS architecture using Terraform
 • How to build and maintain a CI/CD pipeline that takes code from commit to production
 • The importance of security at every layer — IAM, Kubernetes Secrets, private subnets
 • Writing Bash scripts to reduce repetitive manual steps in deployments

## 👩🏻‍💻 Author
  kalavakunta Divya Sree
📧 ksdivyaa2001@gmail.com
🔗 https://www.linkedin.com/in/ksdivya-sree-cloud-devops



