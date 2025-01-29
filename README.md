# DevOps Monitoring and Alerting System

This project demonstrates a fully functional **DevOps Monitoring and Alerting System** using Kubernetes, Prometheus, Grafana, and Alertmanager. It showcases how to deploy a containerized Node.js application, monitor its performance, and trigger real-time alerts.

---

## Features

- **Containerized Application**: A Node.js app running in a Kubernetes cluster.
- **Monitoring**: Metrics collection using Prometheus and visualization using Grafana.
- **Alerts**: Real-time alerting for CPU usage and pod restarts with Alertmanager.
- **Auto-scaling**: Horizontal Pod Autoscaler (HPA) to dynamically scale pods.

---

## Prerequisites

To run this project, ensure you have the following installed:

- **Docker**: [Install Docker](https://docs.docker.com/get-docker/)
- **Minikube**: [Install Minikube](https://minikube.sigs.k8s.io/docs/start/)
- **Helm**: [Install Helm](https://helm.sh/docs/intro/install/)
- **Node.js**: [Install Node.js](https://nodejs.org/)

---

## How to Run the Project

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/DevOps-Monitoring-System.git
cd DevOps-Monitoring-System

## 2. Build and Push Docker Image


```bash
docker build -t your-dockerhub-username/sample-app .
docker push your-dockerhub-username/sample-app
```

## 3. Start Minikube
Start your local Kubernetes cluster:

```bash
minikube start
```

## 4. Deploy to Kubernetes
Apply the Kubernetes manifests to deploy the application:

```bash
kubectl apply -f manifests/
```

## 5. Install Prometheus and Grafana
Add the Prometheus Helm repository, update it, and install the monitoring stack:

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install prometheus prometheus-community/kube-prometheus-stack -f prometheus/custom-values.yaml
```

## 6. Access Grafana
Port-forward Grafana to your local machine:

```bash
kubectl port-forward svc/prometheus-grafana 3000:80
```

Open your browser and visit:

```http
http://localhost:3000
```
## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

Made with ❤️ by **Neel Vaidya**
