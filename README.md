# 🚀 Task-3: Kubernetes Microservices Deployment using Minikube

## 📌 Internship Task Description

Deploy a microservices‑based application on a Kubernetes cluster and provide:

* YAML configuration files
* Documentation and demonstration screenshots

---

## 🧩 Objective

To set up a **local Kubernetes cluster** using **Minikube** and deploy a **3‑service microservices application** using Kubernetes Deployments and Services.

---

## 🏗️ Architecture Overview

This project implements three microservices:

| Service         | Technology         | Type      | Purpose                 |
| --------------- | ------------------ | --------- | ----------------------- |
| Users Service   | Nginx image        | ClusterIP | Internal API simulation |
| Orders Service  | Apache HTTPD image | ClusterIP | Internal API simulation |
| Gateway Service | Nginx image        | NodePort  | Public entry point      |

All resources are grouped in one namespace:

```
microservices-demo
```

---

## 🛠️ Tools & Technologies Used

* Kubernetes
* Minikube (local Kubernetes cluster)
* kubectl CLI
* Docker Desktop
* Kubernetes Dashboard UI

---

## 🔧 Setup Instructions (Windows)

### 1️⃣ Install Required Tools

```powershell
winget install -e --id Kubernetes.kubectl
winget install -e --id Kubernetes.minikube
```

Install Docker Desktop & enable virtualization.

---
<img width="1920" height="1080" alt="Screenshot 2025-12-04 095721" src="https://github.com/user-attachments/assets/40c47f24-e0f3-4e61-89fa-247e06f04422" />


### 2️⃣ Start Minikube Cluster

```powershell
minikube start --driver=docker
kubectl get nodes
```

Expected: `minikube` node in **Ready** state ✔

<img width="1920" height="1080" alt="Screenshot 2025-12-04 103522" src="https://github.com/user-attachments/assets/b898109c-4716-45ee-8716-f8d7751edae7" />


---

### 3️⃣ Deploy Microservices

Create file: `k8s-microservices.yml`
(contains Namespace, 3 Deployments & 3 Services)

Apply YAML:

```powershell
kubectl apply -f k8s-microservices.yml
kubectl get pods -n microservices-demo
kubectl get svc -n microservices-demo
```

---

### 4️⃣ Open Kubernetes Dashboard UI

```powershell
minikube dashboard
```

Switch Namespace → `microservices-demo`
View Deployments, Pods, and Services visually.

<img width="1920" height="1080" alt="Screenshot 2025-12-04 105422" src="https://github.com/user-attachments/assets/afe85fb8-e58e-4da3-9f42-b04d8975df2a" />

<img width="1920" height="1080" alt="Screenshot 2025-12-04 105437" src="https://github.com/user-attachments/assets/8067ec67-663a-4e30-9f1e-f95a648e66cb" />

<img width="1920" height="1080" alt="Screenshot 2025-12-04 105450" src="https://github.com/user-attachments/assets/6bb66172-3034-4151-bc6c-468b2bfd476b" />



---

### 5️⃣ Access Application in Browser

Expose Gateway Service:

```powershell
minikube service gateway-service -n microservices-demo --url
```

Copy URL → open in browser → NGINX page visible ✔

<img width="1920" height="1080" alt="Screenshot 2025-12-04 105640" src="https://github.com/user-attachments/assets/e8f6c918-85a0-4629-9bb1-9c95c166ef12" />


---

## ✔ What’s Working

* Kubernetes Cluster deployed locally
* Microservices running successfully
* Service discovery inside cluster
* NodePort allows external access
* Verified using Dashboard UI & Browser ✔

---

## 📄 YAML File Used

Filename: `k8s-microservices.yml`

> (Already uploaded to repository root as part of deliverables)

---


## Conclusion

Successfully deployed a **microservices architecture** using Kubernetes Deployments and Services on a local Minikube cluster. Demonstrated scalable, isolated, and service‑based cloud‑native deployment aligned with modern DevOps practices.

---


✨ **Task‑3 Completed & Verified Successfully** ✨
