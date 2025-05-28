# Devops-LLM-Bot-Infrastructure-PFA

This repository contains all the Kubernetes resource files required to deploy the infrastructure for the Devops LLM Bot project. The infrastructure is organized to support the following main components:

- **Backend Service**
- **Database (PostgreSQL)**
- **pgAdmin (Database Administration)**
- **Frontend Service**

## Project Structure

- `backend/` - Kubernetes manifests for the backend service (Deployment, Service, ConfigMap, etc.)
- `database/` - Kubernetes manifests for the PostgreSQL database (StatefulSet or Deployment, Service, PersistentVolumeClaim, etc.)
- `pgadmin/` - Kubernetes manifests for pgAdmin (Deployment, Service, ConfigMap, etc.)
- `frontend/` - Kubernetes manifests for the frontend service (Deployment, Service, ConfigMap, etc.)

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/Devops-LLM-Bot-PFA/Devops-LLM-Bot-Infrastructure-PFA.git
   cd Devops-LLM-Bot-Infrastructure-PFA
   ```

2. Apply the Kubernetes manifests in the correct order (database and pgAdmin first, then backend, then frontend):

   ```bash
   kubectl apply -f database/
   kubectl apply -f pgadmin/
   kubectl apply -f backend/
   kubectl apply -f frontend/
   ```

3. Monitor your resources:

   ```bash
   kubectl get all
   ```

## Customization

- Edit environment variables, resource requests/limits, and configurations in the respective manifest files as needed.
- Update any image references to match your built images.

## Prerequisites

- Kubernetes cluster (local via Minikube, Kind, or remote)
- `kubectl` configured to access your cluster

