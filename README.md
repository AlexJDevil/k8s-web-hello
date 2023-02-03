# Kubernetes for beginners training

<br />

## Enable Kubernetes single-node cluster on Docker-Desktop 
* Kubernetes can be enabled from Kubernetes settings panel
* Check the Enable Kubernetes box and press Apply & Restart 
* (Optional) Check the Use Rosetta for x86/amd64 emulation on Apple Silicon box
* And Enable the virtualization framework in General panel then press Apply and Restart

<br />

## Get the Docker-Desktop node's ip address
```yaml
cat /etc/hosts
# To allow the same kube context to work on the host and the container:
127.0.0.1 kubernetes.docker.internal
```
<br />

## Project Overview
* Create a new deployment for our node.js application, named k8s-web-hello
* This application contains one route
```yaml
  '/'
```
* We are exposing this deployment using a service type LoadBalancer
* Using LoadBalancer will enable connecting using the LoadBalancer IP address

<br />

## Application manifest files
```yaml
application/index.mjs
application/package.json
application/package-lock.json
```
<br />

## Docker manifest files
```yaml
application/Dockerfile
```
<br />

## K8s manisfest files
```yaml
deployment/deployment.yaml
deployment/service.yaml
``` 

<br />

## Docker commands

<br />

### Build and push the image to Docker Hub
```yaml
docker build . -t alexjdevil/k8s-web-hello:v1.0
docker push alexjdevil/k8s-web-hello:v1.0
```
<br />

## K8s commands

<br />

### Get K8s cluster info
```yaml    
kubectl cluster-info
```

<br />

### Get basic info about K8s components
```yaml
kubectl get node
kubectl get pod
kubectl get svc
kubectl get all
kubectl delete all -all
```
<br />

### Get extended info about components
```yaml
kubectl get pod -o wide
kubectl get node -o wide
```

<br />

### Get detailed info about a specific component
```yaml
kubectl describe svc {svc-name}
kubectl describe pod {pod-name}
```

<br />

### Get application logs
```yaml
kubectl logs {pod-name}
```
<br />

## Deploy everything
* Apply deployment and service yaml's
```yaml
  kubectl apply -f ./deployment/deployment.yaml
  kubectl apply -f ./deployment/service.yaml
```
* Confirm the deployment, pods and service were created and started
```yaml
  kubectl get pods -n default
  kubectl get services -n default
```
* Check deployment and service details
```yaml
  kubectl describe deployment deployment
  kubectl describe service 
```
* Access the Application endpoint
```yaml
  http://localhost:3030
```
<br />

### Clean up everything
```yaml
kubectl delete -f deployment/deployment.yaml
kubectl delete -f deployment/service.yaml 
```

<br />

## Stop and quit your Kubernetes cluster
* To pause or quit click on the Moby icon in Upper right corner and chose either pause or stop 

<br />

## Links
* K8s official documentation: https://kubernetes.io/docs/home/
* Application code repo: https://github.com/AlexJDevil/k8s-web-hello
* Application image on Docker Hub: https://hub.docker.com/repository/docker/alexjdevil/k8s-web-hello/general

