# k8s-simple-deployment-demo

## Overview

This project is a minimal Kubernetes deployment example using nginx to understand how Deployment and Service objects work together.

---

## Architecture

User → Kubernetes Service → Pods (Deployment) → nginx container

## Repository Structure

```bash
.
├── README.md
├── deployment.yaml
└── service.yaml
```

## Prerequisites

- Kubernetes cluster (Minikube / Kind / cloud)
- kubectl installed and configured
- Docker image available (or using nginx for testing)

## Deployment Steps

### 1. Apply Deployment

```bash
kubectl apply -f deployment.yaml
```

## 2. Apply Service

```bash
kubectl apply -f service.yaml
```

### Verify Deployment
# Check Pods

```bash
kubectl get pods
```

### Expected output:
```text
NAME                                   READY   STATUS    RESTARTS   AGE
k8s-simple-deployment-xxxxx           1/1     Running   0          1m
```

### Check Service
```bash
kubectl get services
```

### Access Application (Minikube)

```bash
minikube service k8s-simple-service
```

### Update Deployment
```bash
kubectl rollout restart deployment k8s-simple-deployment
```

Notes
Default image used: nginx:latest. You can replace it with your own Docker image in deployment.yaml

```md
This project was created to understand Kubernetes Deployment and Service basics using a minimal nginx container.
```

## Version
```
v1.0 - Initial Kubernetes deployment using nginx
