# django-k8s-deployment
Simple Django project that runs with uWSGI, deployed on a Kubernetes cluster using Nginx Ingress Controller.


## ✅ PROJECT OVERVIEW

We'll create:

-   A Django project called `myapp`
    
-   Dockerfile to run it with `uWSGI`
    
-   Kubernetes manifests:
    
    -   Deployment
        
    -   Service
        
    -   Ingress
        
    -   ConfigMap (for uWSGI config)
        
    -   Secret (for Django secret key)
        
-   Instructions to deploy everything


## NGINX INGRESS CONTROLLER SETUP

Install via Helm:

	helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
	helm repo update

	helm install nginx-ingress ingress-nginx/ingress-nginx` 

----------

##  BUILD & PUSH DOCKER IMAGE

`docker build -t your-dockerhub-username/myapp:latest .
docker push your-dockerhub-username/myapp:latest` 

----------

##  APPLY K8S FILES

`kubectl apply -f k8s/configmap.yaml
kubectl apply -f k8s/secret.yaml
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl apply -f k8s/ingress.yaml` 

----------

##  ACCESS APP

Edit your `/etc/hosts` file:

`<external-ip-of-nginx-ingress> myapp.local` 

Then go to http://myapp.local in your browser.