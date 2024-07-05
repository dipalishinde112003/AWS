# Attaching a Static/Elastic IP to an EC2 Instance

This guide provides step-by-step instructions to attach a static/elastic IP address to an AWS EC2 instance using the AWS Management Console. This ensures that the instance retains the same public IP address even after it is stopped and started again.

## Prerequisites

- An AWS account
- An existing EC2 instance

## Steps

### 1. Allocate an Elastic IP Address

1. **Log in to AWS Management Console:**
   - Navigate to the EC2 Dashboard.

2. **Allocate Elastic IP:**
   - In the left-hand navigation pane, click on `Elastic IPs`.
   - Click on `Allocate Elastic IP address`.
   - Choose the `Amazon pool` option.
   - Click on `Allocate`.

3. **Note the Elastic IP Address:**
   - Once allocated, note down the Elastic IP address.

### 2. Associate the Elastic IP Address with Your EC2 Instance

1. **Associate Elastic IP:**
   - In the `Elastic IPs` section, select the Elastic IP address you just allocated.
   - Click on `Actions` and then `Associate Elastic IP address`.
   - In the `Instance` field, select the instance you want to associate the Elastic IP with.
   - Click on `Associate`.

### 3. Verify the Association

1. **Check Elastic IP:**
   - Go to the EC2 Dashboard.
   - Select `Instances` and find your instance.
   - Check the `Public IP` field to see if it matches the Elastic IP you allocated.

### 4. Release Elastic IP Address (Optional)

1. **Release Elastic IP:**
   - In the `Elastic IPs` section, select the Elastic IP address.
   - Click on `Actions` and then `Disassociate Elastic IP address`.
   - Confirm the disassociation.
   - Click on `Actions` and then `Release Elastic IP address`.
   - Confirm the release.

### Conclusion

You have successfully allocated and associated an Elastic IP address to your EC2 instance. This ensures that your instance retains the same public IP address even after it is stopped and started again.
