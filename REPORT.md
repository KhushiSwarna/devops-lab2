# Lab 2 - Containerization & Kubernetes Orchestration

## Objective

To implement containerization using Docker and application orchestration using Kubernetes, including deployment, scaling, rolling updates, rollback and continuous deployment.

## Architecture

GitHub
↓
Jenkins
↓
Kubernetes / Minikube
↓
Deployment
↓
Pods
↓
Service
↓
Application

## 1. Docker Containerization

A Python Flask application was containerized using a Dockerfile based on `python:3.12-slim`.

The application image was built as:

`devops-lab2:v1`

The container exposed port 5000 and the application was successfully accessed through the browser.

Docker image layers were inspected using `docker history`.

## 2. Docker Container and Image Management

Docker containers were listed, started, stopped and removed.

The application image was tagged and pushed to Docker Hub:

`axdy02/devops-lab2:v1`

Docker Compose was also used to run a multi-container setup consisting of the Flask application and Redis.

## 3. Docker Storage

Without persistent storage, data disappeared after the original container was removed.

A Docker named volume called `lab2-data` demonstrated persistent storage across container deletion.

A bind mount demonstrated two-way file sharing between Ubuntu and a Docker container.

## 4. Docker Networking

A custom Docker bridge network called `lab2-network` was created.

Two containers communicated successfully using:

- Container names
- Container IP addresses

Docker network inspection confirmed both containers belonged to the same subnet.

## 5. Kubernetes Deployment

Minikube was started using the Docker driver.

The application was deployed using:

- Deployment manifest
- Service manifest

Two application pods were successfully created and the application was exposed through a Kubernetes Service.

## 6. Kubernetes Deployment Strategies

The Deployment was scaled from two replicas to four replicas.

Version 2 of the application was built and pushed to Docker Hub.

A rolling update replaced version 1 with version 2 without recreating the entire Deployment manually.

Kubernetes rollout history was inspected and a rollback successfully restored version 1.

## 7. Continuous Deployment

Jenkins was integrated with the Kubernetes deployment.

The Jenkins pipeline automatically applies the Kubernetes Deployment and Service manifests and verifies rollout status.

This demonstrates a basic Continuous Deployment workflow.

## Results

The following tasks were successfully completed:

1. Docker image creation
2. Container management
3. Docker Hub registry push
4. Docker Compose
5. Persistent storage
6. Docker networking
7. Kubernetes deployment
8. Replica scaling
9. Rolling updates
10. Rollback
11. Jenkins-based continuous deployment

## Conclusion

The experiment demonstrated a complete containerization and orchestration workflow using Docker, Docker Hub, Kubernetes, Minikube and Jenkins.
