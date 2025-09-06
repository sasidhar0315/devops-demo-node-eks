# 🚀 DevOps Demo: Node.js App on AWS EKS with GitHub Actions & Helm

This project demonstrates a **CI/CD pipeline** using:
- **GitHub Actions** (build & deploy automation)
- **Docker** (containerization)
- **Helm** (Kubernetes deployment templates)
- **AWS EKS** (Kubernetes cluster)

---

## 📌 Project Overview
- Node.js demo application  
- Docker image pushed to **DockerHub** → [`donsasi/node-demo-app`](https://hub.docker.com/r/donsasi/node-demo-app)  
- Deployment on **EKS** using Helm chart  
- Automated pipeline with **GitHub Actions**

---

## ⚙️ CI/CD Workflow
1. **Code Commit** (on `main` or `dev` branch)  
2. **GitHub Actions**:
   - Build Docker image  
   - Push to DockerHub  
   - Deploy/update app on AWS EKS with Helm  
3. **Helm Deployment**:
   - Handles service, probes, scaling configs  
   - App exposed via `NodePort`  

---

## 🌱 Branching Strategy
- **`dev` branch** → Deploys to `dev` namespace  
- **`main` branch** → Deploys to `prod` namespace  

---

## 🛠️ Run Locally (Optional)
```bash
# Clone the repo
git clone https://github.com/<your-username>/devops-demo-node-eks.git
cd devops-demo-node-eks

# Build Docker image
docker build -t donsasi/node-demo-app:1.0 .

# Run container locally
docker run -p 3000:3000 donsasi/node-demo-app:1.0
