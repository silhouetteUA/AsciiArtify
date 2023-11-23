# Minikube vs KIND vs K3D side-by-side comparison!

## General info:
Minikube, k3d, and kind are tools that facilitate the deployment and management of Kubernetes clusters, but they differ in their specific use cases and purposes.

Below is a simple  table comparing Minikube, K3d, and Kind based on certain aspects. Please note that this is a high-level overview:

| Feature          | Minikube                                      | K3d                                           | Kind                                          |
|------------------|-----------------------------------------------|------------------------------------------------|-----------------------------------------------|
| **Ease of Use**  | Easy to set up and use for local development. | Designed for simplicity and lightweight use.   | Quick and easy cluster creation for testing.  |
| **Footprint**    | Larger footprint due to VM-based deployment.  | Lightweight, suitable for edge and IoT devices.| Lightweight and ideal for testing purposes.   |
| **Installation** | Requires a hypervisor for VM deployment.      | Single binary installation, no VM required.    | Single binary installation, no VM required.  |
| **Features**     | Full Kubernetes implementation.               | Stripped-down, but covers essential features. | Focuses on simplicity, fewer advanced features.|
| **Performance**  | Slower due to VM overhead in local setups.    | Faster startup and operation in constrained environments. | Fast startup for testing and development.     |
| **Use Case**     | Suitable for local development and testing.  | Lightweight deployments, edge scenarios.      | Testing and development environments.        |
| **Community**    | Large and active community support.           | Growing community, especially in edge space.  | Well-supported for testing and development.  |
| **Maintainer**   | Maintained by the Kubernetes project.         | Maintained by Rancher Labs.                    | Maintained by the Kubernetes SIGs.           |
| **Documentation**| Well-documented with extensive resources.     | Good documentation, especially for edge use.  | Decent documentation for testing purposes.   |





### ***Minikube*** basic commands and demo


![](../.data/minikube_showcase.gif)


| Command                                   | Description                                          |
|-------------------------------------------|------------------------------------------------------|
| `minikube start`                          | Start a local Kubernetes cluster using Minikube.     |
| `minikube stop`                           | Stop the currently running Minikube cluster.         |
| `minikube status`                         | Show the status of the Minikube cluster.              |
| `minikube ip`                             | Get the IP address of the Minikube cluster.          |
| `minikube dashboard`                      | Open the Kubernetes dashboard in a web browser.      |
| `minikube ssh`                            | Log into the Minikube VM using SSH.                  |
| `minikube addons list`                    | List enabled and disabled addons for Minikube.       |
| `minikube addons enable <addon-name>`    | Enable a specific addon in the Minikube cluster.     |
| `minikube addons disable <addon-name>`   | Disable a specific addon in the Minikube cluster.    |
| `minikube delete`                         | Delete the Minikube cluster.                         |
| `minikube config set <key> <value>`      | Set a configuration key for Minikube.                |
| `minikube config get <key>`               | Get the value of a specific configuration key.       |
| `minikube logs`                           | Show the logs of the Minikube cluster.               |
| `minikube service <service-name>`         | Open a service in a web browser via a NodePort.      |
| `minikube kubectl -- <kubectl-command>`   | Run a kubectl command against the Minikube cluster.  |
| `minikube update-check`                   | Check for updates to Minikube.                       |
| `minikube update`                         | Update Minikube to the latest version.               |
| `minikube help`                           | Display help information for Minikube.              |





### ***KIND*** basic commands and demo


| Command                                           | Description                                           |
|---------------------------------------------------|-------------------------------------------------------|
| `kind create cluster`                              | Create a new Kubernetes cluster using Docker.          |
| `kind delete cluster`                              | Delete the currently active Kind cluster.              |
| `kind get clusters`                                | List all the clusters managed by Kind.                 |
| `kind export kubeconfig --name <cluster-name>`     | Export the kubeconfig file for a Kind cluster.         |
| `kind load docker-image <image-name>`              | Load a Docker image into nodes of the Kind cluster.    |
| `kind build node-image --name <cluster-name>`       | Build a custom node image for a Kind cluster.          |
| `kind create node --name <cluster-name>`           | Add an additional node to an existing Kind cluster.    |
| `kind get nodes --name <cluster-name>`             | List all nodes in a Kind cluster.                      |
| `kubectl cluster-info --context kind-<cluster-name>`| Display cluster information for a specific Kind cluster.|
| `kubectl config use-context kind-<cluster-name>`    | Set the current kubectl context to a Kind cluster.     |

**Note:** Replace `<cluster-name>` with the actual name of your Kind cluster.

These commands cover the basics of creating, managing, and interacting with Kind clusters. You can refer to the official Kind documentation for more advanced options and configurations: [Kind Documentation](https://kind.sigs.k8s.io/docs/user/quick-start/).





### ***K3d*** basic commands and demo



| Command                                         | Description                                   |
|-------------------------------------------------|-----------------------------------------------|
| `k3d cluster create <cluster_name>`              | Create a new k3s cluster with the given name. |
| `k3d cluster list`                               | List all running k3s clusters.                |
| `k3d cluster delete <cluster_name>`              | Delete the specified k3s cluster.            |
| `k3d node list`                                  | List nodes in the default cluster.            |
| `k3d kubeconfig get <cluster_name>`              | Get the kubeconfig file for the cluster.      |
| `k3d kubeconfig switch <cluster_name>`           | Switch the current kubeconfig context.        |
| `k3d kubeconfig merge <cluster_name> -d`         | Merge the cluster kubeconfig into the default kubeconfig file. |
| `k3d image import <cluster_name> <image>`        | Import a Docker image into the k3s cluster.   |
| `k3d registry create <registry_name>`            | Create a Docker registry in a k3s cluster.    |
| `k3d registry list`                              | List Docker registries in running clusters.   |
| `k3d registry delete <registry_name>`            | Delete a Docker registry from a k3s cluster.  |
| `k3d load balancer create <lb_name>`             | Create a load balancer for a k3s cluster.     |
| `k3d load balancer list`                         | List load balancers in running clusters.      |
| `k3d load balancer delete <lb_name>`             | Delete a load balancer from a k3s cluster.    |
| `k3d version`                                   | Display the k3d version.                      |
| `k3d --help`                                    | Display help information for k3d.             |


