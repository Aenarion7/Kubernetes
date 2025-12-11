How to perform connection to Master or Worker nodes:

Check existing containers

    docker ps

Connect to the node:

    docker exec -it <container_id> bash

    Connection established!

Sprawdzenie komponentów:

    cd /etc/kubernetes/manifests/
    ls -l

check processes what kubernetes processes are running:

    ps -aux

In worker node lista procesów jest mniejsza





