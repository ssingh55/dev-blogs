In this short post, we will demonstrate how to install kubectl, setup up auto-completion, and set an alias for kubectl in your bash shell.

When using kubectl commands to interact with your Kubernetes cluster (K8S), auto-completion can be very useful to avoid having to reference a cheat sheet constantly!

Setting an alias for kubectl on the command line, (commonly as k ), also helps save a lot of time when managing your cluster, and is also recommended for the CKA administrator exam as it is very time limited.

## Install Kubectl on Linux

1. Open your bash shell. Type kubectl. If you see the message ‘kubectl: command not found’, follow these steps to install kubectl. If it is installed, skip to Step 7.
    ```
    Command 'kubectl' not found, but can be installed with:
    sudo snap install kubectl
    ```
2. Download the latest kubectl release with the command:
    `curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"`
3. Download the checksum file:
    `curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"`
4. Validate the kubectl binary against the checksum file:
    `echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check`
5. Install kubectl:
    `sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl`
![Kubectl Install](./assets/kubectl-install.png)

## Set up Auto-completion

7. Check if bash-completion is already installed:
    `type _init_completion`
    If it is already installed, you will see something like the following:
    ![Init Completion](./assets/init_completion.png)
    
    If it is not installed, install using apt or yum, depending on which package manager you are using (usually apt for Ubuntu):

    `apt-get install bash-completion`

8. Set the kubectl completion script source for your shell sessions:
    For all users on the system:
    `kubectl completion bash | sudo tee /etc/bash_completion.d/kubectl > /dev/null`

9. Reload your bash shell. Type kubectl - followed by pressing tab twice to see the available options and verify auto-complete is working:

![kubectl bash completion](./assets/kubectl-bash-completion.png)

## Set Up an Alias for Kubectl and Enable for Auto-completion

10. Set an alias for kubectl as k.

`echo 'alias k=kubectl' >>~/.bashrc`

11. Enable the alias for auto-completion.

`echo 'complete -o default -F __start_kubectl k' >>~/.bashrc`

12. Reload your bash shell. Type k - followed by pressing tab twice to see the available options and verify auto-complete is working with the alias.

`k -`

## Summary

Enabling auto-completion for kubectl and setting an alias will save you time!