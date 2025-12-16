# Description:

Recreate to strategia rolloutu Deploymentu, w której Kubernetes nie trzyma jednocześnie starej i nowej wersji.

Co dokładnie się dzieje: 

1) Gdy zmienisz spec.template (np. obraz):

2) Deployment skaluje stary ReplicaSet do 0 → wszystkie Pody starej wersji są wyłączane/usuwane.

3) Dopiero potem tworzy nowy ReplicaSet i skaluje go do docelowej liczby replik (u Ciebie: do 3).

- Efekt w trakcie rolloutu (dla 3 replik) jest zwykle taki:

    - przez chwilę masz 3 → 2 → 1 → 0 (stara wersja),

    - potem 0 → 1 → 2 → 3 (nowa wersja),

czyli jest luka w dostępności (downtime), chyba że ruch nie jest krytyczny albo masz zewnętrzny mechanizm przełączenia.

- Kiedy ma sens

    - Aplikacja nie może mieć dwóch wersji naraz (np. konflikt migracji, locki, jedyny writer, problemy ze zgodnością).

    - Nie przeszkadza Ci krótka przerwa lub masz bufor (kolejka, retry, maintenance window).

    - Chcesz najprostszy model aktualizacji.

# Prerequisite:
    kubectl get nodes
    kind create cluster --config 01-cluster.yaml
    kubectl get nodes

CLuster is created

# deployment start:

    kubectl create -f 04-simple-deployment-recreate.yaml

# Recreate:
    kubectl apply -f 05-simple-deployment-recreate.yaml

Wszystkie pody zostały zamknięte i utworzone ponownie. Dobre gdy mamy downtime na aktualizacje a aplikacja nie dobrze obsługuje różne wersje aplikacji
