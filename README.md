# DevOps Project – Two-Tier Flask Application with CI/CD, HTTPS & Reverse Proxy

**Author:** Kshitija Randive  
**Role Focus:** DevOps Engineer  
**CI/CD:** GitHub Actions  
**Cloud:** AWS EC2  
**Security:** HTTPS (Self-Signed TLS)

---

## 📌 Project Overview

This project demonstrates a production-grade DevOps deployment of a two-tier Flask and MySQL application on AWS EC2.

The application is containerized using Docker and orchestrated with Docker Compose.  
A complete CI/CD pipeline is implemented using GitHub Actions, and traffic is securely handled via Nginx reverse proxy with HTTPS and caching.

---

## 🏗️ Architecture

### High-Level Architecture

End User (HTTPS)  
→ Nginx (Reverse Proxy + TLS + Cache)  
→ Flask App Container (Internal Network)  
→ MySQL Database Container (Persistent Volume)

### Infrastructure Diagram
![Infrastructure](static/diagrams/Infrastructure.png)

---

## 🔄 CI/CD Workflow

1. Developer pushes code to the main branch  
2. GitHub Actions pipeline is triggered  
3. Docker image is built  
4. Secure SSH connection to AWS EC2  
5. Application deployed using Docker Compose  
6. Nginx serves traffic over HTTPS  

### Workflow Diagram
![Workflow](static/diagrams/project_workflow.png)

---

## 🔐 HTTPS & Reverse Proxy

- Nginx runs inside Docker as a reverse proxy  
- TLS termination is handled by Nginx  
- Self-signed certificate is used (no domain required)  
- HTTP traffic is redirected to HTTPS  
- Caching is enabled for GET requests  

⚠️ Browser warnings are expected due to self-signed certificates.

---

## 🐳 Containerization Details

### Services
- Flask App – Python web application  
- MySQL – Database with persistent volume  
- Nginx – Reverse proxy, HTTPS, caching  

### Networking
- Containers run on a private Docker bridge network  
- Only ports 80 and 443 are exposed publicly  
- Flask and MySQL are not directly accessible  

---

## 🚀 Deployment Verification

```bash
docker ps
```

Access the application:

```
https://<EC2_PUBLIC_IP>
```

---

## ✅ Key DevOps Concepts Demonstrated

- Docker & Docker Compose  
- GitHub Actions CI/CD  
- AWS EC2 deployment  
- Reverse proxy architecture  
- HTTPS without managed certificates  
- Secure container networking  

---

## 🎯 Conclusion

This project demonstrates real-world DevOps practices with automation, security, and production-like infrastructure.