## Cluster Info and Configuration

- `kubectl version`: Provides details about the Kubernetes version for both the client and server.
- `kubectl cluster-info`: Shows the endpoint information of the Kubernetes control plane.
- `kubectl config get-contexts`: Displays all the available contexts in the current kubeconfig file.
- `kubectl config use-context <context name>`: Sets the default context for subsequent kubectl commands.

## Namespaces

Namespaces are crucial in Kubernetes clusters as they help organize and isolate the various resources your application may need. By default, you're working in the "default" namespace, while Kubernetes' own resources are located in the "kube-system" namespace. Here are some commonly used namespace-related commands:

- `kubectl get namespaces`: If you've created multiple namespaces and lost track, this command will list all existing namespaces.
- `kubectl create namespace <namespace name>`: Creates a new namespace but doesn't set it as the default. Without specifying the `--namespace` flag, resources will still be created in the default namespace.
- `kubectl config set-context --current --namespace=<namespace name>`: Changes the default namespace for your current context, so all kubectl commands will apply to that namespace by default. To switch back, remember the default namespace is called "default".
- `kubectl delete namespace <namespace name>`: Deletes the specified namespace along with **all its resources**. Note that deletion is asynchronous, so the namespace might remain in the "Terminating" state for a while.

## Pods, Deployments, Secrets, etc


