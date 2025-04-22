
# CI/CD Pipeline Automation for Software Deployment

This project demonstrates end-to-end CI/CD automation using GitHub Actions and AWS EC2.

## Steps to Run

1. Launch an EC2 instance (Ubuntu)
2. Install Docker on EC2
3. Upload this project to GitHub
4. Add GitHub secrets: `EC2_HOST`, `EC2_KEY`
5. Push a commit to trigger deployment
6. Access your app at http://<EC2-IP>
