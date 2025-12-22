# Description:

How to get the config map values in to the pod.

Only selected key pairs. You can also inject all from a selected file.

All in one YAML file, but the ConfigMap can be in a separate file from the Pod YAML.

# Config:

    kubectl apply 01-simple-configmap.yaml
    kubectl get pod
    kubectl logs my-pod

