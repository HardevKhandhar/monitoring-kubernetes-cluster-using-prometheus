# Monitoring Kubernetes Cluster using Prometheus and Grafana

This repository provides a comprehensive set of resources and configurations to monitor a Kubernetes cluster using Prometheus and Grafana and manage it through a web-based dashboard.

## Introduction

Modern cloud-native applications often run in Kubernetes clusters, providing scalability, reliability, and flexibility. However, managing these clusters and ensuring their health and performance can be challenging. This project aims to simplify Kubernetes cluster management by providing monitoring capabilities through Prometheus and Grafana and a user-friendly web-based dashboard.

## Why Kubernetes Monitoring and Dashboard?

- **Improved Cluster Health Visibility**

    Kubernetes Monitoring allows you to gain real-time insights into your cluster's health, ensuring that your applications are running smoothly and efficiently.

- **Streamlined Troubleshooting**

    Monitor metrics, logs, and application performance, making it easier to identify and resolve issues quickly.

- **Scalability Management**

    Effortlessly scale your applications based on actual usage patterns and resource consumption data.

- **Resource Optimization**

    Optimize resource allocation by identifying underutilized or over-provisioned resources.

## Project Structure

The project is organized into the following directories:

- `deployment`: Contains Kubernetes deployment configurations for your applications.

- `prometheus-grafana`: Includes Prometheus and Grafana configurations for monitoring.

- `web-ui`: Contains resources and instructions for setting up the Kubernetes Dashboard.

Please refer to the respective directories for detailed documentation on each component.

## Benefits

- **Simplified Management**: Easily manage your Kubernetes cluster without the need for extensive command-line expertise.

- **Efficient Resource Usage**: Optimize resource allocation for cost-effective operation.

- **Quick Troubleshooting**: Quickly identify and resolve issues to maintain high availability.

- **User-Friendly Dashboard**: Access critical cluster information through an intuitive web-based interface.

## Directory Structure

```bash
.
├── deployment
│   ├── deployment.yml
│   ├── README.md
│   └── service.yml
├── prometheus-grafana
│   ├── grafana
│   │   ├── configmap.yaml
│   │   ├── deployment.yaml
│   │   ├── README.md
│   │   └── service.yaml
│   ├── kube-state-metrics
│   │   ├── cluster-role-binding.yaml
│   │   ├── cluster-role.yaml
│   │   ├── deployment.yaml
│   │   ├── service-account.yaml
│   │   └── service.yaml
│   ├── metrics-server
│   │   ├── components.yaml
│   │   └── README.md
│   ├── prometheus.deployment.yml
│   └── README.md
├── README.md
└── web-ui
    ├── dashboard-adminuser.yml
    ├── newDeploy.yml
    └── readme.md
```

## Cluster Creation Steps

Before you start monitoring your Kubernetes cluster and using the dashboard, you'll need to create a Kubernetes cluster.

### Step 1: Create a Kubernetes Cluster

Use the following command to create a Kubernetes cluster using [kind](https://kind.sigs.k8s.io/):

```bash
kind create cluster
```

### Step 2: Check Cluster

Verify that your cluster has been created by running:

```bash
kind get clusters
```

### Step 3: Get Cluster Info

To access cluster information, including the API server URL, use:

```bash
kubectl cluster-info
```

### Step 4: Check Nodes

Confirm that the cluster nodes are up and running with:

```bash
kubectl get nodes
```

### Step 5: Check All Resources

Check all resources across namespaces with:

```bash
kubectl get all -A
```

Now that you have a running Kubernetes cluster, you can proceed to set up monitoring and access the Kubernetes Dashboard as per the instructions provided in the respective directories.

---

Thank you!
