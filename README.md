# 🚀 Automate Docker Image Creation & Deployment using Jenkins

This project demonstrates how to install Jenkins from scratch, set up a local Docker registry, and automate Docker builds and image pushes using Jenkins pipelines.

## 🔧 What It Does

- Installs Jenkins manually (no Docker image pull)
- Builds a sample Python app into a Docker image
- Pushes that image to a self-hosted Docker registry
- Uses a declarative Jenkins pipeline (`Jenkinsfile`)

## 📁 Files Included

- `Dockerfile` - Defines the Python app image
- `app.py` - Simple test script
- `Jenkinsfile` - Jenkins pipeline to automate build & push
- `4.docx` - Documented walkthrough of setup and instructions

## 🧪 Test Locally

```bash
docker run -d -p 5000:5000 --name registry registry:2
docker build -t localhost:5000/myapp:v1 .
docker push localhost:5000/myapp:v1
curl http://localhost:5000/v2/_catalog
