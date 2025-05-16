# Group Work - Kubernetes Hackathon
A hands-on DevOps project that deploys a fictional e-commerce platform — **Widgetario** — to a Kubernetes cluster using best practices across **configuration, storage, ingress, observability, and CI/CD**.

Link: https://kubernetes.courselabs.co/hackathon/

## 🧱 Architecture

Widgetario consists of the following services:

- 🛒 **Web App** — customer-facing frontend
- 📦 **Products API** — RESTful API to manage widget inventory
- 🗃️ **Products DB** — PostgreSQL database
- 📈 **Stock API** — calculates stock levels
- 📊 **Observability Stack** — Prometheus, Grafana, Elasticsearch, Fluentd, Kibana
- ⚙️ **CI/CD** — Jenkins pipelines for build/test/deploy

---

## 📂 Repository Structure
## 📁 Repository Structure

kubernetes-hackathon/
├── part1/ # Basic Kubernetes manifests and service deployment
├── part2/ # ConfigMaps, Secrets, and environment variable setup
├── part3/ # Persistent Volumes and PVC configurations
├── part4/ # Ingress setup with domain routing
├── part5/ # Resource limits, readiness/liveness probes, autoscaling
├── part6/ # Prometheus, Grafana, and EFK observability stack. 
    ├── grafana-dashboard.json
│   └── kibana-dashboard.ndjson
├── part7/ # Jenkins CI/CD pipeline configs
    ├── Jenkinsfile # Jenkins pipeline definition
└── README.md # Project documentation

---

## ⚙️ Prerequisites

Install the following tools:

- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Helm](https://helm.sh/)
- [Minikube](https://minikube.sigs.k8s.io/docs/)
- [Jenkins](https://www.jenkins.io/)
- [Docker](https://www.docker.com/)

---
## 🚀 Deployment Instructions

0. **Clone Repo**:

```bash
git clone https://github.com/254Nicole-Nase/kubernetes-hackathon.git
cd kubernetes-hackathon/

```
1. **Start your Kubernetes cluster:**

```bash
minikube start
```
2. **Apply each part**
```bash
kubectl apply -f part1/
kubectl apply -f part2/
kubectl apply -f part3/
kubectl apply -f part4/

```
3. **Update your /etc/hosts** (Depends on your machine)
```bash
127.0.0.1 widgetario.local
127.0.0.1 api.widgetario.local

```

4. **Access Widgetario:**

- Web App: http://widgetario.local

- Products API: http://api.widgetario.local

## 📊 Observability

The observability stack is configured in the [`part6/`](./part6/) directory. It includes:

- **Prometheus** for metrics scraping
- **Grafana** for visualization
- **EFK stack** (Elasticsearch, Fluentd, Kibana) for centralized logging

### Access Dashboards

- **Grafana:** [http://localhost:3000](http://localhost:3000)  
- **Kibana:** [http://localhost:5601](http://localhost:5601)

> To view custom dashboards, import them from the [`monitoring/`](./part6/monitoring) directory.

---

## 🧪 CI/CD

The CI/CD pipeline is set up in the [`part7/`](./part7/) directory and is powered by **Jenkins**.

### Automated Pipeline Stages:

- 🐳 **Docker Image Builds** – builds container images for each service
- 🚀 **Helm Chart Deployment** – deploys services to the Kubernetes cluster using Helm
- 🧪 **Linting and Tests** – ensures manifest quality and application correctness
