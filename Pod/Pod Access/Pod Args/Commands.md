# Description:

W Kubernetes command i args kontrolują, jaki proces uruchamia się w kontenerze i z jakimi parametrami.

W obrazie może być już entry point, więc wtedy wysyłasz tylko args z K8.

Bez budowania obrazu można:

command = co uruchomić (program) → jak Docker ENTRYPOINT
args = z czym uruchomić (argumenty) → jak Docker CMD

command: ["sleep"]
args: ["10"]
Uruchomi: sleep 10

lub:

image: ubuntu
command: ["ping"]
args: ["-c","3","8.8.8.8"]


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

### Entering POD:
    kubectl exec -it my-pod -- bash
    exit                            # it will not kill the pod

# Delete pods:
    kubectl delete -f 01-simple-pod.yaml
    kubectl delete pod/pod-3