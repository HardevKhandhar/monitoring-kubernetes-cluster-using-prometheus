# Kubernetes Deployment

This directory contains Kubernetes Deployment configuration files for deploying your application within a Kubernetes cluster. Below are the steps to deploy your application using these YAML manifests.

## Step 1: Analyze YAML Manifest

Before deploying your application, it's essential to understand the content of the YAML manifest file (`deployment.yml`). You can view its contents using the following command:

```bash
cat deployment.yml
```

## Step 2: Deploy the Manifest

To deploy your application to your Kubernetes cluster, use the following command:

```bash
kubectl apply -f deployment.yml
```

Executing this command instructs Kubernetes to create the deployment based on the specifications in your YAML manifest.

## Step 3: Check Deployment Status

To check the status of your deployment and ensure it's running smoothly, use the following command:

```bash
kubectl get deploy
```

This command provides information about the deployment, including the desired and available replicas and the current deployment status.

## Step 4: Check Pods

To verify that your application's pods are running correctly, execute the following command:

```bash
kubectl get pods
```

This command lists the pods associated with your deployment, along with their current status and other relevant details.

## Step 5: Create a Kubernetes Service

To make your application accessible externally or within the cluster, you need to create a Kubernetes Service. Use the following command to create the service defined in `service.yml`:

```bash
kubectl apply -f service.yml
```

This service allows external access to your application.

## Step 6: Check Service Status

To check the status of your service and obtain information about its endpoints, use the following command:

```bash
kubectl get svc
```

This command displays details about your service, including its type (e.g., ClusterIP or NodePort) and the IP address or port used to access your application.

By following these steps, you can effectively deploy and manage your applications within a Kubernetes cluster using the provided configuration files. 

---

Thank you!
