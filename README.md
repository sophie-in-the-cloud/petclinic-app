# 🐾 Petclinic Application (WAS)
This is a Spring Boot-based Petclinic application, responsible for the **Application Tier** in a 3-Tier architecture.  
It includes Redis-based session clustering and integration with AWS Secrets Manager for secure configuration.

---
## 🛠️ Tech Stack

- Java 11  
- Spring Boot
- AWS ElasticCache Redis (Session Clustering)  
- MySQL (AWS RDS)  
- AWS Secrets Manager  

---
## ▶️ How to Run Locally

```bash
./mvnw clean package -DskipTests -PMySQL
```
- The `MySQL` profile loads DB credentials from AWS Secrets Manager.

---
## 📌 Key Features
- Basic Owner and Pet search functionality  
- Redis-based session clustering for scalability  
- Sensitive credentials managed securely via AWS Secrets Manager

---
## 🔁 CI/CD Pipeline
- GitHub Actions builds the Docker image and pushes it to ECR  
- Argo CD automates deployment to the Kubernetes cluster

> For deployment configuration, refer to the [`manifest`](https://github.com/sophie-in-the-cloud/petclinic-manifest) repository.

---
## 📂 Notes

- This service runs as the WAS layer in an AWS EKS cluster.  
- Designed as a backend API to support frontend client access.
