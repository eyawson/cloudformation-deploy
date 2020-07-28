# Background

Your company is creating an Instagram clone called Udagram. Developers pushed the latest version of their code in a zip file located in a public S3 Bucket.

You have been tasked with deploying the application, along with the necessary supporting software into its matching infrastructure.

This needs to be done in an automated fashion so that the infrastructure can be discarded as soon as the testing team finishes their tests and gathers their results.

## Server Specs

- Launch Configuration
  - 4 servers
    - 2 in each PRIVATE SUBNET
      - 2 vCPU
      - 4gb Ram
      - Ubuntu 18 OS
      - 10gb space

## Security Grps and Roles

- S3 IAM Role
- HTTP Port: 80 (default)
- Load Balancer
  - Load Balancer Health Check
  - Allow all traffic on port 80
  - Outbound on port 80 to servers
  - Deployed in public subnet

- Cloudformation script export > url of load balancer
- BONUS: add <http://> in front of LB DNS Name

## Extra Help

1. While your instances are in public subnets, you'll also need the SSH port open (port 22) for your access, in case you need to troubleshoot your instances.

2. Log information for UserData scripts is located in this file: cloud-init-output.log under the folder: /var/log
