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

