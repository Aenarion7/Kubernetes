# Description:

Create simple deployment

kubectl create nie jest idempotentne, czyli nie jest świadome obecności już istniejących obiektów. Zwróci błąd, jeśli obiekt, który chcemy utworzyć, już istnieje.

kubectl apply jest idempotentne — utworzy obiekty, które jeszcze nie istnieją, a jeśli już istnieją, to zaktualizuje je tylko wtedy, gdy manifest YAML różni się od stanu w klastrze. Jeśli nie ma różnic, nic nie zmieni. Można powiedzieć, że apply “nakłada” zmiany (różnice) na istniejące zasoby. zostanie on utworzony, więc można powiedzieć że tworzy się różnica.

# Prerequisite:
    kubectl get nodes
    kind create cluster --config 01-cluster.yaml
    kubectl get nodes

CLuster is created

# deployment start:

    kubectl create -f 01-simple-deployment.yaml
    Lub
    kubectl apply -f 01-simple-deployment.yaml
   


