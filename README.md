# DevOps-Master-Project

This project provisions a complete CI/CD pipeline on AWS using **Terraform** and integrates **DevSecOps** practices using **GitHub Actions**, **tfsec**, **Trivy**, and **Kubernetes Sealed Secrets**.

---

## 📌 Project Tasks

### 🟩 Task 1: AWS CodePipeline using Terraform
Provision AWS services using Infrastructure as Code (**Terraform**):

- **Source**: GitHub (via CodeStar connection)
- **Build**: AWS CodeBuild
- **Deploy**: AWS CodeDeploy (to EC2)
- **S3**: Artifact storage
- **IAM**: Role-based access
- **Testing**: Terratest for infrastructure validation

### 🟦 Task 2: DevSecOps using GitHub Actions & Sealed Secrets
Set up a CI/CD workflow with security scanning and Kubernetes secret management:

- **Terraform Security Scan**: `tfsec`
- **Docker Image Scan**: `Trivy`
- **Kubernetes Deployment**: via GitHub Actions
- **Secrets Management**: Sealed Secrets

---

## 🧱 Project Structure
DevSecOps-Masters-Project/
├── terraform/
│ ├── main.tf
│ ├── variables.tf
│ ├── outputs.tf
│ └── versions.tf
│
├── test/
│ └── pipeline_test.go # Terratest validation
│
├── docker/
│ └── Dockerfile # Containerized app
│
├── k8s/
│ ├── manifests/
│ │ └── deployment.yaml # Kubernetes deployment
│ └── secrets/
│ └── sealed-secret.yaml # Encrypted SealedSecret
│
├── .github/
│ └── workflows/
│ └── devsecops-pipeline.yml # GitHub Actions pipeline
│
├── .gitignore
└── README.md

---

## 🔧 Prerequisites

- AWS CLI (configured)
- Terraform ≥ 1.4
- Go (for Terratest)
- Docker Desktop with Kubernetes enabled
- `kubectl` & `kubeseal`
- GitHub personal access token & CodeStar connection
- EC2 instance with CodeDeploy agent installed

---

## 🚀 Deployment Guide

### Step 1: Clone the Repository
```bash
git clone https://github.com/<your-username>/DevSecOps-Masters-Project.git
cd DevSecOps-Masters-Project/terraform

