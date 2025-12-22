# Description:

Jak wstrzyknąć pliki (wiele linni konfiguracji)

### sprawd

## Create config map

    kubectl apply -f 01-inject-cm-as-file.yaml
    kubectl get pod
    kubectl exec -it my-pod -- bash

go to localization and check whether file is present:

/usr/share/props


