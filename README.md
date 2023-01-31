# Kubernetes for beginners training by Bogdan Stashchuk

<br />

### Git repository for k8s-web-hello project

## Enable Kubernetes single-node cluster on Docker-Desktop 
* Kubernetes can be enabled from Kubernetes settings panel
* Check the Enable Kubernetes box and press Apply & Restart 
* (Optional) Check the Use Rosetta for x86/amd64 emulation on Apple Silicon box
* And Enable the virtualization framework in General panel then press Apply and Restart

<br />

## Get the Docker-Desktop node's ip address
    cat /etc/hosts
    # To allow the same kube context to work on the host and the container:
    127.0.0.1 kubernetes.docker.internal

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

### Get K8s cluster info
    kubectl cluster-info

### Get basic info about K8s components
    kubectl get node
    kubectl get pod
    kubectl get svc
    kubectl get all

<br />

### Get extended info about components
    kubectl get pod -o wide
    kubectl get node -o wide

<br />

### Get detailed info about a specific component
    kubectl describe svc {svc-name}
    kubectl describe pod {pod-name}

<br />

### Get application logs
    kubectl logs {pod-name}
    
<br />

## Install Kubernetes Dashboard 
* Deploy Kubernetes Dashboard yaml 
* Create a Service Account
* Create a ClusterRoleBinding
* Run kubectl proxy
* Get a Bearer Token
* Open the browser and navigate to URL
* Select Token and paste the token created earlier and press Sign In
* You are now logged in with an admin 

<br />

## Install Kubernetes Metric Server
* Install Helm
* Add metrics-server repository
* Create namespace metrics
* Install metrics-server helm chart and add the option --set args={"--kubelet-insecure-tls=true"}

<br />

### Get top pods and nodes
    kubectl top pods
    kubectl top node

<br />

## Stop and quit your Kubernetes cluster
* To pause or quit click on the Moby icon in Upper right corner and chose either pause or stop 

<br />
<br />

## Links
* Deploying Kubernetes Dashboard: https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/
* Accessing Kubernetes Dashboard: https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md
* Kubernetes Metrics-Server: https://github.com/kubernetes-sigs/metrics-server
* Kubernetes Metrics-Server Releases: https://github.com/kubernetes-sigs/metrics-server/releases
* k8s official documentation: https://kubernetes.io/docs/home/
* webapp code repo: https://github.com/AlexJDevil/k8s-web-hello
* webapp image on Docker Hub: https://hub.docker.com/repository/docker/alexjdevil/k8s-web-hello/general

