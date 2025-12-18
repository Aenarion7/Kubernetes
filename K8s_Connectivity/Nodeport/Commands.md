# Description:

01-cluster - to manifest

host Linux:80 → (Docker port mapping) → kind node:30001

Service NodePort:30001 → nginx w Podach na porcie 80

# Uruchomienie:

    kind create cluster --config kind-config.yaml
    kubectl apply -f nginx.yaml

# test z hosta:

    curl -I http://localhost/

Powinieneś zobaczyć HTTP/1.1 200 OK i nagłówek Server: nginx.