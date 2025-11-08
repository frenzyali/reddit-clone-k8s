# Reddit Clone Kubernetes Deployment 🚀

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

---

## Overview
This project demonstrates a full **end-to-end deployment** of a containerized Reddit clone application on **Kubernetes**.  

Key Highlights:
- Containerized using Docker
- Deployed and orchestrated using Kubernetes
- Exposed externally via NodePort service
- Suitable for CI/CD integration

---

## Architecture
GitHub Repository
│
▼
CI Server (Docker Build)
│
▼
Docker Image pushed to Registry
│
▼
Kubernetes Cluster on EC2
├─ Deployment: reddit-clone
└─ Service: NodePort (external access)

yaml
Copy code

---

## Features
- **Containerized Application**: Dockerized for consistency across environments  
- **Kubernetes Deployment**: Scalable deployment with multiple replicas  
- **Service Exposure**: NodePort service for external access  
- **CI/CD Ready**: Integrates easily with automated pipelines  

---

## Prerequisites
- [Docker](https://www.docker.com/) installed  
- Kubernetes cluster (Minikube, Kind, or EC2 K8s cluster)  
- `kubectl` configured to access the cluster  
- GitHub account for pushing/pulling code  

---

## Deployment Steps

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/frenzyali/reddit-clone-k8s.git
cd reddit-clone-k8s
2️⃣ Build Docker Image
bash
Copy code
docker build -t <your-username>/reddit-clone .
docker push <your-username>/reddit-clone
3️⃣ Deploy on Kubernetes
bash
Copy code
kubectl apply -f reddit-deployment.yaml
kubectl apply -f reddit-service.yaml
4️⃣ Access the Service
Minikube Tunnel:

bash
Copy code
minikube service reddit-clone-service --url
Port Forward (Permanent Localhost):

bash
Copy code
kubectl port-forward service/reddit-clone-service 31000:3000
Then open: http://localhost:31000

Notes
Designed for demo and learning purposes

Can be scaled by updating replicas in the deployment YAML

CI/CD integration possible for automated builds and deploys

Author
Ali Hussain – DevOps & Kubernetes Enthusiast

GitHub: frenzyali

LinkedIn: [Your LinkedIn Profile]
