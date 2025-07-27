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