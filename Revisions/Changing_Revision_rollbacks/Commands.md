# Description:
Zmiana w manifeście niekoniecznie oznacza nową rewizję. 
- np. zmiana ilości replicas nie wprowadza nowej rewizji
- Modyfikacja pod template spec to nowa rewizja (czyli zmina konfiguracji aplikacji)

Jak wygląda rollout (RollingUpdate)

Domyślnie Deployment ma strategię RollingUpdate:
- tworzy nowy ReplicaSet (nowa wersja),
- podnosi liczbę Podów w nowym RS i jednocześnie zdejmuje Pody ze starego RS,
- parametry sterujące tempem:
    - maxSurge – ile “nadmiarowych” Podów można dodać ponad docelową liczbę
    - axUnavailable – ile Podów może być chwilowo niedostępnych

Druga strategia to Recreate: ubija stare Pody i dopiero tworzy nowe (brak “płynnego” przejścia).

1. Create simple deployment
2. Apply new revision

Plik 01, 02 oraz03 umieszczone w osobnych plikach aby pokazać zmianę
# Prerequisite:
    kubectl get nodes
    kind create cluster --config 01-cluster.yaml
    kubectl get nodes

CLuster is created

# deployment start:

    kubectl create -f 01-simple-deployment.yaml

Aktualizacja aplikacji:

    kubectl apply -f 02-simple-deployment.yaml
   
# Rollout

    kubectl rollout history deploy

Sprawdź czy są replica sets. Jeśli masz to po wykonaniu komendy, zmieni się wykorzystanie replica setów. Aplikacja wraca do starszej wersji

    kubectl rollout undo deploy/01-service

    kubectl rollout history deploy

Jeśli miałeś np Revision 1,2,3 to po rollbacku będzie to tak: 1,3,4. Wersja 2 stanie sięwersją 4.

Uwaga: teraz kolejny rollout spowodowałby powrót do 3! Czyli wielokrotne undu robi pętlę.

# Rollowanie do właściwej wersji:

    kubectl rollout undo deploy/order-service-deploy --to-revision=1
    kubectl rollout history deploy

# Checking Rollout Changes details

    kubectl rollout history deploy --revision=3



