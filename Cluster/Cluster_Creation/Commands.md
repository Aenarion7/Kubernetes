# Description:

In real life you will use deployments.

create 01-cluster.yaml

To stop all containers:

    docker ps -a  
    docker system prune -f
To check what are the networks:

    docker network ls
To check whether there is any kubernetes configuration. If there is, delete it.

    ls ~/.kube

Create Kubernetes cluster. I will also download docker imagess and it will create docker images and K8 cluster.

    kind create cluster -- config 01-cluster.yaml

Check for docker containers:

    docker ps

    There should be: one master and two worker nodes.

check for brigne networks:

    docker network ls
    
    There should be new network

to view config:

    cat ~/.kube/config

    To tutaj znajdują się informacje o tym jak się komunikować z nodem. 
    To się dostarcza zespołą aby mogły nawiązaćkomunikacje/rozmawiać z wystawionym klastrem.

wyświetlenei wersji serwera

    kubectl version --output=yaml

    This means that kubectl is able to talk to master.

Wyświetlenie nodów:

    kubectl get nodes