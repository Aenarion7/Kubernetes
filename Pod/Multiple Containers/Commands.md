# Description:




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

### Pod and Multiple containers commands

Check whether it has been created succesfully:

    kubectl get pod
    kubectl describe pod

If you see: Crash llop Backoff - that means that something went wrong

Check both containers logs:

    kubectl logs my-pod -c nginx-1
    kubectl logs my-pod -c vinsdocker/util

### connect to a specyfic container in a pod:

    kubectl exec -it my-pod -c util -- bash     #util is container name         # Host name will stay the same, (my-pod)



