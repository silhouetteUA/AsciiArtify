# Minimum Viable Product (MVP): AsciiArtify

## Purpose:
The general idea behind MVP is to deploy AsciiArtify application using the ArgoCD and showcase its capabilities. ArgoCD is going to use local Minikube installation as its destination to deploy AsciiArtify application and synchronise it with the remote GIT repository (https://github.com/den-vasyliev/go-demo-app)

## Ways to create and manage your app using ArgoCD

ArgoCD provides several ways to create and manage applications. Here are the primary methods:

### 1.**Declarative Application Management:**

-   **Description:** Declare the desired state of your applications using Git repositories. ArgoCD continuously monitors the repositories and ensures the cluster state matches the declared state.
    
-   **Steps:**
    
    1.  Define your application manifests in a Git repository.
    2.  Create an ArgoCD Application CR or use the CLI to create an application.
    3.  ArgoCD will automatically sync the cluster with the Git repository.
    
### 2. **CLI-Based Application Management:**

-   **Description:** Use the ArgoCD CLI to create and manage applications by providing commands and flags.
    
-   **Steps:**
    
    1.  Run `argocd app create` command to create an application.
    2.  Specify application details and synchronization parameters.
    3.  Monitor the application status using `argocd app get`.

### 3. **UI-Based Application Management:**

-   **Description:** Use the ArgoCD web UI to create and manage applications through a graphical interface.
    
-   **Steps:**
    
    1.  Open the ArgoCD web UI.
    2.  Navigate to the "Applications" tab.
    3.  Click on the "New Application" button.
    4.  Fill in the application details, repository URL, and sync options.
    5.  Save the application.
-   **Example:** [ArgoCD Web UI](https://argoproj.github.io/argo-cd/getting_started/#2-access-the-argo-cd-ui)


## Which way best fits for you?

Choose the method that best fits your `workflow` and `preferences`. Arguably, the **declarative** approach using Git repositories aligns closely with the GitOps philosophy promoted by ArgoCD.

## Benefits of declarative approach

The declarative approach in ArgoCD, as in GitOps workflows, has several benefits that contribute to a more reliable, auditable, and scalable application deployment and management process. Here are some key advantages:

1.  **Immutable Infrastructure:**
    
    -   **Description:** Declarative configurations define the desired state of the entire application stack.
    -   **Benefits:** This promotes the concept of immutable infrastructure, where changes are made by updating the declarative configuration rather than modifying live systems. This enhances stability and reproducibility.
2.  **Version Control:**
    
    -   **Description:** Declarative configurations are stored in version-controlled repositories (e.g., Git).
    -   **Benefits:** This provides a complete audit trail of changes, allows for easy rollbacks, and supports collaboration among teams. Version control helps maintain a historical record of changes and facilitates collaboration in a multi-user environment.
3.  **Consistent Environments:**
    
    -   **Description:** Declarative configurations ensure consistency between different environments (e.g., development, staging, production).
    -   **Benefits:** By using the same configuration across environments, you reduce the risk of configuration drift and improve the reliability of your applications. Environments are more likely to behave consistently, reducing the chance of unexpected issues.
4.  **Predictable Rollouts:**
    
    -   **Description:** ArgoCD continuously monitors the declared state and automatically syncs the cluster to match it.
    -   **Benefits:** This ensures that the cluster is always in the desired state, making rollouts predictable and reducing the risk of manual errors during deployments. Automatic synchronization simplifies the management of resources.
5.  **Efficient Rollbacks:**
    
    -   **Description:** Rollbacks involve reverting to a previous version of the declarative configuration.
    -   **Benefits:** In the event of issues or errors, rolling back is as simple as pointing ArgoCD to a previous version of the configuration. This process is quick, reliable, and helps minimize downtime.
6.  **Scalability:**
    
    -   **Description:** Declarative configurations are easily scalable to manage large and complex applications.
    -   **Benefits:** The declarative approach scales well as the application grows. It's easier to manage and maintain configurations for a diverse set of microservices or components, making it well-suited for modern, distributed architectures.
7.  **Infrastructure as Code (IaC):**
    
    -   **Description:** Declarative configurations can be treated as code and follow Infrastructure as Code (IaC) principles.
    -   **Benefits:** This aligns with modern DevOps practices, enabling infrastructure changes to be managed, tested, and versioned just like application code. It facilitates collaboration between development and operations teams.
8.  **Security and Compliance:**
    
    -   **Description:** Declarative configurations can include security and compliance policies.
    -   **Benefits:** By defining security policies in the configuration, you can ensure that security practices are consistently applied. This helps in meeting compliance requirements and maintaining a secure infrastructure.
9.  **Ease of Collaboration:**
    
    -   **Description:** Declarative configurations are text files that can be easily reviewed and collaborated on by team members.
    -   **Benefits:** This promotes collaboration among team members, encourages code reviews, and facilitates knowledge sharing. The text-based nature of configurations makes it accessible to both developers and operations teams.

In summary, the declarative approach in ArgoCD aligns well with the principles of GitOps and provides a robust foundation for managing Kubernetes applications, offering benefits in terms of consistency, reliability, scalability, and collaboration.

## Showcase: Declarative approach


