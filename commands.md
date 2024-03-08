# Install
- https://minikube.sigs.k8s.io/docs/start/
- https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/#install-nonstandard-package-tools

# Setup
- kubectl cluster-info
- minikube start/status
- minikube dashboard

# Cluster,Deployment
- kubectl create deployment my-nginx --image=nginx:latest
- kubectl get deployments
- kubectl get pods
- kubectl delete deployment my-nginx
- kubectl expose deployment my-nginx --port=80 --type=LoadBalancer
- kubectl get services
- minikube service my-nginx
- docker push 8001040511/project-ice:tagname
- kubectl create deployment sod --image=8001040511/sod-backend:4.0.0

## Rollout / update
- create new version and image push to docker-hub
- kubectl set image deployment sod sod-backend=8001040511/sod-backend:5.0.0
- kubectl rollout status deployment sod

## Rollback / revert
- kubectl set image deployment sod sod-backend=8001040511/sod-backend:11.0.0 , wrong version that does not exist
- kubectl rollout undo deployment sod

## Auto healing

## Scale up
- kubectl scale deployment test --replicas=4 ,scale up
- kubectl scale deployment test --replicas=2 ,scale down

## config 
- kubectl apply -f service-sod.yml
- kubectl apply -f deployment-sod.yml
- service-name:port for url
- kubectl get pc
- kubectl get pv
- kubectl get pvc