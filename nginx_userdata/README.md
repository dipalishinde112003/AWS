# Automated NGINX Installation and "Hello World" Deployment on EC2 Using User Data Script

## Prerequisites

- AWS account
- AWS CLI installed and configured
- Key pair created in AWS for SSH access to the EC2 instance
- Security group with appropriate rules to allow SSH (port 22) and HTTP (port 80) access

## Step-by-Step Guide

### 1. Create an EC2 Instance with User Data Script

#### Description
You can automate the setup process by providing a script as user data when launching the EC2 instance. This script will run during the instance's initial boot cycle and handle the installation of NGINX and deployment of a "Hello World" app.

#### User Data Script
When launching a new EC2 instance, you can provide the following script in the User Data field:

```bash
#!/bin/bash
sudo apt update
sudo apt install -y nginx
echo "Hello World">var/www/html/index.html

Review and Launch. Click Launch

Access the Deployed "Hello World" App
-Get the Public DNS (IPv4) of the Instance.
-Open a Web Browser.
-Enter the Public DNS Address of your EC2 instance.
-View the "Hello World" Page:
