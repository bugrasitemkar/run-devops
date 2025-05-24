# Deploying .NET Microservices to Azure Kubernetes Services (AKS) with Azure DevOps

This repository demonstrates how to build and deploy .NET-based microservices to Azure Kubernetes Services (AKS), using Docker and Azure Container Registry (ACR), and automating deployments via Azure DevOps CI/CD pipelines integrated with GitHub.

## 🔭 Overview

We will develop and deploy three core microservices:

- `Shopping.Client` (ASP.NET MVC)
- `Shopping.API` (ASP.NET Web API with MongoDB)
- `MongoDB` (NoSQL Database)

![Overall Architecture](https://user-images.githubusercontent.com/1147445/105671396-b152f580-5ef3-11eb-8f3b-7f9f7c9c4d24.png)

---

## 🛍 Shopping MVC Client Application

This is a standalone ASP.NET MVC web project that initially includes its own data. Key steps include:

- Dockerizing the application.
- Pushing the Docker image to Docker Hub.
- Deploying the container using **Azure Web App for Containers**.

Later, the client will consume the external Shopping API.

---

## 🔌 Shopping API Microservice

This ASP.NET Core Web API project:

- Manages product data using MongoDB.
- Exposes endpoints for the Shopping Client.
- Is containerized using a Dockerfile.
- Is pushed to **Azure Container Registry (ACR)**.
- Is deployed via **Kubernetes**.

---

## 🗃 MongoDB Microservice

MongoDB acts as the data source for the API service.

- MongoDB is pulled as a Docker image from Docker Hub.
- It is composed with other services using Docker Compose.
- Integration with the Shopping.API project is established.

---

## ☸️ Local to Cloud Deployment

By the end of the project, you will have:

- Dockerized all microservices.
- Tested them locally using Docker Compose.
- Deployed them on a local Kubernetes cluster.
- Pushed all Docker images to ACR.
- Shifted deployments to Azure Kubernetes Services (AKS).
- Updated microservices with **zero-downtime deployments**.

---

## 🚀 CI/CD with Azure DevOps Pipelines

The final phase focuses on automation using Azure DevOps:

- Creating **CI/CD pipelines** for each microservice.
- Automating builds on **GitHub pushes**.
- Building Docker images and pushing them to **ACR**.
- Deploying to **AKS with zero downtime** using Kubernetes manifests and Azure Pipelines.

![CI/CD Pipeline](https://user-images.githubusercontent.com/1147445/105671542-f37c3700-5ef3-11eb-9532-59a5855214d0.png)

---

## 📁 Repository Structure

```
/Shopping.Client        # ASP.NET MVC application
/Shopping.API           # ASP.NET Core Web API with MongoDB
/docker-compose.yml     # Compose all services for local dev
/infra                  # Kubernetes manifests and pipeline YAMLs
```

---

## 🧰 Technologies Used

- .NET Core (MVC + Web API)
- MongoDB
- Docker & Docker Compose
- Azure Container Registry (ACR)
- Azure Kubernetes Services (AKS)
- Azure DevOps Pipelines
- GitHub Integration

---

## 📌 Prerequisites

- Docker
- Kubernetes CLI
- Azure CLI
- Azure Subscription
- Azure DevOps Account

---

## 📄 License

This project is part of a course and intended for educational purposes.
