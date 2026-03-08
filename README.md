# 🚀 AWS EC2 Nginx Web Server Deployment

![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Linux](https://img.shields.io/badge/OS-AmazonLinux-yellow)
![Web Server](https://img.shields.io/badge/WebServer-Nginx-green)
![Project](https://img.shields.io/badge/Project-Cloud%20Deployment-blue)

---

# 📌 Project Overview

This project demonstrates how to deploy a **web server on an AWS EC2 instance** and host a simple static website using **Nginx on Amazon Linux**.

The goal of this project is to gain hands-on experience with:


* Launching and configuring an **AWS EC2 instance**
* Managing **security groups**
* Connecting to a cloud server using **SSH**
* Installing and configuring the **Nginx web server**
* Deploying a **static website on the cloud**

This project represents a **basic cloud infrastructure setup** commonly used as the foundation for scalable web applications.

---

# 🏗 Architecture Diagram

<img width="1536" height="1024" alt="ChatGPT Image Mar 8, 2026, 02_27_36 PM" src="https://github.com/user-attachments/assets/916c2146-fa0d-4185-9bf3-482c7623d045" />
---

# 🔁 Architecture Flow

```
User Browser
      │
      │ HTTP Request
      ▼
Internet
      │
      ▼
Security Group (Firewall)
      │
      ▼
EC2 Instance (Amazon Linux)
      │
      ▼
Nginx Web Server
      │
      ▼
Website Files
(/usr/share/nginx/html)
```

---

# 🧰 Technologies Used

| Technology      | Purpose               |
| --------------- | --------------------- |
| AWS EC2         | Cloud virtual machine |
| Amazon Linux    | Operating system      |
| Nginx           | Web server            |
| Security Groups | Firewall rules        |
| SSH             | Secure remote access  |
| HTML            | Website content       |

---

# 📋 Prerequisites

Before starting this project, ensure you have:

* An **AWS Account**
* Basic knowledge of **Linux commands**
* **SSH client** (Terminal / Git Bash / PowerShell)
* **EC2 key pair (.pem file)**

---

# ⚙️ Step 1: Launch EC2 Instance

1. Login to **AWS Management Console**
2. Navigate to **EC2 Dashboard**
3. Click **Launch Instance**

Configuration:

| Setting       | Value               |
| ------------- | ------------------- |
| Name          | EC2-Web-Server      |
| AMI           | Amazon Linux        |
| Instance Type | t2.micro            |
| Key Pair      | Create new key pair |

Launch the instance and copy the **Public IP Address**.

---

# 🔐 Step 2: Configure Security Group

Add inbound rules to allow traffic.

| Type | Port | Source    |
| ---- | ---- | --------- |
| SSH  | 22   | My IP     |
| HTTP | 80   | 0.0.0.0/0 |

These rules allow remote login and public web access.

---

# 💻 Step 3: Connect to EC2 Using SSH

Change key permissions:

```bash
chmod 400 mykey.pem
```

Connect to the instance:

```bash
ssh -i mykey.pem ec2-user@PUBLIC-IP
```

Example:

```bash
ssh -i mykey.pem ec2-user@3.88.120.55
```

---

# 🔄 Step 4: Update the Server

Update system packages:

```bash
sudo yum update -y
```

---

# 🌐 Step 5: Install Nginx Web Server

Install Nginx:

```bash
sudo amazon-linux-extras install nginx1 -y
```

Start Nginx:

```bash
sudo systemctl start nginx
```

Enable Nginx to start automatically:

```bash
sudo systemctl enable nginx
```

Check service status:

```bash
sudo systemctl status nginx
```

---

# 📂 Step 6: Deploy Website

Navigate to the Nginx web directory:

```bash
cd /usr/share/nginx/html
```

Check existing files:

```bash
ls
```

Edit the index file:

```bash
sudo nano index.html
```

Example website content:

```html
<h1>Hello from AWS EC2 Nginx Server</h1>
<p>This website is hosted on AWS EC2 using Nginx.</p>
```

Save the file.

---

# 🌍 Step 7: Access the Website

Open a browser and enter:

```
http://PUBLIC-IP
```

Example:

```
http://3.88.120.55
```

Your website should now be accessible from the internet.

---

# 📸 Project Screenshots



### EC2 Instance Running

<img width="1918" height="1027" alt="Screenshot 2026-03-08 143501" src="https://github.com/user-attachments/assets/307df1e3-c673-43c6-ae7e-bd488b8fa2a4" />

### Nginx Web Server Output

<img width="1906" height="980" alt="Screenshot 2026-03-08 143622" src="https://github.com/user-attachments/assets/c166f32b-dd8e-48d0-9076-2562b3b9ab8b" />


---

# 📊 Skills Learned

* AWS EC2 instance deployment
* Security group configuration
* SSH remote server access
* Nginx installation and configuration
* Hosting a website on cloud infrastructure
* Basic Linux server management

---

# 🔮 Future Improvements

This project can be extended by implementing:

* Application Load Balancer
* Auto Scaling Group
* Route53 custom domain
* SSL certificate (HTTPS)
* CI/CD deployment pipeline
* Docker container deployment

---

# 👨‍💻 Author

**Sudarshan Mane**

Cloud & DevOps Enthusiast

---

⭐ If you found this project helpful, consider giving this repository a **star**.
