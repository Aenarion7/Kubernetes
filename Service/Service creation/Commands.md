# Description:

Create simple deployment

Tworzymy serwis dostępowy do nginx

# Prerequisite:
    kubectl get nodes
    kind create cluster --config 01-cluster.yaml
    kubectl get nodes

CLuster is created

# deployment start:

W lokacji z plikami .yaml:

    kubectl create -f .
   
    kubectl describe service nginx_access       # lub svc
   
IP - stały IP przypisanyu
Endpoints - poprzez sprecyzowanie Selector - mamy przypisane endpointy

    kubectl get pod -o wide

Zauważ że endpointy zmieniają sie dynamicznie w serwisie, np stworzony nowy pod, zostanie automatycznie dodany


