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
 
### Connection to a pod/deployment

    kubectl exec -it deploy/my-deploy -- bash

### Informacje o kind: pod/ReplicaSet/Deployment/StatefulSet/DaemonSet/Job/CronJob/Node/Namespace itd.
    kubectl describe kind
    kubectl get kind
    kubectl ger pod pod-1
    kubectl get pod --show-labels
    kubectl get pod -l dept=dept-1
    kubectl get pod -l dept!=dept-1
    kubectl get pod -l dept=dept-1,team=team-a
    kubectl get pod -o wide             - more info 
Jeśli nie masz pliku yaml, np. ktoś inny stworzył Poda:
    kubectl get pod pod-1 -o yaml

### Logs

Logi z Poda:

    kubectl logs <pod-name>

Z konkretnym namespace:

    kubectl logs -n <namespace> <pod-name>

Logi z wybranego kontenera:

    kubectl logs <pod-name> -c <container-name>

Podgląd na żywo:

    kubectl logs -f <pod-name>

Zakres czasu:

    kubectl logs <pod-name> --since=10m
    kubectl logs <pod-name> --since-time=2025-12-16T10:00:00Z