# Description:

In real life you will use deployments.

### Base Resource Yaml format:
Pod Format documentation:

    https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/

# Prerequisite:
    kubectl get nodes
    kind create cluster --config 01-cluster.yaml
    kubectl get nodes

CLuster is created

# Pod creation:

    kubectl get pod

go to location of pod.yaml

    kubectl create -f 01-simple-pod.yaml
    kubectl get pod

# Delete pods:
    kubectl delete -f 01-simple-pod.yaml
    kubectl delete pod/pod-3