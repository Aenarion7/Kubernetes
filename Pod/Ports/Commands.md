# Description:

1. Port expose in pod yaml file
2. Port forwarding
    It forwards your local port 8080 to port 80 inside the pod my-pod in the cluster.
    
    On your local machine you connect to:
    http://localhost:8080
    
    But the traffic actually goes to:
    my-pod:80 in Kubernetes:

    [LOCAL] 8080  --->  [POD my-pod] 80

It is not the proper way to serve traffic; it is only useful for debugging.

### Base Resource Yaml format:
Pod Format documentation:

    https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/

## Prerequisite:
    kubectl get nodes
    kind create cluster --config 01-cluster.yaml
    kubectl get nodes

CLuster is created

## Pod creation:

    kubectl get pod

go to location of pod.yaml

    kubectl create -f 01-simple-pod.yaml
    kubectl get pod

### Part 2, port forwarding:

    kubectl port-forward my-pod 8080:80

## Delete pods:
    kubectl delete -f 01-simple-pod.yaml
    kubectl delete pod/pod-3