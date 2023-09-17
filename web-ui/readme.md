# Kubernetes Dashboard (Web UI)

Kubernetes Dashboard is a web-based user interface that provides a convenient way to interact with your Kubernetes cluster. With Dashboard, you can get an overview of the applications running on your cluster, create or modify Kubernetes resources, and monitor the state of resources and any errors that may occur.

## Configuration Steps

- Deploy the Kubernetes Dashboard UI

    To deploy the Kubernetes Dashboard UI, execute the following command:

    ```bash
    kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
    ```

- Create a New User

    Run the following command to create a new user for the Dashboard:

    ```bash
    kubectl apply -f dashboard-adminuser.yml
    ```

- Access the Dashboard UI

    Start a proxy server to access the Dashboard UI by running:

    ```bash
    kubectl proxy
    ```

- After starting the proxy, you can access the Dashboard UI at 

    ```bash
    http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/
    ```

- Obtain Authentication Token

    To log in to the Dashboard, you need an authentication token. Run the following commands to get the token and copy it to your clipboard:

    ```bash
    kubectl -n kube-system get secret
    ```

    >_All secrets with type `kubernetes.io/service-account-token` will allow to log in. Note that they have different privileges._

    Example Output:
    
    ```bash
    NAME                                TYPE                                  DATA    AGE
    deployment-controller-token-frsqj   kubernetes.io service-account-token   3       22h
    ```

    Modify the `service-account-name` accordingly
    
    ```bash
    kubectl -n kube-system describe secret deployment-controller-token-frsqj
    ```

    Copy the secret token to clipboard.
    
- Log In to the Dashboard

    Paste the token you obtained in the previous step into the login screen to access the Dashboard.

- Create Resources Using the Dashboard
    
    - To create Kubernetes resources via the Dashboard, follow these steps:
    
        - Click on the "+" button in the top right corner of the Dashboard.
        - Select "Upload YAML" and upload the `newDeploy.yml` manifest file.
        - This will create a new deployment resource in your cluster.

## Additional Configuration Steps

- Create Cluster Role Binding (Optional)

    If you want to grant cluster-admin privileges to the service accounts, you can create a cluster role binding with the following command:

    ```bash
    sudo kubectl create clusterrolebinding serviceaccounts-cluster-admin --clusterrole=cluster-admin --group=system:serviceaccounts
    ```

    >_This step is optional and provides elevated privileges to service accounts, allowing them to manage cluster resources. Please use caution when granting such privileges, and ensure that it aligns with your security policies and requirements._

## Useful Links

- [Deploying Dashboard UI](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/#deploying-the-dashboard-ui)

- [Creating a Sample User](https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md)

- [Official Dashboard Github Repository](https://github.com/kubernetes/dashboard/)

---

Thank you!
