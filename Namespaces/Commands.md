### Komendy show:

    kubectl get namespaces
    kubectl get ns
    kubectl get pod -n dev
    kubectl get all -n dev

view system components:

    kubectl get pod -n kube-system

Są domyślne namespacy zarezerwowane dla systemu w kubernetes.

### Tworzenie namespace

    kubectl create ns dev

### Tworzenie wszystkich zasobów z lokalizacji z danej namespace

    kubectl apply -f . -n dev


### Deployowanie na dany namespace

    kubectl apply -f 01-simple-deployment.yaml -n dev

### Mapowanie portu dla serwisu (aplikacji) w namespace:

    kubectl port-forward svc my-app 8080:80 -n dev   #svc to serwis

### kasowanie namespace i wszystkich zasobów w danym namespace

    kubectl delete ns dev

