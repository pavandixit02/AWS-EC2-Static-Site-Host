# 🚀 Static Website Hosting on AWS EC2

A beginner-friendly cloud project demonstrating how to host a static website on **AWS EC2 using Apache HTTP Server**.

## 📌 About the Project

This project focuses on deploying a static website on an AWS EC2 instance. The website is built using HTML, CSS, and JavaScript, while Apache serves the website files over HTTP.

### ✨ Key Features

- Static website hosting on AWS EC2
- Apache HTTP Server configuration
- Secure remote access using SSH
- Website file transfer using SCP
- Public access through an EC2 IPv4 address
- Basic Linux server management and troubleshooting

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

*Note: The image files are part of the repository structure but are not used or embedded in this README.*

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| AWS EC2 | Hosts the website on a cloud server |
| Amazon Linux | Server operating system |
| Apache (`httpd`) | Web server |
| HTML5 | Website structure |
| CSS3 | Website styling |
| JavaScript | Website functionality |
| Ubuntu Linux | Local development environment |
| SSH & SCP | Remote access and file transfer |
| AWS Security Groups | Network access control |

## ⚙️ How It Works

1. Launch an EC2 instance on AWS.
2. Connect to the server using SSH.
3. Install and start Apache HTTP Server.
4. Transfer the website files to EC2.
5. Place the files in Apache's web directory.
6. Open the website using the EC2 public IPv4 address.

## ✅ Prerequisites

- An AWS account with EC2 access
- An EC2 instance running Amazon Linux
- An SSH private key (`.pem`)
- An Ubuntu system
- Basic knowledge of Linux commands
- Website files: `index.html`, `style.css`, and `script.js`

## 🌐 Access the Website

Once the deployment is complete, open the following URL in your browser:

```text
http://YOUR_EC2_PUBLIC_IP
```

Replace `YOUR_EC2_PUBLIC_IP` with the public IPv4 address of your EC2 instance.

The instance must be running, Apache must be active, and the security group must allow inbound HTTP traffic on port 80.

## 🛠️ Common Issues

| Issue | What to Check |
|---|---|
| SSH connection failed | Public IP, private key, username, and port 22 access |
| Permission denied | Key permissions and correct SSH username |
| Website not opening | Apache status and security group rules |
| 403 Forbidden | File permissions and index file |
| 404 Not Found | File location and URL |
| CSS or JavaScript not loading | Asset paths and transferred files |

For Apache logs on Amazon Linux:

```bash
sudo tail -n 50 /var/log/httpd/error_log
```

## 🔐 Security Best Practices

- Never share or upload your `.pem` private key.
- Allow SSH access only from trusted IP addresses.
- Use least-privilege IAM permissions.
- Keep the operating system and web server updated.
- Open only the required network ports.
- Use HTTPS for production websites.
- Avoid storing credentials in public repositories.

## 💰 AWS Cost Management

AWS charges may apply depending on your resources, region, and account eligibility.

- Monitor your AWS billing regularly.
- Stop or terminate unused EC2 instances.
- Review attached EBS volumes, snapshots, and public IPv4 resources.
- Back up important data before deleting resources.

**Important:** Stopping an EC2 instance does not necessarily stop every associated charge. Check AWS Billing and Cost Management for your actual usage.

## 🎯 What I Learned

- EC2 instance creation and cloud hosting
- Linux server administration
- Apache installation and management
- SSH authentication and SCP file transfer
- Security Group configuration
- Static website deployment
- Basic troubleshooting and cloud cost awareness

## 🚀 Future Enhancements

- Custom domain configuration
- HTTPS using a TLS certificate
- Automated deployment using GitHub Actions
- Infrastructure as Code with Terraform
- Monitoring with Prometheus and Grafana
- Static hosting with Amazon S3 and CloudFront

## 👨‍💻 Author

**Pavan Kumar Dixit**

*Aspiring Cloud & DevOps Engineer*

- GitHub: [GitHub Profile](https://github.com/pavandixit02)

---

*Built as a hands-on AWS cloud learning project to develop practical skills in Linux, web hosting, and cloud infrastructure.*