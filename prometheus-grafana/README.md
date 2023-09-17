# Prometheus, Kube-State-Metrics, Metrics Server, and Grafana

This directory contains resources and instructions for setting up Prometheus, Kube-State-Metrics, Metrics Server, and Grafana for monitoring a Kubernetes cluster.

## Installation and Setup

Follow these steps to set up monitoring for your Kubernetes cluster:

- Create a `monitoring` namespace by running the following command:

   ```bash
   kubectl create namespace monitoring
   ```

- Deploy the monitoring resources using the following command:

   ```bash
   kubectl create -f ./ -R
   ```

- Obtain the IP address of a worker node in your cluster. You can use the following command:

   ```bash
   kubectl get nodes --selector=kubernetes.io/role!=master -o jsonpath={.items[*].status.addresses[?(@.type=="InternalIP")].address}
   ```

- Visit `http://[NODEIP]:30000` in your web browser to access the Prometheus dashboard.

- In the Prometheus dashboard, click on the "Graph" tab. Select a metric from the drop-down menu (next to the "Execute" button), and then click "Execute." 

- You can switch between the "Graph" view and "Console" view to explore metrics further.

>_Note: The Metrics Server YAML can be modified to run in simpler Kubernetes scenarios, such as Docker Desktop._

## Removing Resources

To remove all the monitoring resources, run the following command:

   ```bash
   kubectl delete -f ./ -R
   ```

## Additional Details

- For more details on Prometheus, refer to the official Prometheus documentation: [Prometheus Documentation](https://prometheus.io/docs/prometheus/latest/getting_started)

- Additional information on setting up Prometheus monitoring on Kubernetes can be found at: [Setup Prometheus Monitoring on Kubernetes](https://devopscube.com/setup-prometheus-monitoring-on-kubernetes)

- A list of pod metrics provided by kube-state-metrics can be found in the kube-state-metrics documentation: [Pod Metrics](https://github.com/kubernetes/kube-state-metrics/blob/master/docs/pod-metrics.md)

---

Thank you!
