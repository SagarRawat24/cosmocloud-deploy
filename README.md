
# CosmoCloud Deployment with Helm
This project provides Helm templates to deploy the CosmoCloud application, which includes frontend, backend, and Redis services. The deployment is designed for Kubernetes environments and allows easy customization via the values.yaml file.


## project structure 
```

cosmocloud-deploy/  
|-- Chart.yaml               # Metadata about the Helm chart (name, version, etc.).  
|-- README.md                # Documentation for the Helm chart.  
|-- templates/               # Contains Kubernetes manifests for the application.  
|   |-- Configmap.yaml       # Configuration for the application (e.g., environment variables).  
|   |-- backend.yaml         # Deployment configuration for the backend service.  
|   |-- backendservice.yaml  # Service definition for the backend.  
|   |-- front-service.yaml   # Service definition for the frontend.  
|   |-- frontend.yaml        # Deployment configuration for the frontend service.  
|   |-- redis-svc.yaml       # Service definition for Redis.  
|   `-- redis.yaml           # Deployment configuration for Redis.  
|-- values.yaml              # Default values for configurable parameters.  

```
# Usage

## Clone the repository
```
git clone https://github.com/SagarRawat24/cosmocloud-deploy.git
```

## Deploy the Helm Chart
```
 helm install testapp cosmocloud-deploy --atomic --timeout 30s
                     or 
 helm install testapp ./cosmocloud-deploy --atomic --timeout 30s                    
```

## Check the deployment
```
 kubectl get all
```

## check the environment variables is attach 
```
kubectl exec -it podname -- printenv 
```

## uninstall the deployment 
```
helm uninstall testapp
```

## upgrade the application 
```
helm upgrade testapp ./cosmocloud-deploy
```
# Templates overview


Configmap.yaml: Configures environment variables shared across services.

backend.yaml: Deploys the backend service as a Kubernetes deployment.

backendservice.yaml: Exposes the backend deployment as a service.

frontend.yaml: Deploys the frontend service.

front-service.yaml: Exposes the frontend deployment as a service.

redis.yaml: Deploys Redis as a Kubernetes deployment. 

redis-svc.yaml: Exposes Redis as a service for inter-service communication.
# Prerequisites
Kubernetes cluster: Ensure you have a running Kubernetes cluster.

Helm: Install Helm (version 3 or later).

kubectl: Install kubectl and configure it to access your cluster.

#Screenshots
![Screenshot 2024-12-03 193825](https://github.com/user-attachments/assets/f1a336d3-3b83-45a7-9000-672dda6acefe)
![Screenshot 2024-12-03 193902](https://github.com/user-attachments/assets/7a3d4551-5c73-42c8-b15a-449c2f325ad5)

