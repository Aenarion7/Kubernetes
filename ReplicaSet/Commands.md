# Description:

In real life you will use deployments.

# Prerequisite:
    kubectl get nodes
    kind create cluster --config 01-cluster.yaml
    kubectl get nodes

CLuster is created

# Replica Set start:

    kubectl get pod

go to location of pod.yaml

    kubectl apply -f simple-rs.yaml

    kubectl get rs

    kubectl get pods -l app=my-app

