# 🚀 Deploy Dynamic Web Apps on AWS using CI/CD Pipelines and GitHub Actions

[![Terraform](https://img.shields.io/badge/IaC-Terraform-623CE4?logo=terraform)](https://www.terraform.io/)
[![CI/CD](https://img.shields.io/badge/GitHub%20Actions-CI%2FCD-blue?logo=githubactions)](https://github.com/features/actions)
[![AWS](https://img.shields.io/badge/Cloud-AWS-FF9900?logo=amazon-aws)](https://aws.amazon.com/)
[![Docker](https://img.shields.io/badge/Container-Docker-2496ED?logo=docker)](https://www.docker.com/)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

> This project demonstrates how to deploy a **rentzone web application** on AWS using **Infrastructure as Code**, **GitHub Actions**, **Docker**, and a **fully automated CI/CD pipeline**.
![Alt text](/Components.png)
---

## 🛠️ Setup & Steps

### 1. Local Development Setup
- Installed Terraform, Git, AWS CLI, and VS Code.
- Set up SSH keys for GitHub access.
- Installed Terraform and AWS extensions in VS Code.

### 2. AWS Configuration
- Created an IAM user and configured AWS credentials locally.
- Created an S3 bucket and DynamoDB table to store Terraform state.

### 3. Terraform Infrastructure Deployment
- Initialized a GitHub repository and added Terraform code.
- Registered a domain in Route 53.
- Created and filled in `terraform.tfvars`.
- Ran `terraform init`, `plan`, and `apply` to deploy infrastructure.

### 4. Secrets & Domain
- Added secrets in AWS Secrets Manager.
- Connected domain name with Route 53 hosted zone.

### 5. GitHub Actions CI/CD Pipeline
- Generated a GitHub Personal Access Token.
- Created GitHub repository secrets (AWS credentials, etc.).
- Created workflow files to:
  - Configure AWS credentials
  - Deploy infrastructure
  - Build and push Docker image to Amazon ECR

### 6. Self-Hosted Runner for GitHub Actions
- Launched EC2 instance and installed Docker + Git.
- Created an AMI for self-hosted runner.
- Used GitHub Actions jobs to:
  - Start and stop the self-hosted runner dynamically
  - Export environment variables to S3
  - Create new ECS Task Definitions
  - Restart ECS services

### 7. Application Deployment
- Created a Laravel application and added the `AppServiceProvider.php`.
- Wrote a `Dockerfile` to containerize the app.
- Built and pushed Docker image using GitHub Actions.
- Created SQL migration scripts and added them under `/sql`.
- Used Flyway in CI/CD to migrate the database.

---

## 🔁 GitHub Actions Workflow Summary

| Workflow File                  | Purpose                                                    |
|--------------------------------|-------------------------------------------------------------|
| `setup-aws-credentials.yml`    | Configure AWS credentials securely                         |
| `deploy-infrastructure.yml`    | Apply Terraform to provision infrastructure                |
| `build-and-push-docker.yml`    | Build Docker image and push to Amazon ECR                  |
| `runner-start.yml`             | Launch self-hosted EC2 runner                              |
| `runner-stop.yml`              | Terminate the self-hosted EC2 runner                       |
| `export-env-vars.yml`          | Export secrets to S3                                       |
| `db-migration.yml`             | Use Flyway to migrate RDS schemas                          |
| `ecs-deploy.yml`               | Update ECS task definition and restart the service         |

---

## 📚 What I Learned

Through this project, I gained hands-on experience in:

✅ Provisioning infrastructure using **Terraform**

✅ Managing AWS resources like **EC2, ECS, RDS, S3, DynamoDB, Route 53**, and **Secrets Manager**

✅ Setting up a **CI/CD pipeline** using **GitHub Actions** with multiple jobs and dependencies

✅ Building and pushing **Docker images to ECR**

✅ Creating and managing **self-hosted runners** in AWS

✅ Handling **secure environment variables** and **database migrations** using **Flyway**

✅ Leveraging **domain name services** and updating DNS records via **Route 53**

✅ Writing production-ready, modular, and reusable **Infrastructure as Code**

---

## ✅ Final Result

- ✅ Fully automated CI/CD pipeline from code push to deployment
- ✅ Laravel app deployed in **ECS Fargate**
- ✅ Infrastructure managed by **Terraform** with remote state in **S3** and locking via **DynamoDB**
- ✅ Container images built and pushed to **Amazon ECR**
- ✅ RDS Database migrations handled via **Flyway**

---

## 📬 Contact

Have questions or want to collaborate? Feel free to connect!::terrencencube593@gmail.com

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

