# GitHub Actions CI/CD POC - EC2 + Docker

This project shows how to:
- Commit code to GitHub
- Build & push Docker image using GitHub Actions
- Deploy container on AWS EC2 instance

## Files
- `index.html` - Hello world page served by nginx
- `Dockerfile` - Docker build recipe
- `.github/workflows/ci-cd.yml` - GitHub Actions pipeline

## Setup Steps
1. Create AWS EC2 (Ubuntu) and install Docker
2. Create Docker Hub repo (e.g., `devops-hello`)
3. Add GitHub Secrets:
   - DOCKERHUB_USERNAME
   - DOCKERHUB_TOKEN
   - SSH_HOST (EC2 public DNS/IP)
   - SSH_USER (`ubuntu`)
   - SSH_PRIVATE_KEY (contents of `.pem` file)
   - SSH_PORT (`22`)
4. Push code to `main` branch
5. GitHub Actions:
   - builds and pushes Docker image
   - SSHes into EC2
   - runs container on port 8081
6. Visit: `http://<EC2_PUBLIC_IP>:8081/`
