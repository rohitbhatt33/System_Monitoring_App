# 🚀 System Monitoring App (Flask + Docker + Kubernetes + HPA)

A Production-Ready Cloud-Native System Monitoring Application built using:

- 🐍 Python (Flask + psutil)
- 🐳 Docker
- ☸️ Kubernetes
- 📈 Horizontal Pod Autoscaler (HPA)
- ☁️ AWS (ECR + EKS ready)

---

## 📌 Project Overview

This project demonstrates how to:

- Build a real-time system monitoring app
- Containerize it using Docker
- Deploy it to Kubernetes
- Implement Health Checks (Liveness & Readiness)
- Configure Horizontal Pod Autoscaling
- Make the app production-ready

It follows real-world DevOps best practices.

---

## 🏗️ Architecture

User → Kubernetes Service → Deployment → Pods (ReplicaSet)  
                                     ↓  
                             HPA (Auto Scaling)

---

## ⚙️ Tech Stack

| Layer | Technology |
|-------|------------|
| Backend | Flask + psutil |
| Visualization | Plotly |
| Container | Docker |
| Orchestration | Kubernetes |
| Scaling | HPA |


---

## 🧠 Production Enhancements Implemented

- ✅ Gunicorn instead of Flask dev server  
- ✅ Liveness Probe  
- ✅ Readiness Probe  
- ✅ Resource Requests & Limits  
- ✅ Replica configuration  
- ✅ Horizontal Pod Autoscaler  
- ✅ Clean Kubernetes YAML structure  
- ✅ Stress tested with load tools  

---

# 🐍 Run Locally

```bash
git clone <your-repo-url>
cd cloud-native-monitoring-app

pip install -r requirements.txt
python app.py
```

Open in browser:

```
http://localhost:5000
```

---

# 🐳 Docker Setup

### Build Image

```bash
docker build -t monitoring-app .
```

### Run Container

```bash
docker run -p 5000:5000 monitoring-app
```

---

# ☸️ Kubernetes Deployment (Minikube)

### Start Minikube

```bash
minikube start
```

### Apply Manifests

```bash
kubectl apply -f k8s/
```

### Verify Resources

```bash
kubectl get pods
kubectl get svc
kubectl get deployment
```

---

# ❤️ Health Checks

Why use Liveness & Readiness if replicas exist?

- Liveness → Restarts crashed containers automatically
- Readiness → Removes unhealthy pods from service traffic
- Ensures zero downtime
- Prevents broken pods from serving users

---

# 📈 Horizontal Pod Autoscaling (HPA)

Autoscaling based on CPU utilization.

```bash
kubectl autoscale deployment utilize-app \
  --cpu=50% \
  --min=2 \
  --max=5
```

Check status:

```bash
kubectl get hpa
```

---

# 🔥 Stress Testing

Install Apache Benchmark:

```bash
sudo apt install apache2-utils
```

Run load test:

```bash
ab -n 10000 -c 100 http://<service-ip>:5000/
```

Watch scaling live:

```bash
kubectl get pods -w
```

Pods automatically scale based on load 🚀

---

# ☁️ AWS Deployment (Optional)

1. Build Docker Image
2. Push to AWS ECR
3. Create EKS Cluster
4. Deploy using Kubernetes manifests
5. Expose using LoadBalancer service

---

# 📂 Project Structure

```
cloud-native-monitoring-app/
│
├── app.py
├── requirements.txt
├── Dockerfile
├── k8s/
│   ├── deployment.yml
│   ├── service.yml
│   ├── hpa.yml
│
└── README.md
```

---

# 🎯 Real-World Learning Outcomes

After completing this project, you understand:

- Difference between Flask dev server & Gunicorn
- Why replicas alone are not enough
- Importance of health probes
- How HPA works internally
- Resource limits & CPU throttling
- Kubernetes service types
- Production containerization best practices

---

# 💼 Interview Explanation (Short Version)

"I built a cloud-native monitoring app using Flask, containerized it with Docker, deployed it to Kubernetes, implemented health probes and HPA, and validated autoscaling through stress testing. The system scales automatically based on CPU utilization and ensures high availability."

---

# 🏁 Future Improvements

- Add Prometheus + Grafana
- Add Ingress Controller
- Add CI/CD pipeline (GitHub Actions)
- Add Helm chart
- Add Centralized logging (ELK stack)

---
🙏 Acknowledgement

This project is inspired by and based on the original repository created by:

**Nasi.C**  
GitHub: https://github.com/N4si  
Repository: https://github.com/N4si/cloud-native-monitoring-app  