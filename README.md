# Kubernetes for beginners training by Bogdan Stashchuk

<br />

### Git repository for k8s-web-hello project

<br />

## Application manifest files
* index.mjs
* package.json
* package-lock.json

<br />

## K8s manisfest files
* 
*
*
*

<br />

## Docker manifest files
* Dockerfile

<br />

## K8s commands

<br />

### start Minikube and check status
    minikube start --vm-driver=hyperkit 
    minikube status

<br />

### get minikube node's ip address
    minikube ip

<br />

### get basic info about k8s components
    kubectl get node
    kubectl get pod
    kubectl get svc
    kubectl get all

<br />

### get extended info about components
    kubectl get pod -o wide
    kubectl get node -o wide

<br />

### get detailed info about a specific component
    kubectl describe svc {svc-name}
    kubectl describe pod {pod-name}

<br />

### get application logs
    kubectl logs {pod-name}
    
<br />

### stop your Minikube cluster
    minikube stop

<br />

> <mark>Warning:</mark> **Known issue - Minikube IP not accessible** 

<br />

If you can't access the NodePort service webapp with `MinikubeIP:NodePort`, execute the following command:
    
    minikube service webapp-service

<br />

## Links
* mongodb image on Docker Hub: https://hub.docker.com/_/mongo
* webapp image on Docker Hub: https://hub.docker.com/repository/docker/nanajanashia/k8s-demo-app
* k8s official documentation: https://kubernetes.io/docs/home/
* webapp code repo: https://gitlab.com/nanuchi/developing-with-docker/-/tree/feature/k8s-in-hour

