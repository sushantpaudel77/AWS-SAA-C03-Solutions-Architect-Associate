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

### Question 422 - Machine Learning Model Microservices
A company is developing a new machine learning (ML) model solution on AWS. The models are developed as independent microservices that fetch approximately 1 GB of model data from Amazon S3 at startup and load the data into memory. Users access the models through an asynchronous API. Users can send a request or a batch of requests and specify where the results should be sent. The company provides models to hundreds of users. The usage patterns for the models are irregular. Some models could be unused for days or weeks. Other models could receive batches of thousands of requests at a time.

**Which design should a solutions architect recommend to meet these requirements?**

A) Direct the requests from the API to a Network Load Balancer (NLB). Deploy the models as AWS Lambda functions that are invoked by the NLB.

B) Direct the requests from the API to an Application Load Balancer (ALB). Deploy the models as Amazon Elastic Container Service (Amazon ECS) services that read from an Amazon Simple Queue Service (Amazon SQS) queue. Use AWS App Mesh to scale the instances of the ECS cluster based on the SQS queue size.

C) Direct the requests from the API into an Amazon Simple Queue Service (Amazon SQS) queue. Deploy the models as AWS Lambda functions that are invoked by SQS events. Use AWS Auto Scaling to increase the number of vCPUs for the Lambda functions based on the SQS queue size.

D) Direct the requests from the API into an Amazon Simple Queue Service (Amazon SQS) queue. Deploy the models as Amazon Elastic Container Service (Amazon ECS) services that read from the queue. Enable AWS Auto Scaling on Amazon ECS for both the cluster and copies of the service based on the queue size.

---

### Question 423 - IAM Identity-Based Policy Attachment
A solutions architect wants to use the following JSON text as an identity-based policy to grant specific permissions:

**Which IAM principals can the solutions architect attach this policy to? (Choose two.)**

A) Role

B) Group

C) Organization

D) Amazon Elastic Container Service (Amazon ECS) resource

E) Amazon EC2 resource

---

### Question 424 - Cost-Effective EC2 Instance Strategy
A company is running a custom application on Amazon EC2 On-Demand Instances. The application has frontend nodes that need to run 24 hours a day, 7 days a week and backend nodes that need to run only for a short time based on workload. The number of backend nodes varies during the day. The company needs to scale out and scale in more instances based on workload.

**Which solution will meet these requirements MOST cost-effectively?**

A) Use Reserved Instances for the frontend nodes. Use AWS Fargate for the backend nodes.

B) Use Reserved Instances for the frontend nodes. Use Spot Instances for the backend nodes.

C) Use Spot Instances for the frontend nodes. Use Reserved Instances for the backend nodes.

D) Use Spot Instances for the frontend nodes. Use AWS Fargate for the backend nodes.

---

### Question 425 - EBS Volume Type Selection
A company uses high block storage capacity to runs its workloads on premises. The company's daily peak input and output transactions per second are not more than 15,000 IOPS. The company wants to migrate the workloads to Amazon EC2 and to provision disk performance independent of storage capacity.

**Which Amazon Elastic Block Store (Amazon EBS) volume type will meet these requirements MOST cost-effectively?**

A) GP2 volume type

B) io2 volume type

C) GP3 volume type

D) io1 volume type

---

### Question 426 - Healthcare Data Migration with Audit Requirements
A company needs to store data from its healthcare application. The application's data frequently changes. A new regulation requires audit access at all levels of the stored data. The company hosts the application on an on-premises infrastructure that is running out of storage capacity. A solutions architect must securely migrate the existing data to AWS while satisfying the new regulation.

**Which solution will meet these requirements?**

A) Use AWS DataSync to move the existing data to Amazon S3. Use AWS CloudTrail to log data events.

B) Use AWS Snowcone to move the existing data to Amazon S3. Use AWS CloudTrail to log management events.

C) Use Amazon S3 Transfer Acceleration to move the existing data to Amazon S3. Use AWS CloudTrail to log data events.

D) Use AWS Storage Gateway to move the existing data to Amazon S3. Use AWS CloudTrail to log management events.

---

### Question 427 - Highly Available Java Application Deployment
A solutions architect is implementing a complex Java application with a MySQL database. The Java application must be deployed on Apache Tomcat and must be highly available.

**What should the solutions architect do to meet these requirements?**

A) Deploy the application in AWS Lambda. Configure an Amazon API Gateway API to connect with the Lambda functions.

B) Deploy the application by using AWS Elastic Beanstalk. Configure a load-balanced environment and a rolling deployment policy.

C) Migrate the database to Amazon ElastiCache. Configure the ElastiCache security group to allow access from the application.

D) Launch an Amazon EC2 instance. Install a MySQL server on the EC2 instance. Configure the application on the server. Create an AMI. Use the AMI to create a launch template with an Auto Scaling group.

---

### Question 428 - Lambda Function DynamoDB Access
A serverless application uses Amazon API Gateway, AWS Lambda, and Amazon DynamoDB. The Lambda function needs permissions to read and write to the DynamoDB table.

**Which solution will give the Lambda function access to the DynamoDB table MOST securely?**

A) Create an IAM user with programmatic access to the Lambda function. Attach a policy to the user that allows read and write access to the DynamoDB table. Store the access_key_id and secret_access_key parameters as part of the Lambda environment variables. Ensure that other AWS users do not have read and write access to the Lambda function configuration.

B) Create an IAM role that includes Lambda as a trusted service. Attach a policy to the role that allows read and write access to the DynamoDB table. Update the configuration of the Lambda function to use the new role as the execution role.

C) Create an IAM user with programmatic access to the Lambda function. Attach a policy to the user that allows read and write access to the DynamoDB table. Store the access_key_id and secret_access_key parameters in AWS Systems Manager Parameter Store as secure string parameters. Update the Lambda function code to retrieve the secure string parameters before connecting to the DynamoDB table.

D) Create an IAM role that includes DynamoDB as a trusted service. Attach a policy to the role that allows read and write access from the Lambda function. Update the code of the Lambda function to attach to the new role as an execution role.

---

### Question 429 - IAM Policy Effective Permissions
The following IAM policy is attached to an IAM group. This is the only policy applied to the group.

**What are the effective IAM permissions of this policy for group members?**

A) Group members are permitted any Amazon EC2 action within the us-east-1 Region. Statements after the Allow permission are not applied.

B) Group members are denied any Amazon EC2 permissions in the us-east-1 Region unless they are logged in with multi-factor authentication (MFA).

C) Group members are allowed the ec2:StopInstances and ec2:TerminateInstances permissions for all Regions when logged in with multi-factor authentication (MFA). Group members are permitted any other Amazon EC2 action.

D) Group members are allowed the ec2:StopInstances and ec2:TerminateInstances permissions for the us-east-1 Region only when logged in with multi-factor authentication (MFA). Group members are permitted any other Amazon EC2 action within the us-east-1 Region.

---

### Question 430 - CSV to Image Processing Pipeline
A manufacturing company has machine sensors that upload .csv files to an Amazon S3 bucket. These .csv files must be converted into images and must be made available as soon as possible for the automatic generation of graphical reports. The images become irrelevant after 1 month, but the .csv files must be kept to train machine learning (ML) models twice a year. The ML trainings and audits are planned weeks in advance.

**Which combination of steps will meet these requirements MOST cost-effectively? (Choose two.)**

A) Launch an Amazon EC2 Spot Instance that downloads the .csv files every hour, generates the image files, and uploads the images to the S3 bucket.

B) Design an AWS Lambda function that converts the .csv files into images and stores the images in the S3 bucket. Invoke the Lambda function when a .csv file is uploaded.

C) Create S3 Lifecycle rules for .csv files and image files in the S3 bucket. Transition the .csv files from S3 Standard to S3 Glacier 1 day after they are uploaded. Expire the image files after 30 days.

D) Create S3 Lifecycle rules for .csv files and image files in the S3 bucket. Transition the .csv files from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) 1 day after they are uploaded. Expire the image files after 30 days.

E) Create S3 Lifecycle rules for .csv files and image files in the S3 bucket. Transition the .csv files from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 1 day after they are uploaded. Keep the image files in Reduced Redundancy Storage (RRS).

---

### Question 431 - Gaming Application Scoreboard
A company has developed a new video game as a web application. The application is in a three-tier architecture in a VPC with Amazon RDS for MySQL in the database layer. Several players will compete concurrently online. The game's developers want to display a top-10 scoreboard in near-real time and offer the ability to stop and restore the game while preserving the current scores.

**What should a solutions architect do to meet these requirements?**

A) Set up an Amazon ElastiCache for Memcached cluster to cache the scores for the web application to display.

B) Set up an Amazon ElastiCache for Redis cluster to compute and cache the scores for the web application to display.

C) Place an Amazon CloudFront distribution in front of the web application to cache the scoreboard in a section of the application.

D) Create a read replica on Amazon RDS for MySQL to run queries to compute the scoreboard and serve the read traffic to the web application.

---

### Question 432 - Machine Learning and Business Intelligence Integration
An ecommerce company wants to use machine learning (ML) algorithms to build and train models. The company will use the models to visualize complex scenarios and to detect trends in customer data. The architecture team wants to integrate its ML models with a reporting platform to analyze the augmented data and use the data directly in its business intelligence dashboards.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Use AWS Glue to create an ML transform to build and train models. Use Amazon OpenSearch Service to visualize the data.

B) Use Amazon SageMaker to build and train models. Use Amazon QuickSight to visualize the data.

C) Use a pre-built ML Amazon Machine Image (AMI) from the AWS Marketplace to build and train models. Use Amazon OpenSearch Service to visualize the data.

D) Use Amazon QuickSight to build and train models by using calculated fields. Use Amazon QuickSight to visualize the data.

---

### Question 433 - Cost Usage Tags Protection
A company is running its production and nonproduction environment workloads in multiple AWS accounts. The accounts are in an organization in AWS Organizations. The company needs to design a solution that will prevent the modification of cost usage tags.

**Which solution will meet these requirements?**

A) Create a custom AWS Config rule to prevent tag modification except by authorized principals.

B) Create a custom trail in AWS CloudTrail to prevent tag modification.

C) Create a service control policy (SCP) to prevent tag modification except by authorized principals.

D) Create custom Amazon CloudWatch logs to prevent tag modification.

---

### Question 434 - Multi-Region Application Availability
A company hosts its application in the AWS Cloud. The application runs on Amazon EC2 instances behind an Elastic Load Balancer in an Auto Scaling group and with an Amazon DynamoDB table. The company wants to ensure the application can be made available in another AWS Region with minimal downtime.

**What should a solutions architect do to meet these requirements with the LEAST amount of downtime?**

A) Create an Auto Scaling group and a load balancer in the disaster recovery Region. Configure the DynamoDB table as a global table. Configure DNS failover to point to the new disaster recovery Region's load balancer.

B) Create an AWS CloudFormation template to create EC2 instances, load balancers, and DynamoDB tables to be launched when needed. Configure DNS failover to point to the new disaster recovery Region's load balancer.

C) Create an AWS CloudFormation template to create EC2 instances and a load balancer to be launched when needed. Configure the DynamoDB table as a global table. Configure DNS failover to point to the new disaster recovery Region's load balancer.

D) Create an Auto Scaling group and load balancer in the disaster recovery Region. Configure the DynamoDB table as a global table. Create an Amazon CloudWatch alarm to trigger an AWS Lambda function that updates Amazon Route 53 pointing to the disaster recovery load balancer.

---

### Question 435 - MySQL Database Migration
A company needs to migrate a MySQL database from its on-premises data center to AWS within 2 weeks. The database is 20 TB in size. The company wants to complete the migration with minimal downtime.

**Which solution will migrate the database MOST cost-effectively?**

A) Order an AWS Snowball Edge Storage Optimized device. Use AWS Database Migration Service (AWS DMS) with AWS Schema Conversion Tool (AWS SCT) to migrate the database with replication of ongoing changes. Send the Snowball Edge device to AWS to finish the migration and continue the ongoing replication.

B) Order an AWS Snowmobile vehicle. Use AWS Database Migration Service (AWS DMS) with AWS Schema Conversion Tool (AWS SCT) to migrate the database with ongoing changes. Send the Snowmobile vehicle back to AWS to finish the migration and continue the ongoing replication.

C) Order an AWS Snowball Edge Compute Optimized with GPU device. Use AWS Database Migration Service (AWS DMS) with AWS Schema Conversion Tool (AWS SCT) to migrate the database with ongoing changes. Send the Snowball device to AWS to finish the migration and continue the ongoing replication.

D) Order a 1 GB dedicated AWS Direct Connect connection to establish a connection with the data center. Use AWS Database Migration Service (AWS DMS) with AWS Schema Conversion Tool (AWS SCT) to migrate the database with replication of ongoing changes.

---

### Question 436 - RDS PostgreSQL Workload Scaling
A company moved its on-premises PostgreSQL database to an Amazon RDS for PostgreSQL DB instance. The company successfully launched a new product. The workload on the database has increased. The company wants to accommodate the larger workload without adding infrastructure.

**Which solution will meet these requirements MOST cost-effectively?**

A) Buy reserved DB instances for the total workload. Make the Amazon RDS for PostgreSQL DB instance larger.

B) Make the Amazon RDS for PostgreSQL DB instance a Multi-AZ DB instance.

C) Buy reserved DB instances for the total workload. Add another Amazon RDS for PostgreSQL DB instance.

D) Make the Amazon RDS for PostgreSQL DB instance an on-demand DB instance.

---

### Question 437 - E-commerce DDoS Protection
A company operates an ecommerce website on Amazon EC2 instances behind an Application Load Balancer (ALB) in an Auto Scaling group. The site is experiencing performance issues related to a high request rate from illegitimate external systems with changing IP addresses. The security team is worried about potential DDoS attacks against the website. The company must block the illegitimate incoming requests in a way that has a minimal impact on legitimate users.

**What should a solutions architect recommend?**

A) Deploy Amazon Inspector and associate it with the ALB.

B) Deploy AWS WAF, associate it with the ALB, and configure a rate-limiting rule.

C) Deploy rules to the network ACLs associated with the ALB to block the incoming traffic.

D) Deploy Amazon GuardDuty and enable rate-limiting protection when configuring GuardDuty.

---

### Question 438 - Secure Database Sharing with External Auditor
A company wants to share accounting data with an external auditor. The data is stored in an Amazon RDS DB instance that resides in a private subnet. The auditor has its own AWS account and requires its own copy of the database.

**What is the MOST secure way for the company to share the database with the auditor?**

A) Create a read replica of the database. Configure IAM standard database authentication to grant the auditor access.

B) Export the database contents to text files. Store the files in an Amazon S3 bucket. Create a new IAM user for the auditor. Grant the user access to the S3 bucket.

C) Copy a snapshot of the database to an Amazon S3 bucket. Create an IAM user. Share the user's keys with the auditor to grant access to the object in the S3 bucket.

D) Create an encrypted snapshot of the database. Share the snapshot with the auditor. Allow access to the AWS Key Management Service (AWS KMS) encryption key.

---

### Question 439 - VPC IP Address Range Expansion
A solutions architect configured a VPC that has a small range of IP addresses. The number of Amazon EC2 instances that are in the VPC is increasing, and there is an insufficient number of IP addresses for future workloads.

**Which solution resolves this issue with the LEAST operational overhead?**

A) Add an additional IPv4 CIDR block to increase the number of IP addresses and create additional subnets in the VPC. Create new resources in the new subnets by using the new CIDR.

B) Create a second VPC with additional subnets. Use a peering connection to connect the second VPC with the first VPC. Update the routes and create new resources in the subnets of the second VPC.

C) Use AWS Transit Gateway to add a transit gateway and connect a second VPC with the first VPC. Update the routes of the transit gateway and VPCs. Create new resources in the subnets of the second VPC.

D) Create a second VPC. Create a Site-to-Site VPN connection between the first VPC and the second VPC by using a VPN-hosted solution on Amazon EC2 and a virtual private gateway. Update the route between VPCs to the traffic through the VPN. Create new resources in the subnets of the second VPC.

---

### Question 440 - Database Migration from RDS to Aurora
A company used an Amazon RDS for MySQL DB instance during application testing. Before terminating the DB instance at the end of the test cycle, a solutions architect created two backups. The solutions architect created the first backup by using the mysqldump utility to create a database dump. The solutions architect created the second backup by enabling the final DB snapshot option on RDS termination. The company is now planning for a new test cycle and wants to create a new DB instance from the most recent backup. The company has chosen a MySQL-compatible edition of Amazon Aurora to host the DB instance.

**Which solutions will create the new DB instance? (Choose two.)**

A) Import the RDS snapshot directly into Aurora.

B) Upload the RDS snapshot to Amazon S3. Then import the RDS snapshot into Aurora.

C) Upload the database dump to Amazon S3. Then import the database dump into Aurora.

D) Use AWS Database Migration Service (AWS DMS) to import the RDS snapshot into Aurora.

E) Upload the database dump to Amazon S3. Then use AWS Database Migration Service (AWS DMS) to import the database dump into Aurora.

---

### Question 441 - Static Content Cost Optimization
A company hosts a multi-tier web application on Amazon Linux Amazon EC2 instances behind an Application Load Balancer. The instances run in an Auto Scaling group across multiple Availability Zones. The company observes that the Auto Scaling group launches more On-Demand Instances when the application's end users access high volumes of static web content. The company wants to optimize cost.

**What should a solutions architect do to redesign the application MOST cost-effectively?**

A) Update the Auto Scaling group to use Reserved Instances instead of On-Demand Instances.

B) Update the Auto Scaling group to scale by launching Spot Instances instead of On-Demand Instances.

C) Create an Amazon CloudFront distribution to host the static web contents from an Amazon S3 bucket.

D) Create an AWS Lambda function behind an Amazon API Gateway API to host the static website contents.

---

### Question 442 - Cross-Account Data Lake Sharing
A company stores several petabytes of data across multiple AWS accounts. The company uses AWS Lake Formation to manage its data lake. The company's data science team wants to securely share selective data from its accounts with the company's engineering team for analytical purposes.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Copy the required data to a common account. Create an IAM access role in that account. Grant access by specifying a permission policy that includes users from the engineering team accounts as trusted entities.

B) Use the Lake Formation permissions Grant command in each account where the data is stored to allow the required engineering team users to access the data.

C) Use AWS Data Exchange to privately publish the required data to the required engineering team accounts.

D) Use Lake Formation tag-based access control to authorize and grant cross-account permissions for the required data to the engineering team accounts.

---

### Question 443 - Global Scalable Web Application
A company wants to host a scalable web application on AWS. The application will be accessed by users from different geographic regions of the world. Application users will be able to download and upload unique data up to gigabytes in size. The development team wants a cost-effective solution to minimize upload and download latency and maximize performance.

**What should a solutions architect do to accomplish this?**

A) Use Amazon S3 with Transfer Acceleration to host the application.

B) Use Amazon S3 with CacheControl headers to host the application.

C) Use Amazon EC2 with Auto Scaling and Amazon CloudFront to host the application.

D) Use Amazon EC2 with Auto Scaling and Amazon ElastiCache to host the application.

---

### Question 444 - Application Reliability Improvement
A company has hired a solutions architect to design a reliable architecture for its application. The application consists of one Amazon RDS DB instance and two manually provisioned Amazon EC2 instances that run web servers. The EC2 instances are located in a single Availability Zone. An employee recently deleted the DB instance, and the application was unavailable for 24 hours as a result. The company is concerned with the overall reliability of its environment.

**What should the solutions architect do to maximize reliability of the application's infrastructure?**

A) Delete one EC2 instance and enable termination protection on the other EC2 instance. Update the DB instance to be Multi-AZ, and enable deletion protection.

B) Update the DB instance to be Multi-AZ, and enable deletion protection. Place the EC2 instances behind an Application Load Balancer, and run them in an EC2 Auto Scaling group across multiple Availability Zones.

C) Create an additional DB instance along with an Amazon API Gateway and an AWS Lambda function. Configure the application to invoke the Lambda function through API Gateway. Have the Lambda function write the data to the two DB instances.

D) Place the EC2 instances in an EC2 Auto Scaling group that has multiple subnets located in multiple Availability Zones. Use Spot Instances instead of On-Demand Instances. Set up Amazon CloudWatch alarms to monitor the health of the instances. Update the DB instance to be Multi-AZ, and enable deletion protection.

---

### Question 445 - Large Data Transfer with Direct Connect
A company is storing 700 terabytes of data on a large network-attached storage (NAS) system in its corporate data center. The company has a hybrid environment with a 10 Gbps AWS Direct Connect connection. After an audit from a regulator, the company has 90 days to move the data to the cloud. The company needs to move the data efficiently and without disruption. The company still needs to be able to access and update the data during the transfer window.

**Which solution will meet these requirements?**

A) Create an AWS DataSync agent in the corporate data center. Create a data transfer task. Start the transfer to an Amazon S3 bucket.

B) Back up the data to AWS Snowball Edge Storage Optimized devices. Ship the devices to an AWS data center. Mount a target Amazon S3 bucket on the on-premises file system.

C) Use rsync to copy the data directly from local storage to a designated Amazon S3 bucket over the Direct Connect connection.

D) Back up the data on tapes. Ship the tapes to an AWS data center. Mount a target Amazon S3 bucket on the on-premises file system.

---

### Question 446 - S3 Legal Retention Requirements
A company stores data in PDF format in an Amazon S3 bucket. The company must follow a legal requirement to retain all new and existing data in Amazon S3 for 7 years.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Turn on the S3 Versioning feature for the S3 bucket. Configure S3 Lifecycle to delete the data after 7 years. Configure multi-factor authentication (MFA) delete for all S3 objects.

B) Turn on S3 Object Lock with governance retention mode for the S3 bucket. Set the retention period to expire after 7 years. Recopy all existing objects to bring the existing data into compliance.

C) Turn on S3 Object Lock with compliance retention mode for the S3 bucket. Set the retention period to expire after 7 years. Recopy all existing objects to bring the existing data into compliance.

D) Turn on S3 Object Lock with compliance retention mode for the S3 bucket. Set the retention period to expire after 7 years. Use S3 Batch Operations to bring the existing data into compliance.

---

### Question 447 - Multi-Region Lambda Application Deployment
A company has a stateless web application that runs on AWS Lambda functions that are invoked by Amazon API Gateway. The company wants to deploy the application across multiple AWS Regions to provide Regional failover capabilities.

**What should a solutions architect do to route traffic to multiple Regions?**

A) Create Amazon Route 53 health checks for each Region. Use an active-active failover configuration.

B) Create an Amazon CloudFront distribution with an origin for each Region. Use CloudFront health checks to route traffic.

C) Create a transit gateway. Attach the transit gateway to the API Gateway endpoint in each Region. Configure the transit gateway to route requests.

D) Create an Application Load Balancer in the primary Region. Set the target group to point to the API Gateway endpoint hostnames in each Region.

---

### Question 448 - Single Point of Failure Mitigation
A company has two VPCs named Management and Production. The Management VPC uses VPNs through a customer gateway to connect to a single device in the data center. The Production VPC uses a virtual private gateway with two attached AWS Direct Connect connections. The Management and Production VPCs both use a single VPC peering connection to allow communication between the applications.

**What should a solutions architect do to mitigate any single point of failure in this architecture?**

A) Add a set of VPNs between the Management and Production VPCs.

B) Add a second virtual private gateway and attach it to the Management VPC.

C) Add a second set of VPNs to the Management VPC from a second customer gateway device.

D) Add a second VPC peering connection between the Management VPC and the Production VPC.

---

### Question 449 - Oracle Database Migration Strategy
A company runs its application on an Oracle database. The company plans to quickly migrate to AWS because of limited resources for the database, backup administration, and data center maintenance. The application uses third-party database features that require privileged access.

**Which solution will help the company migrate the database to AWS MOST cost-effectively?**

A) Migrate the database to Amazon RDS for Oracle. Replace third-party features with cloud services.

B) Migrate the database to Amazon RDS Custom for Oracle. Customize the database settings to support third-party features.

C) Migrate the database to an Amazon EC2 Amazon Machine Image (AMI) for Oracle. Customize the database settings to support third-party features.

D) Migrate the database to Amazon RDS for PostgreSQL by rewriting the application code to remove dependency on Oracle APEX.

---

### Question 450 - Three-Tier Web Application Migration
A company has a three-tier web application that is in a single server. The company wants to migrate the application to the AWS Cloud. The company also wants the application to align with the AWS Well-Architected Framework and to be consistent with AWS recommended best practices for security, scalability, and resiliency.

**Which combination of solutions will meet these requirements? (Choose three.)**

A) Create a VPC across two Availability Zones with the application's existing architecture. Host the application with existing architecture on an Amazon EC2 instance in a private subnet in each Availability Zone with EC2 Auto Scaling groups. Secure the EC2 instance with security groups and network access control lists (network ACLs).

B) Set up security groups and network access control lists (network ACLs) to control access to the database layer. Set up a single Amazon RDS database in a private subnet.

C) Create a VPC across two Availability Zones. Refactor the application to host the web tier, application tier, and database tier. Host each tier on its own private subnet with Auto Scaling groups for the web tier and application tier.

D) Use a single Amazon RDS database. Allow database access only from the application tier security group.

E) Use Elastic Load Balancers in front of the web tier. Control access by using security groups containing references to each layer's security groups.

F) Use an Amazon RDS database Multi-AZ cluster deployment in private subnets. Allow database access only from application tier security groups.

---

### Question 451 - AWS Shared Responsibility Model
A company is migrating its applications and databases to the AWS Cloud. The company will use Amazon Elastic Container Service (Amazon ECS), AWS Direct Connect, and Amazon RDS.

**Which activities will be managed by the company's operational team? (Choose three.)**

A) Management of the Amazon RDS infrastructure layer, operating system, and platforms

B) Creation of an Amazon RDS DB instance and configuring the scheduled maintenance window

C) Configuration of additional software components on Amazon ECS for monitoring, patch management, log management, and host intrusion detection

D) Installation of patches for all minor and major database versions for Amazon RDS

E) Ensure the physical security of the Amazon RDS infrastructure in the data center

F) Encryption of the data that moves in transit through Direct Connect

---

Question 452 - Java Job Cost Optimization
A company runs a Java-based job on an Amazon EC2 instance. The job runs every hour and takes 10 seconds to run. The job runs on a scheduled interval and consumes 1 GB of memory. The CPU utilization of the instance is low except for short surges during which the job uses the maximum CPU available. The company wants to optimize the costs to run the job.

Which solution will meet these requirements?

A) Use AWS App2Container (A2C) to containerize the job. Run the job as an Amazon Elastic Container Service (Amazon ECS) task on AWS Fargate with 0.5 virtual CPU (vCPU) and 1 GB of memory.

B) Copy the code into an AWS Lambda function that has 1 GB of memory. Create an Amazon EventBridge scheduled rule to run the code each hour.

C) Use AWS App2Container (A2C) to containerize the job. Install the container in the existing Amazon Machine Image (AMI). Ensure that the schedule stops the container when the task finishes.

D) Configure the existing schedule to stop the EC2 instance at the completion of the job and restart the EC2 instance when the next job starts.


Question 453 - Backup Strategy with Immutable Files
A company wants to implement a backup strategy for Amazon EC2 data and multiple Amazon S3 buckets. Because of regulatory requirements, the company must retain backup files for a specific time period. The company must not alter the files for the duration of the retention period.

Which solution will meet these requirements?

A) Use AWS Backup to create a backup vault that has a vault lock in governance mode. Create the required backup plan.

B) Use Amazon Data Lifecycle Manager to create the required automated snapshot policy.

C) Use Amazon S3 File Gateway to create the backup. Configure the appropriate S3 Lifecycle management.

D) Use AWS Backup to create a backup vault that has a vault lock in compliance mode. Create the required backup plan.


Question 454 - Workload Discovery and Mapping
A company has resources across multiple AWS Regions and accounts. A newly hired solutions architect discovers a previous employee did not provide details about the resources inventory. The solutions architect needs to build and map the relationship details of the various workloads across all accounts.

Which solution will meet these requirements in the MOST operationally efficient way?

A) Use AWS Systems Manager Inventory to generate a map view from the detailed view report.

B) Use AWS Step Functions to collect workload details. Build architecture diagrams of the workloads manually.

C) Use Workload Discovery on AWS to generate architecture diagrams of the workloads.

D) Use AWS X-Ray to view the workload details. Build architecture diagrams with relationships.

Question 455 - Budget Controls with Organizations
A company uses AWS Organizations. The company wants to operate some of its AWS accounts with different budgets. The company wants to receive alerts and automatically prevent provisioning of additional resources on AWS accounts when the allocated budget threshold is met during a specific period.

Which combination of solutions will meet these requirements? (Choose three.)

A) Use AWS Budgets to create a budget. Set the budget amount under the Cost and Usage Reports section of the required AWS accounts.

B) Use AWS Budgets to create a budget. Set the budget amount under the Billing dashboards of the required AWS accounts.

C) Create an IAM user for AWS Budgets to run budget actions with the required permissions.

D) Create an IAM role for AWS Budgets to run budget actions with the required permissions.

E) Add an alert to notify the company when each account meets its budget threshold. Add a budget action that selects the IAM identity created with the appropriate config rule to prevent provisioning of additional resources.

F) Add an alert to notify the company when each account meets its budget threshold. Add a budget action that selects the IAM identity created with the appropriate service control policy (SCP) to prevent provisioning of additional resources.


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
| 422 | D | ECS with SQS for microservices |
| 423 | A, B | IAM identity-based policies |
| 424 | B | Reserved + Spot Instance strategy |
| 425 | C | GP3 for cost-effective IOPS |
| 426 | A | DataSync with CloudTrail data events |
| 427 | B | Elastic Beanstalk for Java applications |
| 428 | B | IAM execution role for Lambda |
| 429 | D | Conditional IAM permissions |
| 430 | B, C | Lambda processing with S3 lifecycle |
| 431 | B | ElastiCache Redis for gaming scoreboards |
| 432 | B | SageMaker with QuickSight |
| 433 | C | Service Control Policy for tag protection |
| 434 | A | DynamoDB Global Tables for DR |
| 435 | A | Snowball Edge for database migration |
| 436 | A | Vertical scaling with Reserved Instances |
| 437 | B | AWS WAF for DDoS protection |
| 438 | D | Encrypted snapshot sharing |
| 439 | A | Additional CIDR blocks |
| 440 | A, C | RDS to Aurora migration options |
| 441 | C | CloudFront for static content |
| 442 | D | Lake Formation cross-account access |
| 443 | A | S3 Transfer Acceleration |
| 444 | B | Multi-AZ with Auto Scaling |
| 445 | A | DataSync for large data migration |
| 446 | D | S3 Object Lock compliance mode |
| 447 | A | Route 53 health checks |
| 448 | C | Redundant VPN connections |
| 449 | B | RDS Custom for Oracle |
| 450 | C, E, F | Well-Architected three-tier design |
| 451 | B, C, F | Customer responsibilities in shared model |
| 452 | B | Lambda for short-duration scheduled jobs |
| 453 | D | AWS Backup vault lock compliance mode |
| 454 | C | Workload Discovery on AWS |
| 455 | B, D, F | AWS Budgets with automated actions |

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