# Windows EC2 Instance Setup and RDP Connection from Linux using Remmina

This guide provides step-by-step instructions to create a Windows EC2 instance on AWS, retrieve the password, and connect to it using Remmina on a Linux machine.

## Prerequisites

- An AWS account
- Remmina installed on your Linux machine

## Steps

### 1. Create an EC2 Instance

1. **Log in to AWS Management Console:**
   - Navigate to the EC2 Dashboard.

2. **Launch an Instance:**
   - Click on `Launch Instance`.
   - Choose an Amazon Machine Image (AMI). For this example, select `Microsoft Windows Server`.
   - Choose an Instance Type. For a simple setup, `t2.micro` is sufficient.
   - Configure Instance Details. Ensure you have the right network settings.
   - Add Storage if needed.
   - Add Tags (optional).
   - Configure Security Group:
     - Add a rule for RDP (port 3389) to allow you to connect to the Windows instance.

3. **Launch and Connect:**
   - Review and launch the instance.
   - Download the key pair if prompted (if it's a new key pair).
   - Wait for the instance to start running.

### 2. Retrieve the Administrator Password

1. **Retrieve the Password:**
   - In the EC2 Console, select your instance.
   - Click on `Connect`, then `Get Password`.
   - Decrypt the password using the key pair you downloaded.

### 3. Install and Configure Remmina on Linux

1. **Install Remmina:**
   - Open a terminal and run the following commands to install Remmina:
     ```sh
     sudo apt update
     sudo apt install remmina remmina-plugin-rdp
     ```

2. **Configure Remmina:**
   - Open Remmina from your applications menu.
   - Click on the `+` icon to create a new connection.
   - Set the `Name` to something descriptive (e.g., "AWS Windows Instance").
   - Set the `Protocol` to `RDP - Remote Desktop Protocol`.
   - Enter the `Server` address, which is the public DNS (IPv4) address of your instance.
   - Enter the `Username` as `Administrator`.
   - Enter the `Password` you retrieved and decrypted from the AWS Console.

3. **Connect to the Instance:**
   - Save the connection settings.
   - Double-click on the new connection entry in Remmina.
   - If prompted, accept the certificate to establish the connection.

### Conclusion

You have successfully created a Windows EC2 instance on AWS, retrieved the password, and connected to it using Remmina from a Linux machine. You can now use this instance for various purposes like hosting applications, running scripts, or other tasks that require a Windows environment.
