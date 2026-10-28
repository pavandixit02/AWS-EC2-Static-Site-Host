# 🚀 Deploy a Static Website on AWS EC2

A beginner-friendly guide to deploying a static website on an **AWS EC2 instance** using Apache HTTP Server (`httpd`).

This project demonstrates hosting a static website on a cloud server using HTML, CSS, JavaScript, Linux, and AWS EC2.

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Project Structure](#-project-structure)
- [Technologies Used](#-technologies-used)
- [Prerequisites](#-prerequisites)
- [Troubleshooting](#-troubleshooting)
- [Security Best Practices](#-security-best-practices)
- [Cleanup and Cost Management](#-cleanup-and-cost-management)
- [Learning Outcomes](#-learning-outcomes)
- [Future Improvements](#-future-improvements)

---

## 📖 Project Overview

The objective of this project is to host a static website on an AWS EC2 virtual machine.

The website consists of HTML, CSS, and JavaScript files. Apache HTTP Server serves these files to visitors through a web browser.

### How It Works

1. Launch an EC2 instance in AWS.
2. Connect to the instance using SSH and a private key (`.pem`).
3. Install and configure Apache HTTP Server.
4. Transfer website files from the local Ubuntu system to EC2.
5. Place the website files in Apache's document root.
6. Access the website using the EC2 instance's public IPv4 address.

## 📂 Project Structure

```text
.
├── Guide-Static-Site-EC2.md
├── httpd-install/
│   ├── httpd-install-ec2.png
│   ├── httpd-start-ec2.png
│   ├── index_html.png
│   └── outpust-index_html-ec2.png
├── index.html
├── script.js
├── static-images/
│   ├── first-static-in-ec2.png
│   ├── output-static_website-ec2.png
│   └── transfer-local-ec2.png
├── style.css
└── README.md
```

**Note:** The image directories are part of the existing repository structure, but this README does not embed or reference any images. The deployment uses the website source files directly.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| AWS EC2 | Cloud virtual machine for hosting the website |
| Amazon Linux | Operating system for the EC2 instance |
| Apache HTTP Server (`httpd`) | Serves website files over HTTP |
| HTML5 | Website structure |
| CSS3 | Website styling |
| JavaScript | Client-side functionality |
| Ubuntu Linux | Local development and file transfer |
| SSH | Secure remote access to EC2 |
| SCP | Securely transfers website files |
| AWS Security Groups | Controls inbound network traffic |

## ✅ Prerequisites

Before starting, ensure you have:

- An AWS account with access to EC2.
- An EC2 instance running Amazon Linux.
- A downloaded EC2 key pair file (`.pem`).
- Ubuntu Linux on your local machine.
- Website files: `index.html`, `style.css`, and `script.js`.
- SSH and SCP installed on Ubuntu.
- A public IPv4 address for your EC2 instance.

---

## 🛠️ Troubleshooting

### 1. SSH Connection Timed Out

Check the following:

- EC2 instance state is `Running`.
- Security group permits inbound TCP port 22 from your current IP.
- The public IPv4 address is correct.
- Your local internet connection allows outbound SSH traffic.

### 2. Permission Denied (Public Key)

Verify that:

- You are using the correct private key.
- The private key has appropriate permissions.
- You are using the correct SSH username.

For Amazon Linux, the default username is generally `ec2-user`. For Ubuntu AMIs, it is commonly `ubuntu`.

### 3. Website Does Not Open

Check Apache service status and the EC2 security group's inbound HTTP rule.

Apache logs can help identify server-side errors:

```bash
sudo tail -n 50 /var/log/httpd/error_log
```

Service logs can be inspected with:

```bash
sudo journalctl -u httpd --no-pager -n 50
```

### 4. HTTP 403 Forbidden

Verify that the website files are readable and that the web server can access the document root. Also check that a valid index file exists.

### 5. HTTP 404 Not Found

Confirm that the requested file exists in the correct directory. Linux file names are case-sensitive.

### 6. CSS or JavaScript Is Not Loading

Check the asset paths inside `index.html` and confirm that the referenced files are present in the deployed directory structure.

---

## 🛡️ Security Best Practices

- Keep your `.pem` private key secure and never commit it to a repository.
- Restrict SSH access to trusted IP addresses.
- Use least-privilege IAM permissions.
- Keep the operating system and web server updated.
- Avoid unnecessary inbound security group rules.
- Do not store credentials or access keys in HTML, JavaScript, or public repositories.
- Consider HTTPS with a valid TLS certificate before using the website for production.
- Monitor AWS usage and terminate resources when you no longer need them.

## 💰 Cleanup and Cost Management

AWS EC2 and associated resources may incur charges depending on your instance, region, storage, public IPv4 usage, and account eligibility.

When the project is complete:

- Back up any files you need.
- Stop or terminate the EC2 instance when it is no longer required.
- Review unused EBS volumes and snapshots.
- Review Elastic IP addresses, public IPv4 charges, and other associated resources.
- Check AWS Billing and Cost Management for actual usage and charges.

**Note:** Stopping an instance does not necessarily eliminate all charges. Attached EBS storage, for example, may continue to incur charges. Terminate a disposable learning instance only after confirming that you no longer need its data.

## 🎯 Learning Outcomes

After completing this project, you should understand:

- AWS EC2 instance hosting fundamentals.
- SSH authentication using a PEM private key.
- Apache HTTP Server and Linux web hosting.
- Secure file transfer using SCP.
- Static website deployment on a Linux server.
- AWS Security Groups and inbound traffic rules.
- Troubleshooting common web-server and access issues.
- Basic cloud resource and cost management.

## 🚀 Future Improvements

You can extend this project by adding:

- A custom domain name.
- HTTPS using a valid TLS certificate.
- Automated deployment scripts.
- Continuous deployment using GitHub Actions.
- Infrastructure provisioning using Terraform.
- Monitoring with Prometheus and Grafana.
- A production architecture using Amazon S3 and CloudFront.

---

## 👨‍💻 Author

**Pavan Kumar Dixit**

Cloud Computing | AWS | Linux | DevOps

GitHub: [Visit My GitHub Profile](https://github.com/)

---

*This project is intended for learning and practice. Review security, availability, and cost requirements before using an EC2-hosted website in production.*