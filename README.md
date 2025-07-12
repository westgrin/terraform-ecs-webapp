# Mini Project - Hosting a Dynamic Web App on AWS with Terraform, Docker, ECR, and ECS (Local Setup)

## Project Overview
This project uses Terraform modules to host a Node.js web app on AWS ECS, containerized with Docker and stored in ECR. It includes building a VPC, ECR repository, and ECS cluster, and automating deployment with GitHub Actions. Builds on previous Terraform and Kubernetes projects (Jul 08-12, 2025).

## Setup
- Initiated on Jul 12, 2025, 1:01 PM WAT.
- Used WSL Ubuntu, VS Code, and Git Bash in `C:\Users\Abraham\Documents\Workspace\terraform-ecs-webapp`.
- System: 2 CPUs, 2GB free memory, 20GB free disk space.

## Execution Steps
1. **Confirm Prerequisites**:
   - Verified AWS CLI, Terraform, Docker, and Node.js.
   - [Screenshot: `aws_prerequisites_output_local.png` - Shows AWS CLI verification.]
   - [Screenshot: `docker_version_output_local.png` - Shows Docker version.]
   - [Screenshot: `nodejs_version_output_local.png` - Shows Node.js version.]
2. **Dockerize Web App**:
   - Created Node.js app and `Dockerfile`, tested locally.
   - [Screenshot: `docker_webapp_output_local.png` - Shows local web app output.]
3. **Create ECR and ECS Modules**:
   - Developed `modules/ecr/main.tf` for ECR repository.
   - Developed `modules/ecs/main.tf` for ECS cluster and service.
4. **Push Docker Image to ECR**:
   - Pushed image to `webapp-repo`.
   - [Screenshot: `ecr_push_output_local.png` - Shows Docker push output.]
5. **Deploy with Terraform**:
   - Ran `terraform init`, `validate`, `plan`, and `apply`.
   - [Screenshot: `terraform_init_output_local.png` - Shows initialization.]
   - [Screenshot: `terraform_validate_output_local.png` - Shows validation.]
   - [Screenshot: `terraform_plan_output_local.png` - Shows plan output.]
   - [Screenshot: `terraform_apply_output_local.png` - Shows apply output.]
6. **Access Web App**:
   - Accessed app at `http://<public-ip>:3000`.
   - [Screenshot: `ecs_webapp_output_local.png` - Shows ECS web app output.]
   - [Screenshot: `aws_ecs_output_local.png` - Shows ECS cluster in AWS Console.]
7. **Clean Up**:
   - Ran `terraform destroy` to remove resources.
   - [Screenshot: `terraform_destroy_output_local.png` - Shows destroy output.]
8. **Side Hustle Task**:
   - Automated deployment with GitHub Actions.
   - Pushed to `https://github.com/westgrin/terraform-ecs-webapp`.
   - [Screenshot: `github_actions_terraform_run_local.png` - Shows workflow run.]

## Learning Summary
This project advanced my skills in Terraform modules, Docker, and AWS ECS, building on my previous Terraform and Kubernetes projects (Jul 08-12, 2025). It reinforced containerization and cloud orchestration, aligning with my DevOps goals (June 16, 2025).

## Tools Used
- **WSL Ubuntu Terminal**: For AWS CLI, Terraform, and Docker commands.
- **VS Code**: For editing app and Terraform files.
- **Git Bash**: For GitHub operations.
- **GitHub Actions**: For deployment automation.
- **Terraform**: For infrastructure as code.
- **Docker**: For containerization.
- **AWS CLI**: For AWS authentication.

## Project Deliverables
- **Documentation**: This `README.md` with steps and learning summary.
- **Screenshots**:
  - `aws_prerequisites_output_local.png`
  - `docker_version_output_local.png`
  - `nodejs_version_output_local.png`
  - `docker_webapp_output_local.png`
  - `ecr_push_output_local.png`
  - `terraform_init_output_local.png`
  - `terraform_validate_output_local.png`
  - `terraform_plan_output_local.png`
  - `terraform_apply_output_local.png`
  - `ecs_webapp_output_local.png`
  - `aws_ecs_output_local.png`
  - `terraform_destroy_output_local.png`
  - `github_actions_terraform_run_local.png`
- **Script Link**: [GitHub Repository](https://github.com/westgrin/terraform-ecs-webapp)

## Local Development Instructions
1. Clone repository: `git clone https://github.com/westgrin/terraform-ecs-webapp.git`
2. Configure AWS CLI: `aws configure`
3. Build Docker image: `docker build -t westgrin/webapp:1.0 ./app`
4. Push to ECR: `docker push <account-id>.dkr.ecr.us-east-1.amazonaws.com/webapp-repo:1.0`
5. Initialize Terraform: `terraform init`
6. Validate script: `terraform validate`
7. Plan execution: `terraform plan`
8. Apply configuration: `terraform apply`
9. Access web app: `http://<public-ip>:3000`
10. Destroy resources: `terraform destroy`

## Troubleshooting
- Fixed AWS CLI authentication with `aws configure`.
- Ensured valid ECR repository and ECS task permissions.
- Set DNS to `8.8.8.8` for network issues.
- Verified system resources with `lscpu`, `free -h`, `df -h`.

## Conclusion
This project successfully deployed a Node.js web app on AWS ECS using Terraform and Docker, enhancing my skills in container orchestration and cloud infrastructure.