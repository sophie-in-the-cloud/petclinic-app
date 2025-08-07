# 🐾 Petclinic Application (WAS)

This is a Spring Boot-based Petclinic application, serving as the **Application Tier** in a 3-Tier architecture.  
It handles both business logic and server-side view rendering, and is deployed on Tomcat.

---

## 🛠️ Tech Stack

- Java 11  
- Spring Boot  
- Maven  
- Apache Tomcat  
- AWS ElastiCache for Redis (Session Clustering)  
- AWS RDS (MySQL)  
- AWS Secrets Manager  

---

## ▶️ How to Run Locally

```bash
./mvnw clean package -DskipTests -PMySQL
```

- The `MySQL` profile retrieves DB credentials from AWS Secrets Manager.

---

## 📌 Key Features

- Basic owner and pet data search functionality  
- Redis-based HTTP session clustering for horizontal scalability  
- Externalized secrets management with AWS Secrets Manager

---

## 🔁 CI/CD Pipeline

- GitHub Actions builds a Docker image and pushes it to AWS ECR  
- Then it automatically creates a Pull Request to the [`manifest`](https://github.com/sophie-in-the-cloud/petclinic-manifest) repository with the updated image tag  
- Once the PR is **reviewed and approved**, Argo CD detects the change and syncs the deployment to the EKS cluster

> This approval step ensures safer and auditable production deployments.

---

## 📂 Notes

- This application runs as the WAS layer within an AWS EKS cluster  
- Designed to support frontend access via HTTP reverse proxy (Web Tier)
