# Install NGINX on EC2 and Deploy a "Hello World" App

## Prerequisites

- AWS account
- AWS CLI installed and configured
- Key pair created in AWS for SSH access to the EC2 instance
- Security group with appropriate rules to allow SSH (port 22) and HTTP (port 80) access

## Step-by-Step Guide

### 1. Create an EC2 Instance

1. **Log in to the AWS Management Console**.
2. **Navigate to the EC2 Dashboard**.
3. **Launch a New Instance**.
4. **Choose an Amazon Machine Image (AMI)**.
5. **Choose an Instance Type**.
6. **Configure Instance Details**.
7. **Add Storage**.
8. **Add Tags**.
9. **Configure Security Group**.
10. **Review and Launch**.
11. **View Instances**.

### 2. Connect to the EC2 Instance

1. **Get the Public DNS (IPv4) of the Instance**.
2. **Connect to the Instance Using SSH**.

### 3. Install NGINX

1. **Update the Package List**:
   ```bash
   sudo apt update

Install NGINX:
sudo apt install nginx

Check the Status of NGINX:
sudo service nginx status

Verify NGINX Installation:
curl localhost

### 4.Deploy "Hello World" App
1. Navigate to the Web Root Directory:
      cd /var/www/html/
2.Create a Simple "Hello World" HTML Page:
      echo "Hello World" | sudo tee index.html
3.Access the Web Page:

    Open a web browser.
    Enter the Public DNS address of your EC2 instance.
    You should see the "Hello World" message displayed on the page.
