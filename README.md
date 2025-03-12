# Enterprise CI/CD

## 📌 Overview
Enterprise CI/CD provides an automated pipeline for building, testing, and deploying applications using AWS CodePipeline and GitHub Actions.

## 🚀 Features
- **Continuous Integration & Deployment** with AWS CodePipeline
- **Automated Build & Test** using AWS CodeBuild
- **GitHub Actions Workflow** for repository automation
- **Artifact Storage** in AWS S3

## 📂 Folder Structure
```
enterprise-ci-cd/
├── .github/workflows/  # GitHub Actions pipeline
├── codepipeline/       # AWS CodePipeline setup
├── buildspec.yml       # AWS CodeBuild configuration
├── scripts/            # Helper scripts for deployment
├── README.md           # Documentation
```

## 🛠 Prerequisites
- AWS Account with CLI configured (`aws configure`)
- GitHub repository linked to AWS CodePipeline
- IAM role with access to AWS CodeBuild, S3, and CodePipeline

## ⚡ Deployment Steps

### **Step 1: Clone the Repository**
```sh
git clone https://github.com/your-org/enterprise-ci-cd.git
cd enterprise-ci-cd
```

### **Step 2: Set Up AWS CodePipeline**
- Open AWS Console → CodePipeline → Create Pipeline
- Select GitHub as the source repository
- Choose AWS CodeBuild for build stage (refer to `buildspec.yml`)
- Select S3 or Elastic Beanstalk for deployment stage

### **Step 3: Configure GitHub Actions**
- Edit `.github/workflows/deploy.yml` and add AWS credentials
- Push changes to trigger deployment
```sh
git add .
git commit -m "Setup CI/CD pipeline"
git push origin main
```

## 🎯 Usage
- Every push to `main` will trigger AWS CodePipeline
- GitHub Actions will automate deployment to AWS
- Logs available in AWS CodeBuild and GitHub Actions

## 🔄 Cleanup
To remove the pipeline:
```sh
aws codepipeline delete-pipeline --name my-ci-cd-pipeline
```

## 📖 Documentation
For detailed usage, refer to [AWS CodePipeline Docs](https://docs.aws.amazon.com/codepipeline/latest/userguide/) and [GitHub Actions Docs](https://docs.github.com/en/actions).

## 📌 License
This project is licensed under the MIT License.

