# go-docker-minikube

1. Use Minikube’s Docker Daemon
This allows you to build images directly into the Minikube VM so you can reference them in Kubernetes deployments.
(RUN IN GIT BASH)
minikube start
eval $(minikube docker-env)
Now any docker build you do will go into Minikube's Docker environment.

2. Build the Go App Locally Inside Minikube’s Docker
From your app directory (where Dockerfile is located):
docker build -t user-app:local .
This tags your app image as user-app:local in Minikube's Docker engine.

3. Deploy Everything
kubectl apply -f k8s/


4. Check the Services
minikube service user-app

# Couple of useful commands

| Step | Command |
| --- | --- |
| Verify service URL | minikube service user-app --url |
| Check pod status | kubectl get pods |
| Get app logs | kubectl logs <pod-name> |
| Use port-forward (quick fix) | kubectl port-forward svc/user-app 8080:8080 |

	                        
	            
	            
	                
	


