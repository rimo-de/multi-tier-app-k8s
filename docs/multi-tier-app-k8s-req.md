# Project 2 – Multi-Tier App Deployment on Amazon EKS

This project focuses on deploying a **multi-service voting application** to an **Amazon EKS (Kubernetes) cluster** and automating deployments using **GitHub Actions CI/CD**.

The application includes the following services:

- Vote (Python / Flask)
- Result (Node.js)
- Worker (.NET)
- Redis
- PostgreSQL

---

## Project Goals

### Goal 1 – Provision an EKS Cluster

- Create an **Amazon EKS Kubernetes cluster**
- Use tools such as:
  - `eksctl`
  - Terraform (optional)
- Ensure the cluster is **scalable and production-ready**

---

### Goal 2 – Containerize and Deploy Microservices

Deploy the voting application components to Kubernetes.

Services to deploy:

- Vote service
- Result service
- Worker service
- Redis
- PostgreSQL

Deployment requirements:

- Build Docker images for each microservice
- Push images to a container registry (e.g., Docker Hub)
- Create Kubernetes manifests for:
  - Deployments
  - Services

---

### Goal 3 – Configure Application Networking

Expose the application using Kubernetes networking components.

Requirements:

- Install **NGINX Ingress Controller**
- Configure **Ingress resource**
- Route traffic to services:
  - `/vote` → Vote service
  - `/result` → Result service

---

### Goal 4 – Implement CI/CD Pipeline

Set up **GitHub Actions CI/CD pipeline** to automate deployments.

Pipeline should:

- Build Docker images for each service
- Push images to Docker Hub
- Deploy or update Kubernetes manifests on EKS using `kubectl`

---

## Expected Outcome

By the end of this project:

- The application runs on **Amazon EKS**
- All services are deployed as **Kubernetes pods**
- External access is provided through **Ingress**
- Application deployments are automated using **GitHub Actions**
