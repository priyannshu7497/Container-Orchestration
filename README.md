# Container-Orchestration

# 🚀 Kubernetes Deployment for MERN Frontend Application

This project demonstrates how to build, containerize, and deploy a **React (MERN Frontend)** application using **Docker** and **Kubernetes** on a local development cluster (Docker Desktop Kubernetes).

---

## 👨‍💻 Author

| Field | Details |
|-------|---------|
| **Name** | Priyanshu Gupta |
| HeroVired |
| **Subject** | Container Orchestration |
| **Assignment** | Kubernetes Deployment with Docker |


---

## 📚 Table of Contents

| Section |
|--------|
| 1. Project Overview |
| 2. Technologies Used |
| 3. Folder Structure |
| 4. Architecture Diagram |
| 5. Steps to Deploy |
| 6. Kubernetes Resources |
| 7. Verification |
| 8. Screenshots |
| 9. Cleanup Commands |

---

## 🛠️ Project Overview

The goal of this assignment is to:

- Build a MERN frontend using React
- Create a Docker image of the frontend
- Deploy the Dockerized application on Kubernetes
- Expose the application using a **NodePort Service**
- Verify successful deployment via browser

---

## 🧰 Technologies Used

| Technology | Purpose |
|-----------|---------|
| **React JS** | Frontend Application |
| **Docker** | Containerization |
| **Kubernetes** | Orchestration |
| **kubectl** | Kubernetes CLI |
| **Docker Desktop Kubernetes** | Local cluster |

---

## 📂 Project Folder Structure



Graded Assignment on Container Orchestration/
│── learnerReportCS_frontend/
│ ├── Dockerfile
│ ├── deployment.yaml
│ ├── package.json
│ ├── src/
│ └── build/


---

## 🏗️ Architecture Diagram

```mermaid
flowchart TD
    User --> Browser --> NodePortService --> Pod1[Frontend Pod]
    NodePortService --> Pod2[Frontend Pod]
    Pod1 --> DockerImage
    Pod2 --> DockerImage
    DockerImage --> KubernetesCluster
    KubernetesCluster --> DockerDesktop

⚙️ Deployment Steps
1️⃣ Build Docker Image
docker build -t learner-frontend .
docker tag learner-frontend:latest learner-frontend:v1

2️⃣ Apply Kubernetes Deployment & Service
kubectl apply -f deployment.yaml --validate=false

3️⃣ Check Running Pods
kubectl get pods


Expected Output:

learner-frontend-xxxx Running
learner-frontend-yyyy Running

4️⃣ Expose Service and Get Port
kubectl get svc


Output Example:

learner-frontend-service  NodePort  3000:30007/TCP

5️⃣ Access Application in Browser
http://localhost:30007

📌 Kubernetes Resources Used
Resource	Purpose
Deployment	Ensures multiple running replicas
Pod	Container unit inside K8s
ClusterIP (Internal)	Internal routing
NodePort	Makes application accessible externally
🔍 Verification

[✔️] Docker image built successfully

[✔️] Pods running inside Kubernetes

[✔️] Application accessible through browser

[✔️] Replicas created as defined in deployment
```
📸 Screenshots
✅ 1️⃣ Node Installed Check (Optional but Good)

Command:

node -v
npm -v


👉 Screenshot name: node_npm_installed.png
📌 Proof: development environment setup.

✅ 2️⃣ Docker Image Build Screenshot

Command:

docker build -t learner-frontend .


👉 Screenshot name: docker_build_success.png
📌 Proof: Image successfully created.

✅ 3️⃣ Docker Images List

Command:

docker images


👉 Screenshot name: docker_images_list.png
📌 Proof: Image stored locally.

✅ 4️⃣ Kubernetes Node Running Screenshot

Command:

kubectl get nodes


👉 Screenshot name: kubectl_node_ready.png
📌 Proof: Kubernetes cluster active.

✅ 5️⃣ Deploy Command Output

Command:

kubectl apply -f deployment.yaml


👉 Screenshot name: deployment_created.png
📌 Proof: Deployment created without issues.

✅ 6️⃣ Pods Running Screenshot

Command:

kubectl get pods


👉 Screenshot name: pods_running.png
📌 Proof: Application running inside Kubernetes.

✅ 7️⃣ Service Created Screenshot

Command:

kubectl get svc


👉 Screenshot name: service_created.png
📌 Proof: NodePort service exposed successfully.

✅ 8️⃣ Browser Access Screenshot

Open in browser:

http://localhost:<nodeport>


Example:
➡️ http://localhost:30007

```sh
Replace image names with your actual uploaded images

Step	Screenshot
Docker Build	

Kubernetes Pods	

NodePort Service	

Running Application	
🧹 Cleanup Commands (Optional)
kubectl delete -f deployment.yaml
docker rmi learner-frontend:v1

🏁 Conclusion

This assignment successfully demonstrates:

Building and containerizing an application with Docker

Deploying the application on a Kubernetes cluster

Exposing and accessing the app externally through NodePort

Managing infrastructure using modern cloud-native workflows
