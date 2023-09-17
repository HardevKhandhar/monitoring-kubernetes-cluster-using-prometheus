# Grafana Dashboard

## Overview

The Grafana Dashboard provides comprehensive monitoring and visualization capabilities for your Kubernetes cluster. Follow these steps to set up and use the dashboard effectively.

## Accessing the Grafana Dashboard

1. Visit `http://[NODEIP]:32000` in your web browser to access the Grafana dashboard.

2. Log in with the following credentials:
   - **Username**: admin
   - **Password**: admin
   
   >_You can reset the password on the next screen or click `Skip`._

## Importing Dashboards

To get started with the pre-configured dashboards, follow these steps:

3. On the `Welcome to Grafana` page, click on the `+` sidebar icon in the upper-left corner of the screen.

4. From the drop-down menu, select `Imports`.

5. In the `Grafana.com Dashboard` textbox, enter the dashboard ID `10000` and click `Load`. This will load the `Cluster Monitoring for Kubernetes` dashboard.

   >_**Note:** You can find a list of pre-configured dashboards at [Grafana Dashboard Repository](https://grafana.com/grafana/dashboards). Each dashboard will have an ID that you can copy into the Grafana `Import dashboard` screen._

6. On the next screen, select a Prometheus data source from the `Select a Prometheus data source` drop-down list, and click `Import`. Your dashboard will now load.

7. To load additional pre-configured dashboards, repeat the process:
   - Click on the `Cluster Monitoring for Kubernetes` drop-down in the upper-left corner.
   - Follow the import steps, but this time use the dashboard ID `8588` to load the `Kubernetes Deployment Statefulset Daemonset metrics` dashboard.

8. Continue importing dashboards as needed. For example, import the dashboard with an ID of `10694` called `Container Statistics`.

## Managing Dashboards

9. To switch between dashboards, click on the dashboard name drop-down in the upper-left corner of the screen. You will see all the imported dashboards listed, and you can easily switch between them.

10. Feel free to import more dashboards or create your custom dashboards to monitor specific aspects of your Kubernetes cluster.

With these steps, you can make the most of the Grafana Dashboard to monitor and visualize the performance and health of your Kubernetes environment.

---

Thank you!
