# Kubernetes for beginners training by Bogdan Stashchuk

<br />
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
```yaml
    kubectl get node
    kubectl get pod
    kubectl get svc
    kubectl get all
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
<br />

## Install Kubernetes Dashboard 
* Deploy Kubernetes Dashboard yaml
  
  wget https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
  kubectl apply -f ./recommended.yaml
  
* Create a Service Account
  ```yaml
  kubectl apply -f ./adminuser.yaml

* Create a ClusterRoleBinding
  ```yaml
  kubectl apply -f ./dashboard-adminuser.yaml

* Get a Bearer Token
  ```yaml
  kubectl -n kubernetes-dashboard create token admin-user

* Run kubectl proxy
  ```yaml
  kubectl proxy

* Open the browser and navigate to URL
  ```yaml
  https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/

* Select Token and paste the token created earlier and press Sign In
* You are now logged in with an admin 

<br />
<br />

## Install Kubernetes Metric Server
* Install Helm
  ```yaml
  brew update
  brew install helm

* Add metrics-server repository
  ```yaml
  helm repo add metrics-server https://kubernetes-sigs.github.io/metrics-server/
  helm repo update

* Create namespace metrics
  ```yaml
  kubectl create namespace metrics

* Install metrics-server helm chart
  ```yaml
  helm install metrics-server metrics-server/metrics-server --version 3.8.3 --namespace metrics --set args={"--kubelet-insecure-tls=true"}

* Check the rollout status
  ```yaml
  kubectl -namespace metrics rollout status deployment metrics-server

* Check the pods
  ```yaml
  kubectl get pods --namespace metrics

<br />

### Get top pods and nodes
```yaml
    kubectl top pods
    kubectl top node
```
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

