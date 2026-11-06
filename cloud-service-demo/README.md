# Cloud Service Demo

## Project Purpose
This sample page represents a lightweight web application that can be hosted in the cloud or packaged into a container for consistent execution across different environments.

## Files Included
- **`index.html`**: The main HTML webpage for the application.
- **`Dockerfile`**: Instructions used by Docker to build the application image.
- **`README.md`**: Project documentation and instructions.

---

## Version Control & Cloud Relevance
Version control systems like Git help teams track changes to application files, maintain a complete history of work, and collaborate smoothly on cloud projects.

---

## Docker & Containerization Concepts

- **What Docker is:** A platform that allows applications to run in isolated environments called containers, ensuring they run consistently across different computers, testing servers, and cloud platforms.
- **What a Docker image is:** A packaged, read-only template used as a blueprint to create containers.
- **What a Docker container is:** An isolated, running instance created from a Docker image.

---

## How to Build and Run Using Docker

### 1. Build the Docker Image
Open your terminal in the project root folder and run the following command to build the image (note the trailing `.` which specifies the current directory as the build context):
```bash
docker build -t cloud-service-demo:1.0 .
```

### 2. Running the Docker Container
Start your container in the background and map port 8080 on your host computer to port 80 inside the container:
```bash
docker run -d --name cloud-demo-container -p 8080:80 cloud-service-demo:1.0
```

### 3. Testing Application
Open your web browser and navigate to:
```text
http://localhost:8080