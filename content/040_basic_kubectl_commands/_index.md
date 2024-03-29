---
title: "3. Basic Kubectl Commands"
chapter: true
weight: 6
---

# Kubectl - Command Line Tool

Kubernetes provides a command line tool for communicating with a Kubernetes cluster's control plane, using the Kubernetes API.This tool is named kubectl. We can use kubectl to deploy applications, inspect and manage cluster resources, and view logs.

kubectl is installable on a variety of Linux platforms, macOS and Windows. Refer the below link to install kubectl, 

[Install Kubectl](https://kubernetes.io/docs/tasks/tools/)

:arrow_right: Connect to Kubectl Cluster
```
k3d kubeconfig get local-cluster > $HOME/.kube/localk8scluster.yaml
export KUBECONFIG="$HOME/.kube/localk8scluster.yaml"
```

:arrow_right: Client and Server version information
```
kubectl version
```

:arrow_right: Supported API versions on the server
```
kubectl api-versions
```

:arrow_right: List Resources
```
kubectl get nodes
kubectl get namespaces
kubectl get pods
```

:arrow_right: Deploy First Pod
```
kubectl run nginx --image=nginx
```

:arrow_right: Details of a specific resource
```
kubectl describe node <nodename>
kubectl describe pod <podname>
```


:arrow_right: Scaling and Deploying Applications
```
kubectl create deployment nginx --image=nginx --replicas=2
kubectl expose deployment/nginx --name=nginx-service --type=ClusterIP --port=80 --target-port=80
kubectl get services
kubectl port-forward service/nginx-service 9595:80
```
