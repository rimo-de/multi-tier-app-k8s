# Docker Setup – Build and Push Images

This document explains how Docker images were built for the microservices and pushed to **Docker Hub**.

The Voting Application contains the following services:

- **Vote** – Python Flask application
- **Result** – Node.js application
- **Worker** – .NET background service
- **Redis** – In-memory queue (official image)
- **PostgreSQL** – Database (official image)

Only the **Vote**, **Result**, and **Worker** services require custom Docker images.

---

## 1. Verify Project Structure

Before building Docker images, verify the repository structure.

Each service contains its own **Dockerfile** used to build the image.

```bash
app/
 ├── vote
 ├── result
 └── worker
```

![Projec_2_1]<../img/Project_2_1.png">

---

## 2. Login to Docker Hub

Authenticate with Docker Hub before pushing images.

```bash
docker login
```

After successful login, Docker will use your credentials to push images.

![Projec_2_2]<../img/Project_2_2.png">

---

## 3. Build Docker Images

Docker images are built for each service using the Dockerfile in the respective directories.

---

## Build Vote Service Image

The **Vote service** is a Python Flask application.

```bash
docker build -t rimo9docker/vote_k8s:latest ./app/vote
```

This command:

- Uses the Dockerfile inside `app/vote`
- Builds the container image
- Tags the image as `rimo9docker/vote_k8s:latest`

---

## Build Result Service Image

The **Result service** is a Node.js application.

```bash
docker build -t rimo9docker/result_k8s:latest ./app/result
```

![Projec_2_3]<../img/Project_2_3.png">

---

## Build Worker Service Image

The **Worker service** processes votes and writes results to PostgreSQL.

```bash
docker build -t rimo9docker/worker_k8s:latest ./app/worker
```

![Projec_2_4]<../img/Project_2_4.png">

---

## 4. Push Images to Docker Hub

After building the images, push them to Docker Hub.

```bash
docker push rimo9docker/vote_k8s:latest
docker push rimo9docker/result_k8s:latest
docker push rimo9docker/worker_k8s:latest
```

This uploads the images so they can be pulled by the **Kubernetes cluster**.

![Projec_2_5]<../img/Project_2_5.png">

---

## 5. Verify Docker Images

You can verify that the images exist locally by running:

```bash
docker images
```

Expected output should include:

```bash
rimo9docker/vote_k8s
rimo9docker/result_k8s
rimo9docker/worker_k8s
```

You can also verify the images in your **Docker Hub repository**.

---

## Summary

In this step we:

- Logged into **Docker Hub**
- Built Docker images for:
  - Vote service
  - Result service
  - Worker service
- Pushed images to **Docker Hub**
- Verified images locally

These images will be used in the **Kubernetes Deployment YAML files** when deploying the application to **Amazon EKS**.
