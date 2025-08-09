# AWS Solutions Architect Associate Practice Questions

This repository contains practice questions for the AWS Solutions Architect Associate certification exam. These questions cover various AWS services and architectural best practices.

## Table of Contents
- [Storage Solutions](#storage-solutions)
- [Compute and Auto Scaling](#compute-and-auto-scaling)
- [Networking](#networking)
- [Database Solutions](#database-solutions)
- [Security and Compliance](#security-and-compliance)
- [Monitoring and Analytics](#monitoring-and-analytics)
- [Migration and Transfer](#migration-and-transfer)
- [Serverless Architecture](#serverless-architecture)

## Storage Solutions

### Question 66: S3 Storage Lifecycle Management
A company has an application that generates a large number of files, each approximately 5 MB in size. The files are stored in Amazon S3. Company policy requires the files to be stored for 4 years before they can be deleted. Immediate accessibility is always required as the files contain critical business data that is not easy to reproduce. The files are frequently accessed in the first 30 days of object creation but are rarely accessed after the first 30 days.

**Which storage solution is MOST cost-effective?**

A) Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Glacier 30 days from object creation. Delete the files 4 years after object creation.

B) Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) 30 days from object creation. Delete the files 4 years after object creation.

C) Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Delete the files 4 years after object creation.

D) Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Move the files to S3 Glacier 4 years after object creation.

---

### Question 72: S3 Data Transfer Cost Optimization
A company runs a photo processing application that needs to frequently upload and download pictures from Amazon S3 buckets that are located in the same AWS Region. A solutions architect has noticed an increased cost in data transfer fees and needs to implement a solution to reduce these costs.

**How can the solutions architect meet this requirement?**

A) Deploy Amazon API Gateway into a public subnet and adjust the route table to route S3 calls through it.

B) Deploy a NAT gateway into a public subnet and attach an endpoint policy that allows access to the S3 buckets.

C) Deploy the application into a public subnet and allow it to route through an internet gateway to access the S3 buckets.

D) Deploy an S3 VPC gateway endpoint into the VPC and attach an endpoint policy that allows access to the S3 buckets.

---

### Question 85: Document Immutability Requirements
A company has a production web application in which users upload documents through a web interface or a mobile app. According to a new regulatory requirement, new documents cannot be modified or deleted after they are stored.

**What should a solutions architect do to meet this requirement?**

A) Store the uploaded documents in an Amazon S3 bucket with S3 Versioning and S3 Object Lock enabled.

B) Store the uploaded documents in an Amazon S3 bucket. Configure an S3 Lifecycle policy to archive the documents periodically.

C) Store the uploaded documents in an Amazon S3 bucket with S3 Versioning enabled. Configure an ACL to restrict all access to read-only.

D) Store the uploaded documents on an Amazon Elastic File System (Amazon EFS) volume. Access the data by mounting the volume in read-only mode.

---

### Question 88: Cross-Account S3 Access Cost Optimization
A survey company has gathered data for several years from areas in the United States. The company hosts the data in an Amazon S3 bucket that is 3 TB in size and growing. The company has started to share the data with a European marketing firm that has S3 buckets. The company wants to ensure that its data transfer costs remain as low as possible.

**Which solution will meet these requirements?**

A) Configure the Requester Pays feature on the company's S3 bucket.

B) Configure S3 Cross-Region Replication from the company's S3 bucket to one of the marketing firm's S3 buckets.

C) Configure cross-account access for the marketing firm so that the marketing firm has access to the company's S3 bucket.

D) Configure the company's S3 bucket to use S3 Intelligent-Tiering. Sync the S3 bucket to one of the marketing firm's S3 buckets.

---

### Question 89: S3 Audit Document Security
A company uses Amazon S3 to store its confidential audit documents. The S3 bucket uses bucket policies to restrict access to audit team IAM user credentials according to the principle of least privilege. Company managers are worried about accidental deletion of documents in the S3 bucket and want a more secure solution.

**What should a solutions architect do to secure the audit documents?**

A) Enable the versioning and MFA Delete features on the S3 bucket.

B) Enable multi-factor authentication (MFA) on the IAM user credentials for each audit team IAM user account.

C) Add an S3 Lifecycle policy to the audit team's IAM user accounts to deny the s3:DeleteObject action during audit dates.

D) Use AWS Key Management Service (AWS KMS) to encrypt the S3 bucket and restrict audit team IAM user accounts from accessing the KMS key.

---

### Question 106: S3 Encryption with Compliance Requirements
A company is preparing to store confidential data in Amazon S3. For compliance reasons, the data must be encrypted at rest. Encryption key usage must be logged for auditing purposes. Keys must be rotated every year.

**Which solution meets these requirements and is the MOST operationally efficient?**

A) Server-side encryption with customer-provided keys (SSE-C)

B) Server-side encryption with Amazon S3 managed keys (SSE-S3)

C) Server-side encryption with AWS KMS keys (SSE-KMS) with manual rotation

D) Server-side encryption with AWS KMS keys (SSE-KMS) with automatic rotation

---

### Question 109: S3 Object Immutability with Selective Deletion
A company needs to store data in Amazon S3 and must prevent the data from being changed. The company wants new objects that are uploaded to Amazon S3 to remain unchangeable for a nonspecific amount of time until the company decides to modify the objects. Only specific users in the company's AWS account can have the ability to delete the objects.

**What should a solutions architect do to meet these requirements?**

A) Create an S3 Glacier vault. Apply a write-once, read-many (WORM) vault lock policy to the objects.

B) Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Set a retention period of 100 years. Use governance mode as the S3 bucket's default retention mode for new objects.

C) Create an S3 bucket. Use AWS CloudTrail to track any S3 API events that modify the objects. Upon notification, restore the modified objects from any backup versions that the company has.

D) Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Add a legal hold to the objects. Add the s3:PutObjectLegalHold permission to the IAM policies of users who need to delete the objects.

---

## Compute and Auto Scaling

### Question 67: SQS Message Processing Duplication
A company hosts an application on multiple Amazon EC2 instances. The application processes messages from an Amazon SQS queue, writes to an Amazon RDS table, and deletes the message from the queue. Occasional duplicate records are found in the RDS table. The SQS queue does not contain any duplicate messages.

**What should a solutions architect do to ensure messages are being processed once only?**

A) Use the CreateQueue API call to create a new queue.

B) Use the AddPermission API call to add appropriate permissions.

C) Use the ReceiveMessage API call to set an appropriate wait time.

D) Use the ChangeMessageVisibility API call to increase the visibility timeout.

---

### Question 70: Network Load Balancer Health Checks
A company's HTTP application is behind a Network Load Balancer (NLB). The NLB's target group is configured to use an Amazon EC2 Auto Scaling group with multiple EC2 instances that run the web service. The company notices that the NLB is not detecting HTTP errors for the application. These errors require a manual restart of the EC2 instances that run the web service. The company needs to improve the application's availability without writing custom scripts or code.

**What should a solutions architect do to meet these requirements?**

A) Enable HTTP health checks on the NLB, supplying the URL of the company's application.

B) Add a cron job to the EC2 instances to check the local application's logs once each minute. If HTTP errors are detected, the application will restart.

C) Replace the NLB with an Application Load Balancer. Enable HTTP health checks by supplying the URL of the company's application. Configure an Auto Scaling action to replace unhealthy instances.

D) Create an Amazon CloudWatch alarm that monitors the UnhealthyHostCount metric for the NLB. Configure an Auto Scaling action to replace unhealthy instances when the alarm is in the ALARM state.

---

### Question 81: Parallel Processing with Auto Scaling
A solutions architect is designing the cloud architecture for a new application being deployed on AWS. The process should run in parallel while adding and removing application nodes as needed based on the number of jobs to be processed. The processor application is stateless. The solutions architect must ensure that the application is loosely coupled and the job items are durably stored.

**Which design should the solutions architect use?**

A) Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch configuration that uses the AMI. Create an Auto Scaling group using the launch configuration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on CPU usage.

B) Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch configuration that uses the AMI. Create an Auto Scaling group using the launch configuration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on network usage.

C) Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of items in the SQS queue.

D) Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of messages published to the SNS topic.

---

### Question 84: EC2 Instance Cost Optimization
A company wants to reduce the cost of its existing three-tier web architecture. The web, application, and database servers are running on Amazon EC2 instances for the development, test, and production environments. The EC2 instances average 30% CPU utilization during peak hours and 10% CPU utilization during non-peak hours. The production EC2 instances run 24 hours a day. The development and test EC2 instances run for at least 8 hours each day. The company plans to implement automation to stop the development and test EC2 instances when they are not in use.

**Which EC2 instance purchasing solution will meet the company's requirements MOST cost-effectively?**

A) Use Spot Instances for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.

B) Use Reserved Instances for the production EC2 instances. Use On-Demand Instances for the development and test EC2 instances.

C) Use Spot blocks for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.

D) Use On-Demand Instances for the production EC2 instances. Use Spot blocks for the development and test EC2 instances.

---

### Question 96: IAM Policy Effect Analysis
An Amazon EC2 administrator created the following policy associated with an IAM group containing several users:

**What is the effect of this policy?**

A) Users can terminate an EC2 instance in any AWS Region except us-east-1.

B) Users can terminate an EC2 instance with the IP address 10.100.100.1 in the us-east-1 Region.

C) Users can terminate an EC2 instance in the us-east-1 Region when the user's source IP is 10.100.100.254.

D) Users cannot terminate an EC2 instance in the us-east-1 Region when the user's source IP is 10.100.100.254.

---

### Question 112: Containerized Application Migration
A company hosts a containerized web application on a fleet of on-premises servers that process incoming requests. The number of requests is growing quickly. The on-premises servers cannot handle the increased number of requests. The company wants to move the application to AWS with minimum code changes and minimum development effort.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Use AWS Fargate on Amazon Elastic Container Service (Amazon ECS) to run the containerized web application with Service Auto Scaling. Use an Application Load Balancer to distribute the incoming requests.

B) Use two Amazon EC2 instances to host the containerized web application. Use an Application Load Balancer to distribute the incoming requests.

C) Use AWS Lambda with a new code that uses one of the supported languages. Create multiple Lambda functions to support the load. Use Amazon API Gateway as an entry point to the Lambda functions.

D) Use a high performance computing (HPC) solution such as AWS ParallelCluster to establish an HPC cluster that can process the incoming requests at the appropriate scale.

---

## Networking

### Question 68: Hybrid Connectivity with Cost Optimization
A solutions architect is designing a new hybrid architecture to extend a company's on-premises infrastructure to AWS. The company requires a highly available connection with consistent low latency to an AWS Region. The company needs to minimize costs and is willing to accept slower traffic if the primary connection fails.

**What should the solutions architect do to meet these requirements?**

A) Provision an AWS Direct Connect connection to a Region. Provision a VPN connection as a backup if the primary Direct Connect connection fails.

B) Provision a VPN tunnel connection to a Region for private connectivity. Provision a second VPN tunnel for private connectivity and as a backup if the primary VPN connection fails.

C) Provision an AWS Direct Connect connection to a Region. Provision a second Direct Connect connection to the same Region as a backup if the primary Direct Connect connection fails.

D) Provision an AWS Direct Connect connection to a Region. Use the Direct Connect failover attribute from the AWS CLI to automatically create a backup connection if the primary Direct Connect connection fails.

---

### Question 73: Bastion Host Security Configuration
A company recently launched Linux-based application instances on Amazon EC2 in a private subnet and launched a Linux-based bastion host on an Amazon EC2 instance in a public subnet of a VPC. A solutions architect needs to connect from the on-premises network, through the company's internet connection, to the bastion host, and to the application servers. The solutions architect must make sure that the security groups of all the EC2 instances will allow that access.

**Which combination of steps should the solutions architect take to meet these requirements? (Choose two.)**

A) Replace the current security group of the bastion host with one that only allows inbound access from the application instances.

B) Replace the current security group of the bastion host with one that only allows inbound access from the internal IP range for the company.

C) Replace the current security group of the bastion host with one that only allows inbound access from the external IP range for the company.

D) Replace the current security group of the application instances with one that allows inbound SSH access from only the private IP address of the bastion host.

E) Replace the current security group of the application instances with one that allows inbound SSH access from only the public IP address of the bastion host.

---

### Question 74: Two-Tier Web Application Security Groups
A solutions architect is designing a two-tier web application. The application consists of a public-facing web tier hosted on Amazon EC2 in public subnets. The database tier consists of Microsoft SQL Server running on Amazon EC2 in a private subnet. Security is a high priority for the company.

**How should security groups be configured in this situation? (Choose two.)**

A) Configure the security group for the web tier to allow inbound traffic on port 443 from 0.0.0.0/0.

B) Configure the security group for the web tier to allow outbound traffic on port 443 from 0.0.0.0/0.

C) Configure the security group for the database tier to allow inbound traffic on port 1433 from the security group for the web tier.

D) Configure the security group for the database tier to allow outbound traffic on ports 443 and 1433 to the security group for the web tier.

E) Configure the security group for the database tier to allow inbound traffic on ports 443 and 1433 from the security group for the web tier.

---

### Question 83: Global Content Delivery Optimization
A company's dynamic website is hosted using on-premises servers in the United States. The company is launching its product in Europe, and it wants to optimize site loading times for new European users. The site's backend must remain in the United States. The product is being launched in a few days, and an immediate solution is needed.

**What should the solutions architect recommend?**

A) Launch an Amazon EC2 instance in us-east-1 and migrate the site to it.

B) Move the website to Amazon S3. Use Cross-Region Replication between Regions.

C) Use Amazon CloudFront with a custom origin pointing to the on-premises servers.

D) Use an Amazon Route 53 geoproximity routing policy pointing to on-premises servers.

---

### Question 91: VPC Private S3 Access
A company has applications that run on Amazon EC2 instances in a VPC. One of the applications needs to call the Amazon S3 API to store and read objects. According to the company's security regulations, no traffic from the applications is allowed to travel across the internet.

**Which solution will meet these requirements?**

A) Configure an S3 gateway endpoint.

B) Create an S3 bucket in a private subnet.

C) Create an S3 bucket in the same AWS Region as the EC2 instances.

D) Configure a NAT gateway in the same subnet as the EC2 instances.

---

### Question 92: Secure VPC to S3 Access
A company is storing sensitive user information in an Amazon S3 bucket. The company wants to provide secure access to this bucket from the application tier running on Amazon EC2 instances inside a VPC.

**Which combination of steps should a solutions architect take to accomplish this? (Choose two.)**

A) Configure a VPC gateway endpoint for Amazon S3 within the VPC.

B) Create a bucket policy to make the objects in the S3 bucket public.

C) Create a bucket policy that limits access to only the application tier running in the VPC.

D) Create an IAM user with an S3 access policy and copy the IAM credentials to the EC2 instance.

E) Create a NAT instance and have the EC2 instances use the NAT instance to access the S3 bucket.

---

### Question 101: Private Subnet Internet Access
A solutions architect is designing a VPC with public and private subnets. The VPC and subnets use IPv4 CIDR blocks. There is one public subnet and one private subnet in each of three Availability Zones (AZs) for high availability. An internet gateway is used to provide internet access for the public subnets. The private subnets require access to the internet to allow Amazon EC2 instances to download software updates.

**What should the solutions architect do to enable Internet access for the private subnets?**

A) Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT gateway in its AZ.

B) Create three NAT instances, one for each private subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT instance in its AZ.

C) Create a second internet gateway on one of the private subnets. Update the route table for the private subnets that forward non-VPC traffic to the private internet gateway.

D) Create an egress-only internet gateway on one of the public subnets. Update the route table for the private subnets that forward non-VPC traffic to the egress-only Internet gateway.

---

### Question 115: Private Route for S3 Traffic
A medical records company is hosting an application on Amazon EC2 instances. The application processes customer data files that are stored on Amazon S3. The EC2 instances are hosted in public subnets. The EC2 instances access Amazon S3 over the internet, but they do not require any other network access. A new requirement mandates that the network traffic for file transfers take a private route and not be sent over the internet.

**Which change to the network architecture should a solutions architect recommend to meet this requirement?**

A) Create a NAT gateway. Configure the route table for the public subnets to send traffic to Amazon S3 through the NAT gateway.

B) Configure the security group for the EC2 instances to restrict outbound traffic so that only traffic to the S3 prefix list is permitted.

C) Move the EC2 instances to private subnets. Create a VPC endpoint for Amazon S3, and link the endpoint to the route table for the private subnets.

D) Remove the internet gateway from the VPC. Set up an AWS Direct Connect connection, and route traffic to Amazon S3 over the Direct Connect connection.

---

## Database Solutions

### Question 69: Multi-AZ Database High Availability
A company is running a business-critical web application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances are in an Auto Scaling group. The application uses an Amazon Aurora PostgreSQL database that is deployed in a single Availability Zone. The company wants the application to be highly available with minimum downtime and minimum loss of data.

**Which solution will meet these requirements with the LEAST operational effort?**

A) Place the EC2 instances in different AWS Regions. Use Amazon Route 53 health checks to redirect traffic. Use Aurora PostgreSQL Cross-Region Replication.

B) Configure the Auto Scaling group to use multiple Availability Zones. Configure the database as Multi-AZ. Configure an Amazon RDS Proxy instance for the database.

C) Configure the Auto Scaling group to use one Availability Zone. Generate hourly snapshots of the database. Recover the database from the snapshots in the event of a failure.

D) Configure the Auto Scaling group to use multiple AWS Regions. Write the data from the application to Amazon S3. Use S3 Event Notifications to launch an AWS Lambda function to write the data to the database.

---

### Question 71: DynamoDB Recovery Requirements
A company runs a shopping application that uses Amazon DynamoDB to store customer information. In case of data corruption, a solutions architect needs to design a solution that meets a recovery point objective (RPO) of 15 minutes and a recovery time objective (RTO) of 1 hour.

**What should the solutions architect recommend to meet these requirements?**

A) Configure DynamoDB global tables. For RPO recovery, point the application to a different AWS Region.

B) Configure DynamoDB point-in-time recovery. For RPO recovery, restore to the desired point in time.

C) Export the DynamoDB data to Amazon S3 Glacier on a daily basis. For RPO recovery, import the data from S3 Glacier to DynamoDB.

D) Schedule Amazon Elastic Block Store (Amazon EBS) snapshots for the DynamoDB table every 15 minutes. For RPO recovery, restore the DynamoDB table by using the EBS snapshot.

---

### Question 78: DynamoDB Long-term Data Retention
A company needs to keep user transaction data in an Amazon DynamoDB table. The company must retain the data for 7 years.

**What is the MOST operationally efficient solution that meets these requirements?**

A) Use DynamoDB point-in-time recovery to back up the table continuously.

B) Use AWS Backup to create backup schedules and retention policies for the table.

C) Create an on-demand backup of the table by using the DynamoDB console. Store the backup in an Amazon S3 bucket. Set an S3 Lifecycle configuration for the S3 bucket.

D) Create an Amazon EventBridge (Amazon CloudWatch Events) rule to invoke an AWS Lambda function. Configure the Lambda function to back up the table and to store the backup in an Amazon S3 bucket. Set an S3 Lifecycle configuration for the S3 bucket.

---

### Question 79: DynamoDB Capacity Planning
A company is planning to use an Amazon DynamoDB table for data storage. The company is concerned about cost optimization. The table will not be used on most mornings. In the evenings, the read and write traffic will often be unpredictable. When traffic spikes occur, they will happen very quickly.

**What should a solutions architect recommend?**

A) Create a DynamoDB table in on-demand capacity mode.

B) Create a DynamoDB table with a global secondary index.

C) Create a DynamoDB table with provisioned capacity and auto scaling.

D) Create a DynamoDB table in provisioned capacity mode, and configure it as a global table.

---

