# Eclipse Che on Kubernetes
This repository contains configuration files to deploy Eclipse Che on Kubernetes.

## Deployment Instruction

### 1. Create a custom Che namespace

> kubectl create namespace che

### 2. Deploy the Echo Service and Ingress Controller

The only way that Che-Server can create workspaces is by creating an Ingress Controller. It is required for the Che Architecture. run the following commands:

> kubectl create -f echo-service.yml -n che

Once the Echo service is running execute the following command to create the ingress:

> kubectl create -f nginx-ingress.yml -n che


### 3. Deploy Eclipse che

> kubectl apply -f che.yml -n che

## Access URLS

Eclipse Che is being served using NodePorts. To access the dashboard navigate to the following url:

> http://<K8-MASTER-IP>:30123ee