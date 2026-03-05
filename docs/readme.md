# Multi-Tier Voting Application on Kubernetes (EKS)

This project demonstrates deploying a **multi-service microservices application** to **Amazon EKS (Kubernetes)** with a **CI/CD pipeline using GitHub Actions**.

The application is based on the **Docker Voting App** and showcases how different services communicate within a distributed system deployed on Kubernetes.

---

## Application Architecture

![Voting App Architecture](./img/Voting%20App.png)

The application consists of multiple microservices written in different languages and connected through message queues and databases.

Detailed architecture explanation:

➡️ [Application Description](docs/app-description.md)

---

## Project Requirements

This project focuses on deploying the voting application into a **production-like Kubernetes environment** using **Amazon EKS** and implementing **CI/CD automation**.

Full requirements:

➡️ [Project Requirements](docs/multi-tier-app-k8s-requirements.md)

---

## Deployment Steps

The following table outlines the main steps performed during this project.

| Step | Description                                                                                              | Documentation                                      |
| ---- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------- |
| 1    | Created Docker images for all microservices and pushed them to DockerHub                                 | [docs/docker-images.md](docs/docker-setup.md)      |
| 2    | Created an Amazon EKS Kubernetes cluster                                                                 | [docs/eks-cluster.md](docs/eks-cluster.md)         |
| 3    | Created Kubernetes **Deployment and Service YAML files** for Vote, Result, Worker, Redis, and PostgreSQL | [docs/k8s-deployments.md](docs/k8s-deployments.md) |
| 4    | Configured **Ingress** to expose the application                                                         | [docs/ingress.md](docs/ingress.md)                 |
| 5    | Implemented **GitHub Actions CI/CD pipeline** to automate builds and deployments                         | [docs/github-actions.md](docs/github-actions.md)   |
