Perform this before labs from this folder - to setup test environment

# Install kubectl Linux:
The Kubernetes command-line tool, kubectl, allows you to run commands against Kubernetes clusters.

https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

### Download the latest release with the command:

    curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
    

### Install kubectl:

    sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
        
**Note:** If you do not have root access on the target system, you can still install kubectl to the ~/.local/bin directory. Check link on the top.
    
### Test to ensure the version you installed is up-to-date:

    kubectl version --client


### Install Kind
Kind allows to run Kubernetes on local a computer.
Docker is required

https://kind.sigs.k8s.io/docs/user/quick-start/

    [ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.30.0/kind-linux-amd64

### Veryfie instalation

        kind version
        kubectl
        kubectl version --output=yaml