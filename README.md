Automated CI/CD Pipeline for 2-Tier Flask Application on AWS
📌 Project Overview

This project demonstrates the implementation of a fully automated CI/CD pipeline for deploying a 2-tier Flask web application using modern DevOps tools and AWS cloud services.

The pipeline automates the process of building, testing, and deploying applications, ensuring faster and reliable software delivery.

🏗️ Architecture
Developer → GitHub → Jenkins → Docker → AWS EC2 → Flask Ap
🔹 Components:

Frontend/Application Layer: Flask Web Application

CI/CD Tool: Jenkins

Containerization: Docker

Cloud Platform: AWS EC2

Version Control: GitHub

☁️ AWS EC2 Setup

Instance Type: t2.micro (Free Tier)

OS: Ubuntu

Open Ports:

22 (SSH)

80 (HTTP)

5000 (Flask App)

8080 (Jenkins)

⚙️ Installation & Setup
🔹 Connect to EC2::
ssh -i /path/to/key.pem ubuntu@<ec2-public-ip>

🔹 Install Dependencies::
sudo apt update && sudo apt upgrade -y

sudo apt install git docker.io docker-compose-v2 -y

🔹 Start Docker::
sudo systemctl start docker

sudo systemctl enable docker

sudo usermod -aG docker $Ubuntu

newgrp docker

🔧 Jenkins Setup
🔹 Install Java::

sudo apt install -y openjdk-21-jdk

🔹 Install Jenkins::

wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -

sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

sudo apt update

sudo apt install -y jenkins

🔹 Start Jenkins::
sudo systemctl start jenkins

sudo systemctl enable jenkins

🔹 Unlock Jenkins::

sudo cat /var/lib/jenkins/secrets/initialAdminPassword

Access Jenkins:

http://<EC2-PUBLIC-IP>:8080

🔗 GitHub Integration

Connect Jenkins with your GitHub repository

Configure Webhooks for automatic build triggers

🔄 CI/CD Pipeline
🔹 Pipeline Workflow:

Developer pushes code to GitHub

Jenkins triggers build automatically

Jenkins pulls latest code

Docker image is built

Container is deployed on EC2

Flask app runs on port 5000


🌐 Application Access

Flask App:

http://<EC2-PUBLIC-IP>:5000

Jenkins Dashboard:

http://<EC2-PUBLIC-IP>:8080
