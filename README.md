# Node.js Demo App with Jenkins CI/CD Pipeline

This is a sample Node.js web app deployed using Jenkins CI/CD pipeline with Docker.

## Pipeline Stages:
- Clone source from GitHub
- Build Docker image
- Push to DockerHub
- (Optional) Deploy to server

## Requirements:
- DockerHub account
- Jenkins server with Docker installed
- Jenkins credentials for DockerHub (`dockerhub-creds`)
