# Cloud Service Demo

## Project Purpose & Overview
This sample page represents a lightweight web application that can be hosted in the cloud, packaged into a container for consistent execution across different environments, and orchestrated using Kubernetes. Version control systems like Git help teams track changes to application files, maintain a complete history of work, and collaborate smoothly on cloud projects.

## Files Included
- **`index.html`**: The main HTML webpage for the application.
- **`Dockerfile`**: Instructions used by Docker to build the application image.
- **`kubernetes/deployment.yaml`**: Kubernetes Deployment configuration defining the application Pods and replicas.
- **`kubernetes/service.yaml`**: Kubernetes Service configuration exposing the application Pods.
- **`README.md`**: Project documentation and instructions.

---

## Docker: Containerization Concepts & Commands
Docker is a platform that allows applications to run in isolated environments called containers, ensuring they run consistently across different computers, testing servers, and cloud platforms. A Docker image is a packaged, read-only template used as a blueprint to create containers, while a Docker container is an isolated, running instance created from that image.

To build and run the application using Docker, open your terminal in the project root folder and execute:
```bash
docker build -t cloud-service-demo:1.0 .
docker run -d --name cloud-demo-container -p 8080:80 cloud-service-demo:1.0

Kubernetes: Orchestration Concepts & Commands

Kubernetes is an open-source container orchestration platform used to automate the deployment, scaling, and management of containerized applications, ensuring high availability and resilience. Key resources include:

    Pod: The smallest deployable unit in Kubernetes that encapsulates and runs one or more application containers.

    Deployment: A Kubernetes resource that manages stateless application Pods, ensuring the desired number of replicas are running and healthy.

    Service: A Kubernetes abstraction that provides a stable network endpoint to access a dynamic group of Pods.

To deploy, expose, and access the application using Minikube and Kubernetes, run the following commands in your terminal:
Bash

minikube start --driver=docker
minikube image load cloud-service-demo:1.0
kubectl apply -f kubernetes/deployment.yaml
kubectl apply -f kubernetes/service.yaml
kubectl port-forward service/cloud-service-demo 8080:80