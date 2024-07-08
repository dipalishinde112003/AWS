# Block Storage Project on AWS

This guide outlines the steps to create and manage block storage volumes in different availability zones (AZs) on AWS, connect to an instance, and manage the volumes.

## Prerequisites

- An active AWS account

## Steps

### 1. Create Two Volumes in AP South A and AP South B Availability Zones

1. Open the AWS Management Console.
2. Navigate to the EC2 Dashboard.
3. In the left-hand menu, under "Elastic Block Store," click on "Volumes."
4. Click the "Create Volume" button.
5. Configure the first volume:
   - **Volume Type**: General Purpose SSD (gp2)
   - **Size**: 5 GiB
   - **Availability Zone**: ap-south-1a
6. Click "Create Volume."
7. Repeat steps 4-6 to create the second volume, but set the **Availability Zone** to ap-south-1b.

### 2. Create an Instance in AP South A and Add a New Volume

1. In the EC2 Dashboard, click "Instances" in the left-hand menu.
2. Click the "Launch Instance" button.
3. Configure the instance:
   - **Name and tags**: Name the instance.
   - **Application and OS Images (Amazon Machine Image)**: Select "Ubuntu Server 20.04 LTS (HVM), SSD Volume Type."
   - **Instance Type**: Select t2.micro.
   - **Key pair (login)**: Select an existing key pair or create a new one.
   - **Network settings**: Use default settings.
   - **Configure storage**: Add a new volume.
     - **Volume Type**: General Purpose SSD (gp3)
     - **Size**: 6 GiB
     - **Availability Zone**: ap-south-1a
4. Click "Launch Instance."

### 3. Verify Volumes:

- In volume option now total 4 volumes are available 3 in ap-south-a and 1 in ap-south-b
- Run the lsblk command to list the block devices:
  lsblk
### 4. Attempt to Attach Volume from AP South B to Instance in AP South A (Expected to Fail)

    In the AWS Management Console, navigate to the "Volumes" section.
    Select the volume in ap-south-1b.
    Click "Actions" and select "Attach Volume."
    Attempt to attach it to the instance in ap-south-1a (this should fail due to different AZs).

### 5. Attach Volume from AP South A to Instance in AP South A (Expected to Succeed)

    In the AWS Management Console, navigate to the "Volumes" section.
    Select the volume in ap-south-1a.
    Click "Actions" and select "Attach Volume."
    Select your instance from the dropdown menu and attach the volume.

### 6. Detach the Volume from the Instance

    In the AWS Management Console, navigate to the "Volumes" section.
    Select the attached volume in ap-south-1a.
    Click "Actions" and select "Detach Volume."
