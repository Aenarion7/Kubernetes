# Check Cluster Operation:

### Whether [kube-apiserver] works: 
**Without apiserver:**
- Kubectl commands don't work.
- Scheduler can't schedule pods.
- Controllers can't update anything:

        kubectl cluster-info
    If API server works, you will see something like:

        Kubernetes control plane is running at https://127.0.0.1:6443
    Otherwise:
        
        The connection to the server 127.0.0.1:6443 was refused
 


### Informacje o podach 
    kubectl describe pod
    kubectl get pod
    kubectl ger pod pod-1
    kubectl get pod --show-labels
    kubectl get pod -l dept=dept-1
    kubectl get pod -l dept!=dept-1
    kubectl get pod -l dept=dept-1,team=team-a
    kubectl get pod -o wide             - more info 
Jeśli nie masz pliku yaml, np. ktoś inny stworzył Poda:
    kubectl get pod pod-1 -o yaml

### Running containers
