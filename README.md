# k8s-simple-deployment-demo

## Overview

This project demonstrates a simple Kubernetes deployment using a Deployment and Service.

It deploys a sample containerized application and exposes it using a Kubernetes Service.

> This is a sample Kubernetes deployment project using a public or custom container image.

---

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
## Check Pods

```bash
kubectl get pods
```

### Expected output:
Expected output:

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
Default image used: nginx:latest
You can replace it with your own Docker image in deployment.yaml
