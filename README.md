# 🚀 Brain Tasks App – DevOps Deployment Project

## 📌 Project Overview
This project demonstrates a **production-ready DevOps pipeline** for deploying a React-based application using Docker, Kubernetes (EKS), and AWS CI/CD services.
The application is containerized and deployed on AWS using a fully automated pipeline.

## 🧱 Tech Stack

* Frontend: React (pre-built dist)
* Containerization: Docker
* Orchestration: Kubernetes
* Cloud: AWS
* CI/CD: CodePipeline + CodeBuild
* Registry: Docker Hub
* Monitoring: CloudWatch

---

## 🏗️ Architecture

1. Developer pushes code to GitHub
2. CodePipeline triggers automatically
3. CodeBuild:

   * Builds Docker image
   * Pushes to Docker Hub
   * Updates Kubernetes deployment
4. EKS cluster pulls latest image
5. Application exposed via LoadBalancer

---

## 📂 Project Structure

```
Brain-Tasks-App/
│── dist/
│── Dockerfile
│── deployment.yaml
│── service.yaml
│── buildspec.yml
```

---

## 🐳 Docker Setup

### Build Image

```
docker build -t brain-tasks-app .
```

### Run Locally

```
docker run -d -p 3000:80 brain-tasks-app
```

---

## ☸️ Kubernetes Deployment

### Apply Deployment

```
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### Get Service URL

```
kubectl get svc
```

---

## 🔄 CI/CD Pipeline

### Pipeline Flow

```
GitHub → CodePipeline → CodeBuild → Docker Hub → EKS
```

### buildspec.yml Responsibilities

* Login to Docker Hub
* Build Docker image
* Push image to Docker Hub
* Update Kubernetes deployment
* Verify rollout

---

## 📊 Monitoring

* CloudWatch Logs used for:

  * Build logs
  * Pipeline execution
  * Error debugging

---

## 🌐 Application Access

Application is exposed via:

```
LoadBalancer (AWS ELB)
```

---

## ⚠️ Challenges Faced

* IAM permission issues (EKS access)
* Docker image pull errors
* Kubernetes deployment mismatch
* kubectl binary issues
* YAML formatting errors


## ✅ Solutions Implemented

* Attached correct IAM policies
* Used correct Docker image tagging
* Fixed buildspec.yml structure
* Installed proper kubectl binary
* Used wildcard container update

## 🧹 Cleanup

To avoid charges:

```
eksctl delete cluster --name brain-tasks-cluster --region ap-south-1
```

---

## 🎯 Conclusion

This project demonstrates:

* End-to-end CI/CD pipeline
* Real-world DevOps debugging
* Cloud-native deployment
* Production-ready architecture

---

## 👨‍💻 Author

K.Udaya Kumar
