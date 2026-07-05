# Deploying an Application on Kubernetes

## Project Overview

This repository demonstrates how to deploy a containerized application on a Kubernetes cluster using Kubernetes Deployment and Service manifests.

The Deployment manages application Pods, while the Service exposes the application so it can be accessed within or outside the cluster.

## Repository Structure

```text
Deploying-an-Application-on-Kubernetes/
├── README.md
├── deployment.yaml
└── service.yaml
```

## Prerequisites

Before deploying the application, ensure you have:

* Docker installed
* Kubernetes cluster (Minikube, Kind, Docker Desktop Kubernetes, or a cloud cluster)
* kubectl installed and configured
* A Docker image pushed to Docker Hub

## Kubernetes Manifests

### deployment.yaml

Creates a Deployment that:

* Runs two replicas of the application
* Pulls the Docker image from Docker Hub
* Exposes container port 3000
* Configures CPU and memory resources
* Includes readiness and liveness probes

### service.yaml

Creates a Service that:

* Exposes the application
* Routes traffic to the running Pods
* Maps port 80 to container port 3000

## Deployment Steps

Apply the Deployment:

```bash
kubectl apply -f deployment.yaml
```

Apply the Service:

```bash
kubectl apply -f service.yaml
```

## Verify the Deployment

Check the Deployment:

```bash
kubectl get deployments
```

Check the Pods:

```bash
kubectl get pods
```

Check the Service:

```bash
kubectl get services
```

Describe the Deployment:

```bash
kubectl describe deployment kubernetes-demo-deployment
```

## Updating the Application

After pushing a new Docker image, restart the Deployment:

```bash
kubectl rollout restart deployment kubernetes-demo-deployment
```

## Cleaning Up

Delete all deployed resources:

```bash
kubectl delete -f service.yaml
kubectl delete -f deployment.yaml
```

## Learning Outcomes

This project demonstrates:

* Creating Kubernetes Deployments
* Creating Kubernetes Services
* Deploying containerized applications
* Managing Pods using kubectl
* Exposing applications within a Kubernetes cluster
