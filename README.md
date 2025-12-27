# Dockerized Web Application Deployment 🚀

This project demonstrates the complete workflow of containerizing a simple web application using Docker and deploying it on an AWS EC2 instance to make it publicly accessible.

---

## 🛠️ What You Accomplished

- Created a simple **HTML web application**
- Wrote a **Dockerfile** using **NGINX** as the base image
- Built and tested the Docker image locally
- Tagged and pushed the image to **Docker Hub**
- Launched an **AWS EC2 instance** and installed Docker
- Pulled the Docker image on EC2
- Ran the container and successfully displayed the webpage publicly via EC2

---

## 🧱 Tech Stack

- **HTML**
- **Docker**
- **NGINX**
- **AWS EC2**
- **Docker Hub**
- **Linux (Amazon Linux / Ubuntu)**

---

## 📁 Project Structure

.
├── index.html
├── Dockerfile
└── README.md


--- 
## DockerFile 

**FROM nginx:alpine**  
**COPY index.html /usr/share/nginx/html/index.html**  
**EXPOSE 80**
**CMD ["nginx", "-g", "daemon off;"]**

---

**🚀 Steps to Run Locally**

**1️⃣ Build Docker Image**  
**`docker build -t docker-web-demo .`**

**2️⃣ Run Container**  
**`docker run -d -p 5000:80 docker-web-demo`**

**3️⃣ Open in Browser**  
**`http://localhost:5000`**

---

**📤 Push Image to Docker Hub**

**`docker tag docker-web-demo <dockerhub-username>/docker-web-demo:latest`**  
**`docker push <dockerhub-username>/docker-web-demo:latest`**

---

**🚀 Deploy on AWS EC2**

**1️⃣ Install Docker on EC2**  
**`sudo yum install docker -y`**  
**`sudo systemctl start docker`**  
**`sudo usermod -aG docker ec2-user`**

**2️⃣ Pull Image**  
**`docker pull <dockerhub-username>/docker-web-demo:latest`**

**3️⃣ Run Container**  
**`docker run -d -p 80:80 <dockerhub-username>/docker-web-demo:latest`**

**4️⃣ Access Publicly**  
**`http://<EC2-PUBLIC-IP>`**
