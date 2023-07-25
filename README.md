# Kubernetes Monitoring with Prometheus and Grafana

This repository contains the code and instructions for setting up Kubernetes monitoring using Prometheus and Grafana. By following the steps outlined in this guide, you will be able to deploy Prometheus and Grafana to your Kubernetes cluster, enabling you to monitor and visualize various metrics from your applications and infrastructure.

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Deployment](#deployment)
  - [Step 1: Deploy Prometheus to Kubernetes](#step-1-deploy-prometheus-to-kubernetes)
  - [Step 2: Create a ConfigMap for Prometheus Configuration](#step-2-create-a-configmap-for-prometheus-configuration)
  - [Step 3: Deploy Prometheus ConfigMap and Service](#step-3-deploy-prometheus-configmap-and-service)
  - [Step 4: Deploy Grafana to Kubernetes](#step-4-deploy-grafana-to-kubernetes)
  - [Step 5: Deploy Grafana ConfigMap](#step-5-deploy-grafana-configmap)
  - [Step 6: Deploy Grafana ConfigMap and Service](#step-6-deploy-grafana-configmap-and-service)
  - [Step 7: Access Grafana Dashboard](#step-7-access-grafana-dashboard)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Monitoring Kubernetes clusters is crucial to ensure their stability, performance, and resource utilization. Prometheus, coupled with Grafana, provides a powerful monitoring and visualization solution that helps you gain insights into your Kubernetes infrastructure and applications.

This guide will walk you through the process of deploying Prometheus and Grafana to your Kubernetes cluster. The combination of Prometheus as the monitoring and alerting toolkit and Grafana as the visualization tool will allow you to create informative dashboards that help you make data-driven decisions and proactively respond to potential issues.

## Prerequisites

Before proceeding with the deployment, ensure you have the following prerequisites met:

1. A working Kubernetes cluster.
2. `kubectl` configured to access your Kubernetes cluster.
3. Basic knowledge of Kubernetes concepts.

## Deployment

Follow the steps below to deploy Prometheus and Grafana to your Kubernetes cluster.

### Step 1: Deploy Prometheus to Kubernetes

Create the necessary Kubernetes resources to deploy Prometheus by applying the `prometheus.yaml` file:

```bash
kubectl apply -f prometheus.yaml
```

### Step 2: Create a ConfigMap for Prometheus Configuration

Create a ConfigMap to store the configuration for Prometheus by applying the `prometheus-config.yaml` file:

```bash
kubectl apply -f prometheus-config.yaml
```

### Step 3: Deploy Prometheus ConfigMap and Service

```bash
kubectl apply -f prometheus-config.yaml
kubectl apply -f prometheus.yaml
```

### Step 4: Deploy Grafana to Kubernetes

Deploy Grafana to your Kubernetes cluster by applying the `grafana.yaml` file:

```bash
kubectl apply -f grafana.yaml
```

### Step 5: Deploy Grafana ConfigMap

Create a ConfigMap to configure Grafana by applying the `grafana-datasource.yaml` file:

```bash
kubectl apply -f grafana-datasource.yaml
```

### Step 6: Deploy Grafana ConfigMap and Service

```bash
kubectl apply -f grafana-datasource.yaml
kubectl apply -f grafana.yaml
```

### Step 7: Access Grafana Dashboard

Forward the Grafana port to your localhost:

```bash
kubectl port-forward -n monitoring $GRAFANA_POD 3000:3000
```

Now, access Grafana dashboard by visiting http://localhost:3000 in your web browser.

## Usage

Once you have set up Prometheus and Grafana, you can start creating custom dashboards and visualizations to monitor your Kubernetes resources and applications. Grafana provides a user-friendly interface to create insightful dashboards based on the data collected by Prometheus.

## Contributing

We welcome contributions to this project. If you find any issues or have suggestions for improvement, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute it as per the terms of the license.

---

We hope you find this guide helpful in setting up Kubernetes monitoring using Prometheus and Grafana. If you have any questions or need further assistance, please feel free to reach out to us.

Happy monitoring!
