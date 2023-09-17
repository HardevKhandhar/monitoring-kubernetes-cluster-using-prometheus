# Metrics Server

Metrics Server is a cluster-wide aggregator of resource usage data for Kubernetes clusters. It collects and serves resource metrics such as CPU and memory usage, which are essential for autoscaling and monitoring purposes.

## Metrics Server Installation Steps

To install Metrics Server in your Kubernetes cluster, follow these steps:

1. Download the `components.yaml` file locally by running the following command:

    ```bash
    wget https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
    ```

   This file contains the configuration settings required for Metrics Server deployment.

2. Open and modify the `components.yaml` file using your preferred text editor. For example, you can use `vim`:

    ```bash
    vim components.yaml
    ```

3. Inside the text editor (e.g., `vim`), locate the `args` section under the `containers` section within the `deployment` configuration. Add the following argument:

    ```yaml
    --kubelet-insecure-tls
    ```

## References

[Metrics Server (GitHub)](https://github.com/kubernetes-sigs/metrics-server)

---

Thank you!
