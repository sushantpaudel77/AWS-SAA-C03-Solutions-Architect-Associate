# AWS Solutions Architect Associate Practice Questions

This repository contains a comprehensive collection of AWS Solutions Architect Associate certification practice questions covering various AWS services and architectural patterns.

## Table of Contents
- [Questions Overview](#questions-overview)
- [Topics Covered](#topics-covered)
- [How to Use](#how-to-use)
- [Answer Key](#answer-key)
- [Contributing](#contributing)

## Questions Overview

This collection includes 30 practice questions (391-420) that test knowledge across core AWS services and architectural best practices. Each question is designed to simulate the real AWS Solutions Architect Associate exam experience.

## Topics Covered

- **Backup and Recovery Strategies**
- **Security Groups and Network Security**
- **Data Processing and Analytics**
- **Storage Solutions**
- **High Availability and Scalability**
- **Serverless Architecture**
- **Database Management**
- **Monitoring and Logging**
- **Cost Optimization**
- **Migration Strategies**

---

## Practice Questions

### Question 391 - Backup Strategy for Three-Tier Application
A company needs a backup strategy for its three-tier stateless web application. The web application runs on Amazon EC2 instances in an Auto Scaling group with a dynamic scaling policy that is configured to respond to scaling events. The database tier runs on Amazon RDS for PostgreSQL. The web application does not require temporary local storage on the EC2 instances. The company's recovery point objective (RPO) is 2 hours. The backup strategy must maximize scalability and optimize resource utilization for this environment.

**Which solution will meet these requirements?**

A) Take snapshots of Amazon Elastic Block Store (Amazon EBS) volumes of the EC2 instances and database every 2 hours to meet the RPO.

B) Configure a snapshot lifecycle policy to take Amazon Elastic Block Store (Amazon EBS) snapshots. Enable automated backups in Amazon RDS to meet the RPO.

C) Retain the latest Amazon Machine Images (AMIs) of the web and application tiers. Enable automated backups in Amazon RDS and use point-in-time recovery to meet the RPO.

D) Take snapshots of Amazon Elastic Block Store (Amazon EBS) volumes of the EC2 instances every 2 hours. Enable automated backups in Amazon RDS and use point-in-time recovery to meet the RPO.

---

### Question 392 - Security Group Configuration for Web Application
A company wants to deploy a new public web application on AWS. The application includes a web server tier that uses Amazon EC2 instances. The application also includes a database tier that uses an Amazon RDS for MySQL DB instance. The application must be secure and accessible for global customers that have dynamic IP addresses.

**How should a solutions architect configure the security groups to meet these requirements?**

A) Configure the security group for the web servers to allow inbound traffic on port 443 from 0.0.0.0/0. Configure the security group for the DB instance to allow inbound traffic on port 3306 from the security group of the web servers.

B) Configure the security group for the web servers to allow inbound traffic on port 443 from the IP addresses of the customers. Configure the security group for the DB instance to allow inbound traffic on port 3306 from the security group of the web servers.

C) Configure the security group for the web servers to allow inbound traffic on port 443 from the IP addresses of the customers. Configure the security group for the DB instance to allow inbound traffic on port 3306 from the IP addresses of the customers.

D) Configure the security group for the web servers to allow inbound traffic on port 443 from 0.0.0.0/0. Configure the security group for the DB instance to allow inbound traffic on port 3306 from 0.0.0.0/0.

---

### Question 393 - Audio Processing with PII Redaction
A payment processing company records all voice communication with its customers and stores the audio files in an Amazon S3 bucket. The company needs to capture the text from the audio files. The company must remove from the text any personally identifiable information (PII) that belongs to customers.

**What should a solutions architect do to meet these requirements?**

A) Process the audio files by using Amazon Kinesis Video Streams. Use an AWS Lambda function to scan for known PII patterns.

B) When an audio file is uploaded to the S3 bucket, invoke an AWS Lambda function to start an Amazon Textract task to analyze the call recordings.

C) Configure an Amazon Transcribe transcription job with PII redaction turned on. When an audio file is uploaded to the S3 bucket, invoke an AWS Lambda function to start the transcription job. Store the output in a separate S3 bucket.

D) Create an Amazon Connect contact flow that ingests the audio files with transcription turned on. Embed an AWS Lambda function to scan for known PII patterns. Use Amazon EventBridge to start the contact flow when an audio file is uploaded to the S3 bucket.

---

### Question 394 - Database Performance Optimization
A company is running a multi-tier ecommerce web application in the AWS Cloud. The application runs on Amazon EC2 instances with an Amazon RDS for MySQL Multi-AZ DB instance. Amazon RDS is configured with the latest generation DB instance with 2,000 GB of storage in a General Purpose SSD (gp3) Amazon Elastic Block Store (Amazon EBS) volume. The database performance affects the application during periods of high demand. A database administrator analyzes the logs in Amazon CloudWatch Logs and discovers that the application performance always degrades when the number of read and write IOPS is higher than 20,000.

**What should a solutions architect do to improve the application performance?**

A) Replace the volume with a magnetic volume.

B) Increase the number of IOPS on the gp3 volume.

C) Replace the volume with a Provisioned IOPS SSD (io2) volume.

D) Replace the 2,000 GB gp3 volume with two 1,000 GB gp3 volumes.

---

### Question 395 - Tracking Configuration Changes
An IAM user made several configuration changes to AWS resources in their company's account during a production deployment last week. A solutions architect learned that a couple of security group rules are not configured as desired. The solutions architect wants to confirm which IAM user was responsible for making changes.

**Which service should the solutions architect use to find the desired information?**

A) Amazon GuardDuty

B) Amazon Inspector

C) AWS CloudTrail

D) AWS Config

---

### Question 396 - DDoS Protection for Self-Managed DNS
A company has implemented a self-managed DNS service on AWS. The solution consists of the following:
- Amazon EC2 instances in different AWS Regions
- Endpoints of a standard accelerator in AWS Global Accelerator

The company wants to protect the solution against DDoS attacks.

**What should a solutions architect do to meet this requirement?**

A) Subscribe to AWS Shield Advanced. Add the accelerator as a resource to protect.

B) Subscribe to AWS Shield Advanced. Add the EC2 instances as resources to protect.

C) Create an AWS WAF web ACL that includes a rate-based rule. Associate the web ACL with the accelerator.

D) Create an AWS WAF web ACL that includes a rate-based rule. Associate the web ACL with the EC2 instances.

---

### Question 397 - Scheduled Data Processing Job
An ecommerce company needs to run a scheduled daily job to aggregate and filter sales records for analytics. The company stores the sales records in an Amazon S3 bucket. Each object can be up to 10 GB in size. Based on the number of sales events, the job can take up to an hour to complete. The CPU and memory usage of the job are constant and are known in advance. A solutions architect needs to minimize the amount of operational effort that is needed for the job to run.

**Which solution meets these requirements?**

A) Create an AWS Lambda function that has an Amazon EventBridge notification. Schedule the EventBridge event to run once a day.

B) Create an AWS Lambda function. Create an Amazon API Gateway HTTP API, and integrate the API with the function. Create an Amazon EventBridge scheduled event that calls the API and invokes the function.

C) Create an Amazon Elastic Container Service (Amazon ECS) cluster with an AWS Fargate launch type. Create an Amazon EventBridge scheduled event that launches an ECS task on the cluster to run the job.

D) Create an Amazon Elastic Container Service (Amazon ECS) cluster with an Amazon EC2 launch type and an Auto Scaling group with at least one EC2 instance. Create an Amazon EventBridge scheduled event that launches an ECS task on the cluster to run the job.

---

### Question 398 - Large Data Transfer to AWS
A company needs to transfer 600 TB of data from its on-premises network-attached storage (NAS) system to the AWS Cloud. The data transfer must be complete within 2 weeks. The data is sensitive and must be encrypted in transit. The company's internet connection can support an upload speed of 100 Mbps.

**Which solution meets these requirements MOST cost-effectively?**

A) Use Amazon S3 multi-part upload functionality to transfer the files over HTTPS.

B) Create a VPN connection between the on-premises NAS system and the nearest AWS Region. Transfer the data over the VPN connection.

C) Use the AWS Snow Family console to order several AWS Snowball Edge Storage Optimized devices. Use the devices to transfer the data to Amazon S3.

D) Set up a 10 Gbps AWS Direct Connect connection between the company location and the nearest AWS Region. Transfer the data over a VPN connection into the Region to store the data in Amazon S3.

---

### Question 399 - API Protection from HTTP Flood Attacks
A financial company hosts a web application on AWS. The application uses an Amazon API Gateway Regional API endpoint to give users the ability to retrieve current stock prices. The company's security team has noticed an increase in the number of API requests. The security team is concerned that HTTP flood attacks might take the application offline. A solutions architect must design a solution to protect the application from this type of attack.

**Which solution meets these requirements with the LEAST operational overhead?**

A) Create an Amazon CloudFront distribution in front of the API Gateway Regional API endpoint with a maximum TTL of 24 hours.

B) Create a Regional AWS WAF web ACL with a rate-based rule. Associate the web ACL with the API Gateway stage.

C) Use Amazon CloudWatch metrics to monitor the Count metric and alert the security team when the predefined rate is reached.

D) Create an Amazon CloudFront distribution with Lambda@Edge in front of the API Gateway Regional API endpoint. Create an AWS Lambda function to block requests from IP addresses that exceed the predefined rate.

---

### Question 400 - Event Notification System
A meteorological startup company has a custom web application to sell weather data to its users online. The company uses Amazon DynamoDB to store its data and wants to build a new service that sends an alert to the managers of four internal teams every time a new weather event is recorded. The company does not want this new service to affect the performance of the current application.

**What should a solutions architect do to meet these requirements with the LEAST amount of operational overhead?**

A) Use DynamoDB transactions to write new event data to the table. Configure the transactions to notify internal teams.

B) Have the current application publish a message to four Amazon Simple Notification Service (Amazon SNS) topics. Have each team subscribe to one topic.

C) Enable Amazon DynamoDB Streams on the table. Use triggers to write to a single Amazon Simple Notification Service (Amazon SNS) topic to which the teams can subscribe.

D) Add a custom attribute to each record to flag new items. Write a cron job that scans the table every minute for items that are new and notifies an Amazon Simple Queue Service (Amazon SQS) queue to which the teams can subscribe.

---

### Question 401 - High Availability and Resilience
A company wants to use the AWS Cloud to make an existing application highly available and resilient. The current version of the application resides in the company's data center. The application recently experienced data loss after a database server crashed because of an unexpected power outage. The company needs a solution that avoids any single points of failure. The solution must give the application the ability to scale to meet user demand.

**Which solution will meet these requirements?**

A) Deploy the application servers by using Amazon EC2 instances in an Auto Scaling group across multiple Availability Zones. Use an Amazon RDS DB instance in a Multi-AZ configuration.

B) Deploy the application servers by using Amazon EC2 instances in an Auto Scaling group in a single Availability Zone. Deploy the database on an EC2 instance. Enable EC2 Auto Recovery.

C) Deploy the application servers by using Amazon EC2 instances in an Auto Scaling group across multiple Availability Zones. Use an Amazon RDS DB instance with a read replica in a single Availability Zone. Promote the read replica to replace the primary DB instance if the primary DB instance fails.

D) Deploy the application servers by using Amazon EC2 instances in an Auto Scaling group across multiple Availability Zones. Deploy the primary and secondary database servers on EC2 instances across multiple Availability Zones. Use Amazon Elastic Block Store (Amazon EBS) Multi-Attach to create shared storage between the instances.

---

### Question 402 - Kinesis Data Streams Configuration
A company needs to ingest and handle large amounts of streaming data that its application generates. The application runs on Amazon EC2 instances and sends data to Amazon Kinesis Data Streams, which is configured with default settings. Every other day, the application consumes the data and writes the data to an Amazon S3 bucket for business intelligence (BI) processing. The company observes that Amazon S3 is not receiving all the data that the application sends to Kinesis Data Streams.

**What should a solutions architect do to resolve this issue?**

A) Update the Kinesis Data Streams default settings by modifying the data retention period.

B) Update the application to use the Kinesis Producer Library (KPL) to send the data to Kinesis Data Streams.

C) Update the number of Kinesis shards to handle the throughput of the data that is sent to Kinesis Data Streams.

D) Turn on S3 Versioning within the S3 bucket to preserve every version of every object that is ingested in the S3 bucket.

---

### Question 403 - Lambda Function Permissions
A developer has an application that uses an AWS Lambda function to upload files to Amazon S3 and needs the required permissions to perform the task. The developer already has an IAM user with valid IAM credentials required for Amazon S3.

**What should a solutions architect do to grant the permissions?**

A) Add required IAM permissions in the resource policy of the Lambda function.

B) Create a signed request using the existing IAM credentials in the Lambda function.

C) Create a new IAM user and use the existing IAM credentials in the Lambda function.

D) Create an IAM execution role with the required permissions and attach the IAM role to the Lambda function.

---

### Question 404 - Serverless Application Processing Issues
A company has deployed a serverless application that invokes an AWS Lambda function when new documents are uploaded to an Amazon S3 bucket. The application uses the Lambda function to process the documents. After a recent marketing campaign, the company noticed that the application did not process many of the documents.

**What should a solutions architect do to improve the architecture of this application?**

A) Set the Lambda function's runtime timeout value to 15 minutes.

B) Configure an S3 bucket replication policy. Stage the documents in the S3 bucket for later processing.

C) Deploy an additional Lambda function. Load balance the processing of the documents across the two Lambda functions.

D) Create an Amazon Simple Queue Service (Amazon SQS) queue. Send the requests to the queue. Configure the queue as an event source for Lambda.

---

### Question 405 - Auto Scaling for Demonstration Environment
A solutions architect is designing the architecture for a software demonstration environment. The environment will run on Amazon EC2 instances in an Auto Scaling group behind an Application Load Balancer (ALB). The system will experience significant increases in traffic during working hours but is not required to operate on weekends.

**Which combination of actions should the solutions architect take to ensure that the system can scale to meet demand? (Choose two.)**

A) Use AWS Auto Scaling to adjust the ALB capacity based on request rate.

B) Use AWS Auto Scaling to scale the capacity of the VPC internet gateway.

C) Launch the EC2 instances in multiple AWS Regions to distribute the load across Regions.

D) Use a target tracking scaling policy to scale the Auto Scaling group based on instance CPU utilization.

E) Use scheduled scaling to change the Auto Scaling group minimum, maximum, and desired capacity to zero for weekends. Revert to the default values at the start of the week.

---

### Question 406 - Two-Tiered Architecture Security
A solutions architect is designing a two-tiered architecture that includes a public subnet and a database subnet. The web servers in the public subnet must be open to the internet on port 443. The Amazon RDS for MySQL DB instance in the database subnet must be accessible only to the web servers on port 3306.

**Which combination of steps should the solutions architect take to meet these requirements? (Choose two.)**

A) Create a network ACL for the public subnet. Add a rule to deny outbound traffic to 0.0.0.0/0 on port 3306.

B) Create a security group for the DB instance. Add a rule to allow traffic from the public subnet CIDR block on port 3306.

C) Create a security group for the web servers in the public subnet. Add a rule to allow traffic from 0.0.0.0/0 on port 443.

D) Create a security group for the DB instance. Add a rule to allow traffic from the web servers' security group on port 3306.

E) Create a security group for the DB instance. Add a rule to deny all traffic except traffic from the web servers' security group on port 3306.

---

### Question 407 - Lustre File System for Gaming Application
A company is implementing a shared storage solution for a gaming application that is hosted in the AWS Cloud. The company needs the ability to use Lustre clients to access data. The solution must be fully managed.

**Which solution meets these requirements?**

A) Create an AWS DataSync task that shares the data as a mountable file system. Mount the file system to the application server.

B) Create an AWS Storage Gateway file gateway. Create a file share that uses the required client protocol. Connect the application server to the file share.

C) Create an Amazon Elastic File System (Amazon EFS) file system, and configure it to support Lustre. Attach the file system to the origin server. Connect the application server to the file system.

D) Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

---

### Question 408 - Low Latency UDP Processing with Failover
A company runs an application that receives data from thousands of geographically dispersed remote devices that use UDP. The application processes the data immediately and sends a message back to the device if necessary. No data is stored. The company needs a solution that minimizes latency for the data transmission from the devices. The solution also must provide rapid failover to another AWS Region.

**Which solution will meet these requirements?**

A) Configure an Amazon Route 53 failover routing policy. Create a Network Load Balancer (NLB) in each of the two Regions. Configure the NLB to invoke an AWS Lambda function to process the data.

B) Use AWS Global Accelerator. Create a Network Load Balancer (NLB) in each of the two Regions as an endpoint. Create an Amazon Elastic Container Service (Amazon ECS) cluster with the Fargate launch type. Create an ECS service on the cluster. Set the ECS service as the target for the NLB. Process the data in Amazon ECS.

C) Use AWS Global Accelerator. Create an Application Load Balancer (ALB) in each of the two Regions as an endpoint. Create an Amazon Elastic Container Service (Amazon ECS) cluster with the Fargate launch type. Create an ECS service on the cluster. Set the ECS service as the target for the ALB. Process the data in Amazon ECS.

D) Configure an Amazon Route 53 failover routing policy. Create an Application Load Balancer (ALB) in each of the two Regions. Create an Amazon Elastic Container Service (Amazon ECS) cluster with the Fargate launch type. Create an ECS service on the cluster. Set the ECS service as the target for the ALB. Process the data in Amazon ECS.

---

### Question 409 - Windows File Share Migration
A solutions architect must migrate a Windows Internet Information Services (IIS) web application to AWS. The application currently relies on a file share hosted in the user's on-premises network-attached storage (NAS). The solutions architect has proposed migrating the IIS web servers to Amazon EC2 instances in multiple Availability Zones that are connected to the storage solution, and configuring an Elastic Load Balancer attached to the instances.

**Which replacement to the on-premises file share is MOST resilient and durable?**

A) Migrate the file share to Amazon RDS.

B) Migrate the file share to AWS Storage Gateway.

C) Migrate the file share to Amazon FSx for Windows File Server.

D) Migrate the file share to Amazon Elastic File System (Amazon EFS).

---

### Question 410 - EBS Encryption at Rest
A company is deploying a new application on Amazon EC2 instances. The application writes data to Amazon Elastic Block Store (Amazon EBS) volumes. The company needs to ensure that all data that is written to the EBS volumes is encrypted at rest.

**Which solution will meet this requirement?**

A) Create an IAM role that specifies EBS encryption. Attach the role to the EC2 instances.

B) Create the EBS volumes as encrypted volumes. Attach the EBS volumes to the EC2 instances.

C) Create an EC2 instance tag that has a key of Encrypt and a value of True. Tag all instances that require encryption at the EBS level.

D) Create an AWS Key Management Service (AWS KMS) key policy that enforces EBS encryption in the account. Ensure that the key policy is active.

---

### Question 411 - Cost-Effective Database for Sporadic Usage
A company has a web application with sporadic usage patterns. There is heavy usage at the beginning of each month, moderate usage at the start of each week, and unpredictable usage during the week. The application consists of a web server and a MySQL database server running inside the data center. The company would like to move the application to the AWS Cloud, and needs to select a cost-effective database platform that will not require database modifications.

**Which solution will meet these requirements?**

A) Amazon DynamoDB

B) Amazon RDS for MySQL

C) MySQL-compatible Amazon Aurora Serverless

D) MySQL deployed on Amazon EC2 in an Auto Scaling group

---

### Question 412 - S3 Public Access Prevention
An image-hosting company stores its objects in Amazon S3 buckets. The company wants to avoid accidental exposure of the objects in the S3 buckets to the public. All S3 objects in the entire AWS account need to remain private.

**Which solution will meet these requirements?**

A) Use Amazon GuardDuty to monitor S3 bucket policies. Create an automatic remediation action rule that uses an AWS Lambda function to remediate any change that makes the objects public.

B) Use AWS Trusted Advisor to find publicly accessible S3 buckets. Configure email notifications in Trusted Advisor when a change is detected. Manually change the S3 bucket policy if it allows public access.

C) Use AWS Resource Access Manager to find publicly accessible S3 buckets. Use Amazon Simple Notification Service (Amazon SNS) to invoke an AWS Lambda function when a change is detected. Deploy a Lambda function that programmatically remediates the change.

D) Use the S3 Block Public Access feature on the account level. Use AWS Organizations to create a service control policy (SCP) that prevents IAM users from changing the setting. Apply the SCP to the account.

---

### Question 413 - Email Processing for E-commerce Application
An ecommerce company is experiencing an increase in user traffic. The company's store is deployed on Amazon EC2 instances as a two-tier web application consisting of a web tier and a separate database tier. As traffic increases, the company notices that the architecture is causing significant delays in sending timely marketing and order confirmation emails to users. The company wants to reduce the time it spends resolving complex email delivery issues and minimize operational overhead.

**What should a solutions architect do to meet these requirements?**

A) Create a separate application tier using EC2 instances dedicated to email processing.

B) Configure the web instance to send email through Amazon Simple Email Service (Amazon SES).

C) Configure the web instance to send email through Amazon Simple Notification Service (Amazon SNS).

D) Create a separate application tier using EC2 instances dedicated to email processing. Place the instances in an Auto Scaling group.

---

### Question 414 - Automated File Transfer to S3
A company has a business system that generates hundreds of reports each day. The business system saves the reports to a network share in CSV format. The company needs to store this data in the AWS Cloud in near-real time for analysis.

**Which solution will meet these requirements with the LEAST administrative overhead?**

A) Use AWS DataSync to transfer the files to Amazon S3. Create a scheduled task that runs at the end of each day.

B) Create an Amazon S3 File Gateway. Update the business system to use a new network share from the S3 File Gateway.

C) Use AWS DataSync to transfer the files to Amazon S3. Create an application that uses the DataSync API in the automation workflow.

D) Deploy an AWS Transfer for SFTP endpoint. Create a script that checks for new files on the network share and uploads the new files by using SFTP.

---

### Question 415 - S3 Storage Cost Optimization
A company is storing petabytes of data in Amazon S3 Standard. The data is stored in multiple S3 buckets and is accessed with varying frequency. The company does not know access patterns for all the data. The company needs to implement a solution for each S3 bucket to optimize the cost of S3 usage.

**Which solution will meet these requirements with the MOST operational efficiency?**

A) Create an S3 Lifecycle configuration with a rule to transition the objects in the S3 bucket to S3 Intelligent-Tiering.

B) Use the S3 storage class analysis tool to determine the correct tier for each object in the S3 bucket. Move each object to the identified storage tier.

C) Create an S3 Lifecycle configuration with a rule to transition the objects in the S3 bucket to S3 Glacier Instant Retrieval.

D) Create an S3 Lifecycle configuration with a rule to transition the objects in the S3 bucket to S3 One Zone-Infrequent Access (S3 One Zone-IA).

---

### Question 416 - Global E-commerce Performance Optimization
A rapidly growing global ecommerce company is hosting its web application on AWS. The web application includes static content and dynamic content. The website stores online transaction processing (OLTP) data in an Amazon RDS database. The website's users are experiencing slow page loads.

**Which combination of actions should a solutions architect take to resolve this issue? (Choose two.)**

A) Configure an Amazon Redshift cluster.

B) Set up an Amazon CloudFront distribution.

C) Host the dynamic web content in Amazon S3.

D) Create a read replica for the RDS DB instance.

E) Configure a Multi-AZ deployment for the RDS DB instance.

---

### Question 417 - Cost Optimization for EC2 and Lambda
A company uses Amazon EC2 instances and AWS Lambda functions to run its application. The company has VPCs with public subnets and private subnets in its AWS account. The EC2 instances run in a private subnet in one of the VPCs. The Lambda functions need direct network access to the EC2 instances for the application to work. The application will run for at least 1 year. The company expects the number of Lambda functions that the application uses to increase during that time. The company wants to maximize its savings on all application resources and to keep network latency between the services low.

**Which solution will meet these requirements?**

A) Purchase an EC2 Instance Savings Plan. Optimize the Lambda functions' duration and memory usage and the number of invocations. Connect the Lambda functions to the private subnet that contains the EC2 instances.

B) Purchase an EC2 Instance Savings Plan. Optimize the Lambda functions' duration and memory usage, the number of invocations, and the amount of data that is transferred. Connect the Lambda functions to a public subnet in the same VPC where the EC2 instances run.

C) Purchase a Compute Savings Plan. Optimize the Lambda functions' duration and memory usage, the number of invocations, and the amount of data that is transferred. Connect the Lambda functions to the private subnet that contains the EC2 instances.

D) Purchase a Compute Savings Plan. Optimize the Lambda functions' duration and memory usage, the number of invocations, and the amount of data that is transferred. Keep the Lambda functions in the Lambda service VPC.

---

### Question 418 - Cross-Account S3 Access
A solutions architect needs to allow team members to access Amazon S3 buckets in two different AWS accounts: a development account and a production account. The team currently has access to S3 buckets in the development account by using unique IAM users that are assigned to an IAM group that has appropriate permissions in the account. The solutions architect has created an IAM role in the production account. The role has a policy that grants access to an S3 bucket in the production account.

**Which solution will meet these requirements while complying with the principle of least privilege?**

A) Attach the Administrator Access policy to the development account users.

B) Add the development account as a principal in the trust policy of the role in the production account.

C) Turn off the S3 Block Public Access feature on the S3 bucket in the production account.

D) Create a user in the production account with unique credentials for each team member.

---

### Question 419 - EBS Encryption Enforcement with Organizations
A company uses AWS Organizations with all features enabled and runs multiple Amazon EC2 workloads in the ap-southeast-2 Region. The company has a service control policy (SCP) that prevents any resources from being created in any other Region. A security policy requires the company to encrypt all data at rest. An audit discovers that employees have created Amazon Elastic Block Store (Amazon EBS) volumes for EC2 instances without encrypting the volumes. The company wants any new EC2 instances that any IAM user or root user launches in ap-southeast-2 to use encrypted EBS volumes. The company wants a solution that will have minimal effect on employees who create EBS volumes.

**Which combination of steps will meet these requirements? (Choose two.)**

A) In the Amazon EC2 console, select the EBS encryption account attribute and define a default encryption key.

B) Create an IAM permission boundary. Attach the permission boundary to the root organizational unit (OU). Define the boundary to deny the ec2:CreateVolume action when the ec2:Encrypted condition equals false.

C) Create an SCP. Attach the SCP to the root organizational unit (OU). Define the SCP to deny the ec2:CreateVolume action when the ec2:Encrypted condition equals false.

D) Update the IAM policies for each account to deny the ec2:CreateVolume action when the ec2:Encrypted condition equals false.

E) In the Organizations management account, specify the Default EBS volume encryption setting.

---

### Question 420 - RDS PostgreSQL High Availability
A company wants to use an Amazon RDS for PostgreSQL DB cluster to simplify time-consuming database administrative tasks for production database workloads. The company wants to ensure that its database is highly available and will provide automatic failover support in most scenarios in less than 40 seconds. The company wants to offload reads off of the primary instance and keep costs as low as possible.

**Which solution will meet these requirements?**

A) Use an Amazon RDS Multi-AZ DB instance deployment. Create one read replica and point the read workload to the read replica.

B) Use an Amazon RDS Multi-AZ DB cluster deployment. Create two read replicas and point the read workload to the read replicas.

C) Use an Amazon RDS Multi-AZ DB instance deployment. Point the read workload to the secondary instances in the Multi-AZ pair.

D) Use an Amazon RDS Multi-AZ DB cluster deployment. Point the read workload to the reader endpoint.

---

### Question 421 - Serverless SFTP Service
A company runs a highly available SFTP service. The SFTP service uses two Amazon EC2 Linux instances that run with elastic IP addresses to accept traffic from trusted IP sources on the internet. The SFTP service is backed by shared storage that is attached to the instances. User accounts are created and managed as Linux users in the SFTP servers. The company wants a serverless option that provides high IOPS performance and highly configurable security. The company also wants to maintain control over user permissions.

**Which solution will meet these requirements?**

A) Create an encrypted Amazon Elastic Block Store (Amazon EBS) volume. Create an AWS Transfer Family SFTP service with a public endpoint that allows only trusted IP addresses. Attach the EBS volume to the SFTP service endpoint. Grant users access to the SFTP service.

B) Create an encrypted Amazon Elastic File System (Amazon EFS) volume. Create an AWS Transfer Family SFTP service with elastic IP addresses and a VPC endpoint that has internet-facing access. Attach a security group to the endpoint that allows only trusted IP addresses. Attach the EFS volume to the SFTP service endpoint. Grant users access to the SFTP service.

C) Create an Amazon S3 bucket with default encryption enabled. Create an AWS Transfer Family SFTP service with a public endpoint that allows only trusted IP addresses. Attach the S3 bucket to the SFTP service endpoint. Grant users access to the SFTP service.

D) Create an Amazon S3 bucket with default encryption enabled. Create an AWS Transfer Family SFTP service with a VPC endpoint that has internal access in a private subnet. Attach a security group that allows only trusted IP addresses. Attach the S3 bucket to the SFTP service endpoint. Grant users access to the SFTP service.

---

## Answer Key

| Question | Answer | Key Concept |
|----------|--------|-------------|
| 391 | C | AMI retention for stateless instances, RDS automated backups |
| 392 | A | Security group best practices |
| 393 | C | Amazon Transcribe with PII redaction |
| 394 | B | GP3 IOPS scaling |
| 395 | C | AWS CloudTrail for API tracking |
| 396 | A | AWS Shield Advanced for Global Accelerator |
| 397 | C | ECS Fargate for scheduled tasks |
| 398 | C | AWS Snow Family for large data transfers |
| 399 | B | AWS WAF for API protection |
| 400 | C | DynamoDB Streams with SNS |
| 401 | A | Multi-AZ deployment for high availability |
| 402 | A | Kinesis data retention period |
| 403 | D | IAM execution role for Lambda |
| 404 | D | SQS for decoupling and reliability |
| 405 | D, E | Target tracking and scheduled scaling |
| 406 | C, D | Security group configuration |
| 407 | D | Amazon FSx for Lustre |
| 408 | B | Global Accelerator with NLB for UDP |
| 409 | C | Amazon FSx for Windows File Server |
| 410 | B | EBS encryption at creation |
| 411 | C | Aurora Serverless for variable workloads |
| 412 | D | S3 Block Public Access with SCP |
| 413 | B | Amazon SES for email delivery |
| 414 | B | S3 File Gateway for seamless integration |
| 415 | A | S3 Intelligent-Tiering |
| 416 | B, D | CloudFront and RDS read replicas |
| 417 | C | Compute Savings Plan for Lambda and EC2 |
| 418 | B | Cross-account IAM role trust policy |
| 419 | A, C | EBS encryption account setting and SCP |
| 420 | D | RDS Multi-AZ cluster with reader endpoint |
| 421 | C | AWS Transfer Family with S3 |

---

## Explanations

### Question 391 Explanation
**Answer: C** - For a stateless three-tier application, AMIs are sufficient for the web/application tiers since no persistent data is stored locally. RDS automated backups with point-in-time recovery provide the required 2-hour RPO for the database tier.

### Question 392 Explanation
**Answer: A** - Web servers need to accept HTTPS traffic from anywhere (0.0.0.0/0) since customers have dynamic IPs. The database should only accept connections from the web servers' security group, following the principle of least privilege.

### Question 393 Explanation
**Answer: C** - Amazon Transcribe is the appropriate service for audio-to-text conversion and has built-in PII redaction capabilities. This is more suitable than Textract (for documents) or manually scanning for PII patterns.

### Question 394 Explanation
**Answer: B** - GP3 volumes allow independent scaling of IOPS up to 16,000 IOPS, making it the most cost-effective solution. IO2 would be more expensive and unnecessary for this use case.

### Question 395 Explanation
**Answer: C** - AWS CloudTrail logs all API calls including who made changes to security groups. This is the appropriate service for auditing AWS API activity.

### Question 396 Explanation
**Answer: A** - AWS Shield Advanced provides DDoS protection for Global Accelerator endpoints. WAF cannot be directly associated with Global Accelerator standard endpoints.

### Question 397 Explanation
**Answer: C** - ECS Fargate is ideal for scheduled tasks that run for extended periods (up to 1 hour). Lambda has a 15-minute timeout limit, making it unsuitable for this use case.

### Question 398 Explanation
**Answer: C** - With 100 Mbps internet, transferring 600 TB would take approximately 13 months. Snow Family devices can transfer this amount within the 2-week requirement and are encrypted in transit.

### Question 399 Explanation
**Answer: B** - AWS WAF with rate-based rules provides the most direct protection against HTTP flood attacks with minimal operational overhead compared to custom Lambda solutions.

### Question 400 Explanation
**Answer: C** - DynamoDB Streams automatically capture data changes without affecting application performance. A single SNS topic with multiple subscribers is more efficient than multiple topics.

---

## Study Tips

1. **Focus on Key AWS Services**: Understand the core services and their use cases:
   - EC2, RDS, S3, Lambda, ECS
   - Auto Scaling, Load Balancers
   - VPC, Security Groups, NACLs
   - CloudTrail, CloudWatch, WAF

2. **Architectural Patterns**: Study common patterns like:
   - Multi-tier applications
   - High availability and disaster recovery
   - Serverless architectures
   - Microservices with containers

3. **Cost Optimization**: Understand:
   - Savings Plans vs Reserved Instances
   - Storage classes and lifecycle policies
   - Right-sizing recommendations

4. **Security Best Practices**: Know:
   - Principle of least privilege
   - Encryption at rest and in transit
   - Identity and access management

5. **Performance Optimization**: Understand:
   - Caching strategies (CloudFront, ElastiCache)
   - Database scaling (read replicas, sharding)
   - Network optimization

---

## Additional Resources

- [AWS Architecture Center](https://aws.amazon.com/architecture/)
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS Solutions Architect Associate Exam Guide](https://aws.amazon.com/certification/certified-solutions-architect-associate/)

---

## Contributing

Feel free to contribute additional practice questions or improvements to existing questions by submitting a pull request. Please ensure that:

1. Questions follow the AWS exam format
2. Answers are well-researched and accurate
3. Explanations are clear and educational
4. Content covers diverse AWS services and scenarios

---

## License

This content is provided for educational purposes. Please refer to AWS documentation for the most current and accurate information about AWS services.