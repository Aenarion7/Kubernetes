# Description:

Create simple deployment

Tworzymy serwis dostępowy do nginx który działa jak load balancer

Dodatkowo tworzymy poda testowego do testów



# Prerequisite:
    kubectl get nodes
    kind create cluster --config 01-cluster.yaml
    kubectl get nodes

CLuster is created

# deployment start:

W lokacji z plikami .yaml:

    kubectl create -f .
   
    kubectl describe service nginx_access       # lub svc
   
    kubectl exec it demo-pod -- bash

    curl my-app         # wykonaj kilka razy, zmienia się nazwa hosta i widać LB ale to nei jest round robin tylko random.

