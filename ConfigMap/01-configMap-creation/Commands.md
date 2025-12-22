# Description:

Config map crea

You don’t really “deploy” a ConfigMap as such. It’s configuration, not part of the workload/workflow.

But you do apply the ConfigMap so it’s stored in etcd. From there, it’s made available to any Pods/containers that reference it.

# aby wyświetlić listę konfig map

    kubectl get cm

    kubectl describe cm app-properties


