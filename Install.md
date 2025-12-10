https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

# Install kubectl Linux:

### Download the latest release with the command:

    curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
    

### Install kubectl:

    sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
        
**Note:** If you do not have root access on the target system, you can still install kubectl to the ~/.local/bin directory. Check link on the top.
    
### Test to ensure the version you installed is up-to-date:

    kubectl version --client
