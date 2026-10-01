# Node.js CI/CD Pipeline

## Project Overview

This project demonstrates a basic CI/CD pipeline for a Node.js web application using GitHub Actions and Docker.

The pipeline automatically:

1. Runs tests
2. Builds a Docker image
3. Pushes the Docker image to Docker Hub

The pipeline is triggered whenever code is pushed to the `main` branch.

## Technologies Used

* Node.js
* Express.js
* Jest
* Docker
* Docker Hub
* GitHub
* GitHub Actions

## Application

The application is a simple Express.js web server.

### Endpoints

```text
GET /
GET /health
```

## Run Locally

Install dependencies:

```bash
npm install
```

Run tests:

```bash
npm test
```

Start the application:

```bash
npm start
```

The application runs on:

```text
http://localhost:3000
```

## Run Using Docker

Build the Docker image:

```bash
docker build -t nodejs-demo-app .
```

Run the container:

```bash
docker run -d -p 3000:3000 nodejs-demo-app
```

## CI/CD Pipeline

The GitHub Actions workflow is located at:

```text
.github/workflows/main.yml
```

The pipeline performs the following steps:

```text
Developer pushes code
        ↓
GitHub Repository
        ↓
GitHub Actions
        ↓
Install dependencies
        ↓
Run tests
        ↓
Build Docker image
        ↓
Login to Docker Hub
        ↓
Push Docker image
```

## Docker Hub

The Docker image is published to Docker Hub using the following format:

```text
YOUR_DOCKERHUB_USERNAME/nodejs-demo-app:latest
```

## GitHub Secrets

The workflow uses the following GitHub repository secrets:

```text
DOCKERHUB_USERNAME
DOCKERHUB_TOKEN
```

These secrets are used to authenticate with Docker Hub without exposing credentials in the workflow file.
