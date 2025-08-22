# AWS Solutions Architect Associate (SAA) Practice Questions

This repository contains a comprehensive collection of AWS Solutions Architect Associate certification practice questions covering various AWS services and architectural patterns.

## Table of Contents
- [Overview](#overview)
- [Question Categories](#question-categories)
- [How to Use](#how-to-use)
- [Questions](#questions)
- [Answer Key](#answer-key)

## Overview
This collection includes 65 practice questions (Questions 456-520) designed to test your knowledge of AWS services, architectural best practices, and cost optimization strategies for the AWS Solutions Architect Associate certification exam.

## Question Categories
The questions cover the following AWS service areas:
- **Compute & Storage**: EC2, EBS, S3, Lambda
- **Networking**: VPC, Load Balancers, API Gateway
- **Database**: RDS, DynamoDB
- **Security & Identity**: IAM, Organizations, KMS
- **Migration & Transfer**: DataSync, Snowball, Transfer Family
- **Monitoring & Management**: Cost Explorer, AWS Backup
- **Application Integration**: SQS, SNS, AppFlow

## How to Use
1. Read each question carefully
2. Consider all the requirements and constraints mentioned
3. Choose the best answer based on AWS best practices
4. Check your answers against the answer key
5. Review explanations for better understanding

---

## Questions

### Question 456
A company runs applications on Amazon EC2 instances in one AWS Region. The company wants to back up the EC2 instances to a second Region. The company also wants to provision EC2 resources in the second Region and manage the EC2 instances centrally from one AWS account. Which solution will meet these requirements MOST cost-effectively?

**Options:**
1. Create a disaster recovery (DR) plan that has a similar number of EC2 instances in the second Region. Configure data replication.

2. Create point-in-time Amazon Elastic Block Store (Amazon EBS) snapshots of the EC2 instances. Copy the snapshots to the second Region periodically.

3. Create a backup plan by using AWS Backup. Configure cross-Region backup to the second Region for the EC2 instances.

4. Deploy a similar number of EC2 instances in the second Region. Use AWS DataSync to transfer the data from the source Region to the second Region.

---

### Question 457
A company that uses AWS is building an application to transfer data to a product manufacturer. The company has its own identity provider (IdP). The company wants the IdP to authenticate application users while the users use the application to transfer data. The company must use Applicability Statement 2 (AS2) protocol. Which solution will meet these requirements?

**Options:**
1. Use AWS DataSync to transfer the data. Create an AWS Lambda function for IdP authentication.

2. Use Amazon AppFlow flows to transfer the data. Create an Amazon Elastic Container Service (Amazon ECS) task for IdP authentication.

3. Use AWS Transfer Family to transfer the data. Create an AWS Lambda function for IdP authentication.

4. Use AWS Storage Gateway to transfer the data. Create an Amazon Cognito identity pool for IdP authentication.

---

### Question 458
A solutions architect is designing a REST API in Amazon API Gateway for a cash payback service. The application requires 1 GB of memory and 2 GB of storage for its computation resources. The application will require that the data is in a relational format. Which additional combination of AWS services will meet these requirements with the LEAST administrative effort? (Choose two.)

**Options:**
1. Amazon EC2

2. AWS Lambda

3. Amazon RDS

4. Amazon DynamoDB

5. Amazon Elastic Kubernetes Services (Amazon EKS)

---

### Question 459
A company uses AWS Organizations to run workloads within multiple AWS accounts. A tagging policy adds department tags to AWS resources when the company creates tags. An accounting team needs to determine spending on Amazon EC2 consumption. The accounting team must determine which departments are responsible for the costs regardless of AWS account. The accounting team has access to AWS Cost Explorer for all AWS accounts within the organization and needs to access all reports from Cost Explorer. Which solution meets these requirements in the MOST operationally efficient way?

**Options:**
1. From the Organizations management account billing console, activate a user-defined cost allocation tag named department. Create one cost report in Cost Explorer grouping by tag name, and filter by EC2.

2. From the Organizations management account billing console, activate an AWS-defined cost allocation tag named department. Create one cost report in Cost Explorer grouping by tag name, and filter by EC2.

3. From the Organizations member account billing console, activate a user-defined cost allocation tag named department. Create one cost report in Cost Explorer grouping by the tag name, and filter by EC2.

4. From the Organizations member account billing console, activate an AWS-defined cost allocation tag named department. Create one cost report in Cost Explorer grouping by tag name, and filter by EC2.

---

### Question 460
A company wants to securely exchange data between its software as a service (SaaS) application Salesforce account and Amazon S3. The company must encrypt the data at rest by using AWS Key Management Service (AWS KMS) customer managed keys (CMKs). The company must also encrypt the data in transit. The company has enabled API access for the Salesforce account.

**Options:**
1. Create AWS Lambda functions to transfer the data securely from Salesforce to Amazon S3.

2. Create an AWS Step Functions workflow. Define the task to transfer the data securely from Salesforce to Amazon S3.

3. Create Amazon AppFlow flows to transfer the data securely from Salesforce to Amazon S3.

4. Create a custom connector for Salesforce to transfer the data securely from Salesforce to Amazon S3.

---

### Question 461
A company is developing a mobile gaming app in a single AWS Region. The app runs on multiple Amazon EC2 instances in an Auto Scaling group. The company stores the app data in Amazon DynamoDB. The app communicates by using TCP traffic and UDP traffic between the users and the servers. The application will be used globally. The company wants to ensure the lowest possible latency for all users. Which solution will meet these requirements?

**Options:**
1. Use AWS Global Accelerator to create an accelerator. Create an Application Load Balancer (ALB) behind an accelerator endpoint that uses Global Accelerator integration and listening on the TCP and UDP ports. Update the Auto Scaling group to register instances on the ALB.

2. Use AWS Global Accelerator to create an accelerator. Create a Network Load Balancer (NLB) behind an accelerator endpoint that uses Global Accelerator integration and listening on the TCP and UDP ports. Update the Auto Scaling group to register instances on the NLB.

3. Create an Amazon CloudFront content delivery network (CDN) endpoint. Create a Network Load Balancer (NLB) behind the endpoint and listening on the TCP and UDP ports. Update the Auto Scaling group to register instances on the NLB. Update CloudFront to use the NLB as the origin.

4. Create an Amazon CloudFront content delivery network (CDN) endpoint. Create an Application Load Balancer (ALB) behind the endpoint and listening on the TCP and UDP ports. Update the Auto Scaling group to register instances on the ALB. Update CloudFront to use the ALB as the origin.

---

### Question 462
A company has an application that processes customer orders. The company hosts the application on an Amazon EC2 instance that saves the orders to an Amazon Aurora database. Occasionally when traffic is high the workload does not process orders fast enough. What should a solutions architect do to write the orders reliably to the database as quickly as possible?

**Options:**
1. Increase the instance size of the EC2 instance when traffic is high. Write orders to Amazon Simple Notification Service (Amazon SNS). Subscribe the database endpoint to the SNS topic.

2. Write orders to an Amazon Simple Queue Service (Amazon SQS) queue. Use EC2 instances in an Auto Scaling group behind an Application Load Balancer to read from the SQS queue and process orders into the database.

3. Write orders to Amazon Simple Notification Service (Amazon SNS). Subscribe the database endpoint to the SNS topic. Use EC2 instances in an Auto Scaling group behind an Application Load Balancer to read from the SNS topic.

4. Write orders to an Amazon Simple Queue Service (Amazon SQS) queue when the EC2 instance reaches CPU threshold limits. Use scheduled scaling of EC2 instances in an Auto Scaling group behind an Application Load Balancer to read from the SQS queue and process orders into the database.

---

### Question 463
An IoT company is releasing a mattress that has sensors to collect data about a user's sleep. The sensors will send data to an Amazon S3 bucket. The sensors collect approximately 2 MB of data every night for each mattress. The company must process and summarize the data for each mattress. The results need to be available as soon as possible. Data processing will require 1 GB of memory and will finish within 30 seconds. Which solution will meet these requirements MOST cost-effectively?

**Options:**
1. Use AWS Glue with a Scala job

2. Use Amazon EMR with an Apache Spark script

3. Use AWS Lambda with a Python script

4. Use AWS Glue with a PySpark job

---

### Question 464
A company hosts an online shopping application that stores all orders in an Amazon RDS for PostgreSQL Single-AZ DB instance. Management wants to eliminate single points of failure and has asked a solutions architect to recommend an approach to minimize database downtime without requiring any changes to the application code. Which solution meets these requirements?

**Options:**
1. Convert the existing database instance to a Multi-AZ deployment by modifying the database instance and specifying the Multi-AZ option.

2. Create a new RDS Multi-AZ deployment. Take a snapshot of the current RDS instance and restore the new Multi-AZ deployment with the snapshot.

3. Create a read-only replica of the PostgreSQL database in another Availability Zone. Use Amazon Route 53 weighted record sets to distribute requests across the databases.

4. Place the RDS for PostgreSQL database in an Amazon EC2 Auto Scaling group with a minimum group size of two. Use Amazon Route 53 weighted record sets to distribute requests across instances.

---

### Question 465
A company is developing an application to support customer demands. The company wants to deploy the application on multiple Amazon EC2 Nitro-based instances within the same Availability Zone. The company also wants to give the application the ability to write to multiple block storage volumes in multiple EC2 Nitro-based instances simultaneously to achieve higher application availability. Which solution will meet these requirements?

**Options:**
1. Use General Purpose SSD (gp3) EBS volumes with Amazon Elastic Block Store (Amazon EBS) Multi-Attach

2. Use Throughput Optimized HDD (st1) EBS volumes with Amazon Elastic Block Store (Amazon EBS) Multi-Attach

3. Use Provisioned IOPS SSD (io2) EBS volumes with Amazon Elastic Block Store (Amazon EBS) Multi-Attach

4. Use General Purpose SSD (gp2) EBS volumes with Amazon Elastic Block Store (Amazon EBS) Multi-Attach

---

### Question 466
A company designed a stateless two-tier application that uses Amazon EC2 in a single Availability Zone and an Amazon RDS Multi-AZ DB instance. New company management wants to ensure the application is highly available. What should a solutions architect do to meet this requirement?

**Options:**
1. Configure the application to use Multi-AZ EC2 Auto Scaling and create an Application Load Balancer

2. Configure the application to take snapshots of the EC2 instances and send them to a different AWS Region

3. Configure the application to use Amazon Route 53 latency-based routing to feed requests to the application

4. Configure Amazon Route 53 rules to handle incoming requests and create a Multi-AZ Application Load Balancer

---

### Question 467
A company uses AWS Organizations. A member account has purchased a Compute Savings Plan. Because of changes in the workloads inside the member account, the account no longer receives the full benefit of the Compute Savings Plan commitment. The company uses less than 50% of its purchased compute power.

**Options:**
1. Turn on discount sharing from the Billing Preferences section of the account console in the member account that purchased the Compute Savings Plan.

2. Turn on discount sharing from the Billing Preferences section of the account console in the company's Organizations management account.

3. Migrate additional compute workloads from another AWS account to the account that has the Compute Savings Plan.

4. Sell the excess Savings Plan commitment in the Reserved Instance Marketplace.

---

### Question 468
A company is developing a microservices application that will provide a search catalog for customers. The company must use REST APIs to present the frontend of the application to users. The REST APIs must access the backend services that the company hosts in containers in private VPC subnets. Which solution will meet these requirements?

**Options:**
1. Design a WebSocket API by using Amazon API Gateway. Host the application in Amazon Elastic Container Service (Amazon ECS) in a private subnet. Create a private VPC link for API Gateway to access Amazon ECS.

2. Design a REST API by using Amazon API Gateway. Host the application in Amazon Elastic Container Service (Amazon ECS) in a private subnet. Create a private VPC link for API Gateway to access Amazon ECS.

3. Design a WebSocket API by using Amazon API Gateway. Host the application in Amazon Elastic Container Service (Amazon ECS) in a private subnet. Create a security group for API Gateway to access Amazon ECS.

4. Design a REST API by using Amazon API Gateway. Host the application in Amazon Elastic Container Service (Amazon ECS) in a private subnet. Create a security group for API Gateway to access Amazon ECS.

---

### Question 469
A company stores raw collected data in an Amazon S3 bucket. The data is used for several types of analytics on behalf of the company's customers. The type of analytics requested determines the access pattern on the S3 objects. The company cannot predict or control the access pattern. The company wants to reduce its S3 costs. Which solution will meet these requirements?

**Options:**
1. Use S3 replication to transition infrequently accessed objects to S3 Standard-Infrequent Access (S3 Standard-IA)

2. Use S3 Lifecycle rules to transition objects from S3 Standard to Standard-Infrequent Access (S3 Standard-IA)

3. Use S3 Lifecycle rules to transition objects from S3 Standard to S3 Intelligent-Tiering

4. Use S3 Inventory to identify and transition objects that have not been accessed from S3 Standard to S3 Intelligent-Tiering

---

### Question 470
A company has applications hosted on Amazon EC2 instances with IPv6 addresses. The applications must initiate communications with other external applications using the internet. However the company's security policy states that any external service cannot initiate a connection to the EC2 instances. What should a solutions architect recommend to resolve this issue?

**Options:**
1. Create a NAT gateway and make it the destination of the subnet's route table

2. Create an internet gateway and make it the destination of the subnet's route table

3. Create a virtual private gateway and make it the destination of the subnet's route table

4. Create an egress-only internet gateway and make it the destination of the subnet's route table

---

### Question 471
A company is creating an application that runs on containers in a VPC. The application stores and accesses data in an Amazon S3 bucket. During the development phase, the application will store and access 1 TB of data in Amazon S3 each day. The company wants to minimize costs and wants to prevent traffic from traversing the internet whenever possible. Which solution will meet these requirements?

**Options:**
1. Enable S3 Intelligent-Tiering for the S3 bucket

2. Enable S3 Transfer Acceleration for the S3 bucket

3. Create a gateway VPC endpoint for Amazon S3. Associate this endpoint with all route tables in the VPC

4. Create an interface endpoint for Amazon S3 in the VPC. Associate this endpoint with all route tables in the VPC

---

### Question 472
A company has a mobile chat application with a data store based in Amazon DynamoDB. Users would like new messages to be read with as little latency as possible. A solutions architect needs to design an optimal solution that requires minimal application changes. Which method should the solutions architect select?

**Options:**
1. Configure Amazon DynamoDB Accelerator (DAX) for the new messages table. Update the code to use the DAX endpoint.

2. Add DynamoDB read replicas to handle the increased read load. Update the application to point to the read endpoint for the read replicas.

3. Double the number of read capacity units for the new messages table in DynamoDB. Continue to use the existing DynamoDB endpoint.

4. Add an Amazon ElastiCache for Redis cache to the application stack. Update the application to point to the Redis cache endpoint instead of DynamoDB.

---

### Question 473
A company hosts a website on Amazon EC2 instances behind an Application Load Balancer (ALB). The website serves static content. Website traffic is increasing, and the company is concerned about a potential increase in cost.

**Options:**
1. Create an Amazon CloudFront distribution to cache static files at edge locations

2. Create an Amazon ElastiCache cluster. Connect the ALB to the ElastiCache cluster to serve cached files

3. Create an AWS WAF web ACL and associate it with the ALB. Add a rule to the web ACL to cache static files

4. Create a second ALB in an alternative AWS Region. Route user traffic to the closest Region to minimize data transfer costs

---

### Question 474
A company has multiple VPCs across AWS Regions to support and run workloads that are isolated from workloads in other Regions. Because of a recent application launch requirement, the company's VPCs must communicate with all other VPCs across all Regions. Which solution will meet these requirements with the LEAST amount of administrative effort?

**Options:**
1. Use VPC peering to manage VPC communication in a single Region. Use VPC peering across Regions to manage VPC communications.

2. Use AWS Direct Connect gateways across all Regions to connect VPCs across regions and manage VPC communications.

3. Use AWS Transit Gateway to manage VPC communication in a single Region and Transit Gateway peering across Regions to manage VPC communications.

4. Use AWS PrivateLink across all Regions to connect VPCs across Regions and manage VPC communications.

---

### Question 475
A company is designing a containerized application that will use Amazon Elastic Container Service (Amazon ECS). The application needs to access a shared file system that is highly durable and can recover data to another AWS Region with a recovery point objective (RPO) of 8 hours. The file system needs to provide a mount target in each Availability Zone within a Region. A solutions architect wants to use AWS Backup to manage the replication to another Region. Which solution will meet these requirements?

**Options:**
1. Amazon FSx for Windows File Server with a Multi-AZ deployment

2. Amazon FSx for NetApp ONTAP with a Multi-AZ deployment

3. Amazon Elastic File System (Amazon EFS) with the Standard storage class

4. Amazon FSx for OpenZFS

---

### Question 476
A company is expecting rapid growth in the near future. A solutions architect needs to configure existing users and grant permissions to new users on AWS. The solutions architect has decided to create IAM groups. The solutions architect will add the new users to IAM groups based on department. Which additional action is the MOST secure way to grant permissions to the new users?

**Options:**
1. Apply service control policies (SCPs) to manage access permissions

2. Create IAM roles that have least privilege permission. Attach the roles to the IAM groups

3. Create an IAM policy that grants least privilege permission. Attach the policy to the IAM groups

4. Create IAM roles. Associate the roles with a permissions boundary that defines the maximum permissions

---

### Question 477
A company uses NFS to store large video files in on-premises network attached storage. Each video file ranges in size from 1 MB to 500 GB. The total storage is 70 TB and is no longer growing. The company decides to migrate the video files to Amazon S3. The company must migrate the video files as soon as possible while using the least possible network bandwidth. Which solution will meet these requirements?

**Options:**
1. Create an S3 bucket. Create an IAM role that has permissions to write to the S3 bucket. Use the AWS CLI to copy all files locally to the S3 bucket.

2. Create an AWS Snowball Edge job. Receive a Snowball Edge device on premises. Use the Snowball Edge client to transfer data to the device. Return the device so that AWS can import the data into Amazon S3.

3. Deploy an S3 File Gateway on premises. Create a public service endpoint to connect to the S3 File Gateway. Create an S3 bucket. Create a new NFS file share on the S3 File Gateway. Point the new file share to the S3 bucket. Transfer the data from the existing NFS file share to the S3 File Gateway.

4. Set up an AWS Direct Connect connection between the on-premises network and AWS. Deploy an S3 File Gateway on premises. Create a public virtual interface (VIF) to connect to the S3 File Gateway. Create an S3 bucket. Create a new NFS file share on the S3 File Gateway. Point the new file share to the S3 bucket. Transfer the data from the existing NFS file share to the S3 File Gateway.

---

### Question 478
A law firm needs to share information with the public. The information includes hundreds of files that must be publicly readable. Modifications or deletions of the files by anyone before a designated future date are prohibited. Which solution will meet these requirements in the MOST secure way?

**Options:**
1. Upload all files to an Amazon S3 bucket that is configured for static website hosting. Grant read-only IAM permissions to any AWS principals that access the S3 bucket until the designated date.

2. Create a new Amazon S3 bucket with S3 Versioning enabled. Use S3 Object Lock with a retention period in accordance with the designated date. Configure the S3 bucket for static website hosting. Set an S3 bucket policy to allow read-only access to the objects.

3. Create a new Amazon S3 bucket with S3 Versioning enabled. Configure an event trigger to run an AWS Lambda function in case of object modification or deletion. Configure the Lambda function to replace the objects with the original versions from a private S3 bucket.

4. Upload all files to an Amazon S3 bucket that is configured for static website hosting. Select the folder that contains the files. Use S3 Object Lock with a retention period in accordance with the designated date. Grant read-only IAM permissions to any AWS principals that access the S3 bucket.

---

### Question 479
A company is making a prototype of the infrastructure for its new website by manually provisioning the necessary infrastructure. This infrastructure includes an Auto Scaling group, an Application Load Balancer and an Amazon RDS database. After the configuration has been thoroughly validated, the company wants the capability to immediately deploy the infrastructure for development and production use in two Availability Zones in an automated fashion. What should a solutions architect recommend to meet these requirements?

**Options:**
1. Use AWS Systems Manager to replicate and provision the prototype infrastructure in two Availability Zones

2. Define the infrastructure as a template by using the prototype infrastructure as a guide. Deploy the infrastructure with AWS CloudFormation.

3. Use AWS Config to record the inventory of resources that are used in the prototype infrastructure. Use AWS Config to deploy the prototype infrastructure into two Availability Zones.

4. Use AWS Elastic Beanstalk and configure it to use an automated reference to the prototype infrastructure to automatically deploy new environments in two Availability Zones.

---

### Question 480
A business application is hosted on Amazon EC2 and uses Amazon S3 for encrypted object storage. The chief information security officer has directed that no application traffic between the two services should traverse the public internet. Which capability should the solutions architect use to meet the compliance requirements?

**Options:**
1. AWS Key Management Service (AWS KMS)

2. VPC endpoint

3. Private subnet

4. Virtual private gateway

---

### Question 481
A company hosts a three-tier web application in the AWS Cloud. A Multi-AZ Amazon RDS for MySQL server forms the database layer Amazon ElastiCache forms the cache layer. The company wants a caching strategy that adds or updates data in the cache when a customer adds an item to the database. The data in the cache must always match the data in the database. Which solution will meet these requirements?

**Options:**
1. Implement the lazy loading caching strategy

2. Implement the write-through caching strategy

3. Implement the adding TTL caching strategy

4. Implement the AWS AppConfig caching strategy

---

### Question 482
A company wants to migrate 100 GB of historical data from an on-premises location to an Amazon S3 bucket. The company has a 100 megabits per second (Mbps) internet connection on premises. The company needs to encrypt the data in transit to the S3 bucket. The company will store new data directly in Amazon S3. Which solution will meet these requirements with the LEAST operational overhead?

**Options:**
1. Use the s3 sync command in the AWS CLI to move the data directly to an S3 bucket

2. Use AWS DataSync to migrate the data from the on-premises location to an S3 bucket

3. Use AWS Snowball to move the data to an S3 bucket

4. Set up an IPsec VPN from the on-premises location to AWS. Use the s3 cp command in the AWS CLI to move the data directly to an S3 bucket

---

### Question 483
A company containerized a Windows job that runs on .NET 6 Framework under a Windows container. The company wants to run this job in the AWS Cloud. The job runs every 10 minutes. The job's runtime varies between 1 minute and 3 minutes. Which solution will meet these requirements MOST cost-effectively?

**Options:**
1. Create an AWS Lambda function based on the container image of the job. Configure Amazon EventBridge to invoke the function every 10 minutes.

2. Use AWS Batch to create a job that uses AWS Fargate resources. Configure the job scheduling to run every 10 minutes.

3. Use Amazon Elastic Container Service (Amazon ECS) on AWS Fargate to run the job. Create a scheduled task based on the container image of the job to run every 10 minutes.

4. Use Amazon Elastic Container Service (Amazon ECS) on AWS Fargate to run the job. Create a standalone task based on the container image of the job. Use Windows task scheduler to run the job every 10 minutes.

---

### Question 484
A company wants to move from many standalone AWS accounts to a consolidated, multi-account architecture. The company plans to create many new AWS accounts for different business units. The company needs to authenticate access to these AWS accounts by using a centralized corporate directory service. Which combination of actions should a solutions architect recommend to meet these requirements? (Choose two.)

**Options:**
1. Create a new organization in AWS Organizations with all features turned on. Create the new AWS accounts in the organization.

2. Set up an Amazon Cognito identity pool. Configure AWS IAM Identity Center (AWS Single Sign-On) to accept Amazon Cognito authentication.

3. Configure a service control policy (SCP) to manage the AWS accounts. Add AWS IAM Identity Center (AWS Single Sign-On) to AWS Directory Service.

4. Create a new organization in AWS Organizations. Configure the organization's authentication mechanism to use AWS Directory Service directly.

5. Set up AWS IAM Identity Center (AWS Single Sign-On) in the organization. Configure IAM Identity Center, and integrate it with the company's corporate directory service.

---

### Question 485
A company is looking for a solution that can store video archives in AWS from old news footage. The company needs to minimize costs and will rarely need to restore these files. When the files are needed, they must be available in a maximum of five minutes. What is the MOST cost-effective solution?

**Options:**
1. Store the video archives in Amazon S3 Glacier and use Expedited retrievals.

2. Store the video archives in Amazon S3 Glacier and use Standard retrievals.

3. Store the video archives in Amazon S3 Standard-Infrequent Access (S3 Standard-IA).

4. Store the video archives in Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA).

---

### Question 486
A company is building a three-tier application on AWS. The presentation tier will serve a static website. The logic tier is a containerized application. This application will store data in a relational database. The company wants to simplify deployment and to reduce operational costs. Which solution will meet these requirements?

**Options:**
1. Use Amazon S3 to host static content. Use Amazon Elastic Container Service (Amazon ECS) with AWS Fargate for compute power. Use a managed Amazon RDS cluster for the database.

2. Use Amazon CloudFront to host static content. Use Amazon Elastic Container Service (Amazon ECS) with Amazon EC2 for compute power. Use a managed Amazon RDS cluster for the database.

3. Use Amazon S3 to host static content. Use Amazon Elastic Kubernetes Service (Amazon EKS) with AWS Fargate for compute power. Use a managed Amazon RDS cluster for the database.

4. Use Amazon EC2 Reserved Instances to host static content. Use Amazon Elastic Kubernetes Service (Amazon EKS) with Amazon EC2 for compute power. Use a managed Amazon RDS cluster for the database.

---

### Question 487
A company seeks a storage solution for its application. The solution must be highly available and scalable. The solution also must function as a file system, be mountable by multiple Linux instances in AWS and on premises through native protocols, and have no minimum size requirements. The company has set up a Site-to-Site VPN for access from its on-premises network to its VPC. Which storage solution meets these requirements?

**Options:**
1. Amazon FSx Multi-AZ deployments

2. Amazon Elastic Block Store (Amazon EBS) Multi-Attach volumes

3. Amazon Elastic File System (Amazon EFS) with multiple mount targets

4. Amazon Elastic File System (Amazon EFS) with a single mount target and multiple access points

---

### Question 488
A 4-year-old media company is using the AWS Organizations all features feature set to organize its AWS accounts. According to the company's finance team, the billing information on the member accounts must not be accessible to anyone, including the root user of the member accounts. Which solution will meet these requirements?

**Options:**
1. Add all finance team users to an IAM group. Attach an AWS managed policy named Billing to the group.

2. Attach an identity-based policy to deny access to the billing information to all users, including the root user.

3. Create a service control policy (SCP) to deny access to the billing information. Attach the SCP to the root organizational unit (OU).

4. Convert from the Organizations all features feature set to the Organizations consolidated billing feature set.

---

### Question 489
An ecommerce company runs an application in the AWS Cloud that is integrated with an on-premises warehouse solution. The company uses Amazon Simple Notification Service (Amazon SNS) to send order messages to an on-premises HTTPS endpoint so the warehouse application can process the orders. The local data center team has detected that some of the order messages were not received. A solutions architect needs to retain messages that are not delivered and analyze the messages for up to 14 days. Which solution will meet these requirements with the LEAST development effort?

**Options:**
1. Configure an Amazon SNS dead letter queue that has an Amazon Kinesis Data Stream target with a retention period of 14 days.

2. Add an Amazon Simple Queue Service (Amazon SQS) queue with a retention period of 14 days between the application and Amazon SNS.

3. Configure an Amazon SNS dead letter queue that has an Amazon Simple Queue Service (Amazon SQS) target with a retention period of 14 days.

4. Configure an Amazon SNS dead letter queue that has an Amazon DynamoDB target with a TTL attribute set for a retention period of 14 days.

---

### Question 490
A gaming company uses Amazon DynamoDB to store user information such as geographic location, player data, and leaderboards. The company needs to configure continuous backups to an Amazon S3 bucket with a minimal amount of coding. The backups must not affect availability of the application and must not affect the read capacity units (RCUs) that are defined for the table. Which solution meets these requirements?

**Options:**
1. Use an Amazon EMR cluster. Create an Apache Hive job to back up the data to Amazon S3.

2. Export the data directly from DynamoDB to Amazon S3 with continuous backups. Turn on point-in-time recovery for the table.

3. Configure Amazon DynamoDB Streams. Create an AWS Lambda function to consume the stream and export the data to an Amazon S3 bucket.

4. Create an AWS Lambda function to export the data from the database tables to Amazon S3 on a regular basis. Turn on point-in-time recovery for the table.

---

### Question 491
A solutions architect is designing an asynchronous application to process credit card data validation requests for a bank. The application must be secure and be able to process each request at least once. Which solution will meet these requirements MOST cost-effectively?

**Options:**
1. Use AWS Lambda event source mapping. Set Amazon Simple Queue Service (Amazon SQS) standard queues as the event source. Use AWS Key Management Service (SSE-KMS) for encryption. Add the kms:Decrypt permission for the Lambda execution role.

2. Use AWS Lambda event source mapping. Use Amazon Simple Queue Service (Amazon SQS) FIFO queues as the event source. Use SQS managed encryption keys (SSE-SQS) for encryption. Add the encryption key invocation permission for the Lambda function.

3. Use the AWS Lambda event source mapping. Set Amazon Simple Queue Service (Amazon SQS) FIFO queues as the event source. Use AWS KMS keys (SSE-KMS). Add the kms:Decrypt permission for the Lambda execution role.

4. Use the AWS Lambda event source mapping. Set Amazon Simple Queue Service (Amazon SQS) standard queues as the event source. Use AWS KMS keys (SSE-KMS) for encryption. Add the encryption key invocation permission for the Lambda function.

---

### Question 492
A company has multiple AWS accounts for development work. Some staff consistently use oversized Amazon EC2 instances, which causes the company to exceed the yearly budget for the development accounts. The company wants to centrally restrict the creation of AWS resources in these accounts. Which solution will meet these requirements with the LEAST development effort?

**Options:**
1. Develop AWS Systems Manager templates that use an approved EC2 creation process. Use the approved Systems Manager templates to provision EC2 instances.

2. Use AWS Organizations to organize the accounts into organizational units (OUs). Define and attach a service control policy (SCP) to control the usage of EC2 instance types.

3. Configure an Amazon EventBridge rule that invokes an AWS Lambda function when an EC2 instance is created. Stop disallowed EC2 instance types.

4. Set up AWS Service Catalog products for the staff to create the allowed EC2 instance types. Ensure that staff can deploy EC2 instances only by using the Service Catalog products.

---

### Question 493
A company wants to use artificial intelligence (AI) to determine the quality of its customer service calls. The company currently manages calls in four different languages, including English. The company will offer new languages in the future. The company does not have the resources to regularly maintain machine learning (ML) models. The company needs to create written sentiment analysis reports from the customer service call recordings. The customer service call recording text must be translated into English. Which combination of steps will meet these requirements? (Choose three.)

**Options:**
1. Use Amazon Comprehend to translate the audio recordings into English.

2. Use Amazon Lex to create the written sentiment analysis reports.

3. Use Amazon Polly to convert the audio recordings into text.

4. Use Amazon Transcribe to convert the audio recordings in any language into text.

5. Use Amazon Translate to translate text in any language to English.

6. Use Amazon Comprehend to create the sentiment analysis reports.

---

### Question 494
A company uses Amazon EC2 instances to host its internal systems. As part of a deployment operation, an administrator tries to use the AWS CLI to terminate an EC2 instance. However, the administrator receives a 403 (Access Denied) error message. The administrator is using an IAM role that has the following IAM policy attached: What is the cause of the unsuccessful request?

**Options:**
1. The EC2 instance has a resource-based policy with a Deny statement.

2. The principal has not been specified in the policy statement.

3. The "Action" field does not grant the actions that are required to terminate the EC2 instance.

4. The request to terminate the EC2 instance does not originate from the CIDR blocks 192.0.2.0/24 or 203.0.113.0/24.

---

### Question 495
A company is conducting an internal audit. The company wants to ensure that the data in an Amazon S3 bucket that is associated with the company's AWS Lake Formation data lake does not contain sensitive customer or employee data. The company wants to discover personally identifiable information (PII) or financial information, including passport numbers and credit card numbers. Which solution will meet these requirements?

**Options:**
1. Configure AWS Audit Manager on the account. Select the Payment Card Industry Data Security Standards (PCI DSS) for auditing.

2. Configure Amazon S3 Inventory on the S3 bucket. Configure Amazon Athena to query the inventory.

3. Configure Amazon Macie to run a data discovery job that uses managed identifiers for the required data types.

4. Use Amazon S3 Select to run a report across the S3 bucket.

---

### Question 496
A company uses on-premises servers to host its applications. The company is running out of storage capacity. The applications use both block storage and NFS storage. The company needs a high-performing solution that supports local caching without re-architecting its existing applications. Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)

**Options:**
1. Mount Amazon S3 as a file system to the on-premises servers.

2. Deploy an AWS Storage Gateway file gateway to replace NFS storage.

3. Deploy AWS Snowball Edge to provision NFS mounts to on-premises servers.

4. Deploy an AWS Storage Gateway volume gateway to replace the block storage.

5. Deploy Amazon Elastic File System (Amazon EFS) volumes and mount them to on-premises servers.

---

### Question 497
A company has a service that reads and writes large amounts of data from an Amazon S3 bucket in the same AWS Region. The service is deployed on Amazon EC2 instances within the private subnet of a VPC. The service communicates with Amazon S3 over a NAT gateway in the public subnet. However, the company wants a solution that will reduce the data output costs. Which solution will meet these requirements MOST cost-effectively?

**Options:**
1. Provision a dedicated EC2 NAT instance in the public subnet. Configure the route table for the private subnet to use the elastic network interface of this instance as the destination for all S3 traffic.
2. Provision a dedicated EC2 NAT instance in the private subnet. Configure the route table for the public subnet to use the elastic network interface of this instance as the destination for all S3 traffic.
3. Provision a VPC gateway endpoint. Configure the route table for the private subnet to use the gateway endpoint as the route for all S3 traffic.
4. Provision a second NAT gateway. Configure the route table for the private subnet to use this NAT gateway as the destination for all S3 traffic.

---

### Question 498
A company uses Amazon S3 to store high-resolution pictures in an S3 bucket. To minimize application changes, the company stores the pictures as the latest version of an S3 object. The company needs to retain only the two most recent versions of the pictures. The company wants to reduce costs. The company has identified the S3 bucket as a large expense. Which solution will reduce the S3 costs with the LEAST operational overhead?

**Options:**
1. Use S3 Lifecycle to delete expired object versions and retain the two most recent versions.
2. Use an AWS Lambda function to check for older versions and delete all but the two most recent versions.
3. Use S3 Batch Operations to delete noncurrent object versions and retain only the two most recent versions.
4. Deactivate versioning on the S3 bucket and retain the two most recent versions.

---

### Question 499
A company needs to minimize the cost of its 1 Gbps AWS Direct Connect connection. The company's average connection utilization is less than 10%. A solutions architect must recommend a solution that will reduce the cost without compromising security. Which solution will meet these requirements?

**Options:**
1. Set up a new 1 Gbps Direct Connect connection. Share the connection with another AWS account.
2. Set up a new 200 Mbps Direct Connect connection in the AWS Management Console.
3. Contact an AWS Direct Connect Partner to order a 1 Gbps connection. Share the connection with another AWS account.
4. Contact an AWS Direct Connect Partner to order a 200 Mbps hosted connection for an existing AWS account.

---

### Question 500
A company has multiple Windows file servers on premises. The company wants to migrate and consolidate its files into an Amazon FSx for Windows File Server file system. File permissions must be preserved to ensure that access rights do not change. Which solutions will meet these requirements? (Choose two.)

**Options:**
1. Deploy AWS DataSync agents on premises. Schedule DataSync tasks to transfer the data to the FSx for Windows File Server file system.

2. Copy the shares on each file server into Amazon S3 buckets by using the AWS CLI. Schedule AWS DataSync tasks to transfer the data to the FSx for Windows File Server file system.

3. Remove the drives from each file server. Ship the drives to AWS for import into Amazon S3. Schedule AWS DataSync tasks to transfer the data to the FSx for Windows File Server file system.

4. Order an AWS Snowcone device. Connect the device to the on-premises network. Launch AWS DataSync agents on the device. Schedule DataSync tasks to transfer the data to the FSx for Windows File Server file system.

5. Order an AWS Snowball Edge Storage Optimized device. Connect the device to the on-premises network. Copy data to the device by using the AWS CLI. Ship the device back to AWS for import into Amazon S3. Schedule AWS DataSync tasks to transfer the data to the FSx for Windows File Server file system.

---

### Question 501
A company wants to ingest customer payment data into the company's data lake in Amazon S3. The company receives payment data every minute on average. The company wants to analyze the payment data in real time. Then the company wants to ingest the data into the data lake. Which solution will meet these requirements with the MOST operational efficiency?

**Options:**
1. Use Amazon Kinesis Data Streams to ingest data. Use AWS Lambda to analyze the data in real time.

2. Use AWS Glue to ingest data. Use Amazon Kinesis Data Analytics to analyze the data in real time.

3. Use Amazon Kinesis Data Firehose to ingest data. Use Amazon Kinesis Data Analytics to analyze the data in real time.

4. Use Amazon API Gateway to ingest data. Use AWS Lambda to analyze the data in real time.

---

### Question 502
A company runs a website that uses a content management system (CMS) on Amazon EC2. The CMS runs on a single EC2 instance and uses an Amazon Aurora MySQL Multi-AZ DB instance for the data tier. Website images are stored on an Amazon Elastic Block Store (Amazon EBS) volume that is mounted inside the EC2 instance. Which combination of actions should a solutions architect take to improve the performance and resilience of the website? (Choose two.)

**Options:**
1. Move the website images into an Amazon S3 bucket that is mounted on every EC2 instance

2. Share the website images by using an NFS share from the primary EC2 instance. Mount this share on the other EC2 instances.

3. Move the website images onto an Amazon Elastic File System (Amazon EFS) file system that is mounted on every EC2 instance.

4. Create an Amazon Machine Image (AMI) from the existing EC2 instance. Use the AMI to provision new instances behind an Application Load Balancer as part of an Auto Scaling group. Configure the Auto Scaling group to maintain a minimum of two instances. Configure an accelerator in AWS Global Accelerator for the website

5. Create an Amazon Machine Image (AMI) from the existing EC2 instance. Use the AMI to provision new instances behind an Application Load Balancer as part of an Auto Scaling group. Configure the Auto Scaling group to maintain a minimum of two instances. Configure an Amazon CloudFront distribution for the website.

---

### Question 503
A company runs an infrastructure monitoring service. The company is building a new feature that will enable the service to monitor data in customer AWS accounts. The new feature will call AWS APIs in customer accounts to describe Amazon EC2 instances and read Amazon CloudWatch metrics. What should the company do to obtain access to customer accounts in the MOST secure way?

**Options:**
1. Ensure that the customers create an IAM role in their account with read-only EC2 and CloudWatch permissions and a trust policy to the company's account.

2. Create a serverless API that implements a token vending machine to provide temporary AWS credentials for a role with read-only EC2 and CloudWatch permissions.

3. Ensure that the customers create an IAM user in their account with read-only EC2 and CloudWatch permissions. Encrypt and store customer access and secret keys in a secrets management system.

4. Ensure that the customers create an Amazon Cognito user in their account to use an IAM role with read-only EC2 and CloudWatch permissions. Encrypt and store the Amazon Cognito user and password in a secrets management system.

---

### Question 504
A company needs to connect several VPCs in the us-east-1 Region that span hundreds of AWS accounts. The company's networking team has its own AWS account to manage the cloud network. What is the MOST operationally efficient solution to connect the VPCs?

**Options:**
1. Set up VPC peering connections between each VPC. Update each associated subnet's route table

2. Configure a NAT gateway and an internet gateway in each VPC to connect each VPC through the internet

3. Create an AWS Transit Gateway in the networking team's AWS account. Configure static routes from each VPC.

4. Deploy VPN gateways in each VPC. Create a transit VPC in the networking team's AWS account to connect to each VPC.

---

### Question 505
A company has Amazon EC2 instances that run nightly batch jobs to process data. The EC2 instances run in an Auto Scaling group that uses On-Demand billing. If a job fails on one instance, another instance will reprocess the job. The batch jobs run between 12:00 AM and 06:00 AM local time every day. Which solution will provide EC2 instances to meet these requirements MOST cost-effectively?

**Options:**
1. Purchase a 1-year Savings Plan for Amazon EC2 that covers the instance family of the Auto Scaling group that the batch job uses.

2. Purchase a 1-year Reserved Instance for the specific instance type and operating system of the instances in the Auto Scaling group that the batch job uses.

3. Create a new launch template for the Auto Scaling group. Set the instances to Spot Instances. Set a policy to scale out based on CPU usage.

4. Create a new launch template for the Auto Scaling group. Increase the instance size. Set a policy to scale out based on CPU usage.

---

### Question 506
A social media company is building a feature for its website. The feature will give users the ability to upload photos. The company expects significant increases in demand during large events and must ensure that the website can handle the upload traffic from users. Which solution meets these requirements with the MOST scalability?

**Options:**
1. Upload files from the user's browser to the application servers. Transfer the files to an Amazon S3 bucket.

2. Provision an AWS Storage Gateway file gateway. Upload files directly from the user's browser to the file gateway.

3. Generate Amazon S3 presigned URLs in the application. Upload files directly from the user's browser into an S3 bucket.

4. Provision an Amazon Elastic File System (Amazon EFS) file system. Upload files directly from the user's browser to the file system.

---

### Question 507
A company has a web application for travel ticketing. The application is based on a database that runs in a single data center in North America. The company wants to expand the application to serve a global user base. The company needs to deploy the application to multiple AWS Regions. Average latency must be less than 1 second on updates to the reservation database. The company wants to have separate deployments of its web platform across multiple Regions. However, the company must maintain a single primary reservation database that is globally consistent. Which solution should a solutions architect recommend to meet these requirements?

**Options:**
1. Convert the application to use Amazon DynamoDB. Use a global table for the center reservation table. Use the correct Regional endpoint in each Regional deployment.

2. Migrate the database to an Amazon Aurora MySQL database. Deploy Aurora Read Replicas in each Region. Use the correct Regional endpoint in each Regional deployment for access to the database.

3. Migrate the database to an Amazon RDS for MySQL database. Deploy MySQL read replicas in each Region. Use the correct Regional endpoint in each Regional deployment for access to the database.

4. Migrate the application to an Amazon Aurora Serverless database. Deploy instances of the database to each Region. Use the correct Regional endpoint in each Regional deployment to access the database. Use AWS Lambda functions to process event streams in each Region to synchronize the databases.

---

### Question 508
A company has migrated multiple Microsoft Windows Server workloads to Amazon EC2 instances that run in the us-west-1 Region. The company manually backs up the workloads to create an image as needed. In the event of a natural disaster in the us-west-1 Region, the company wants to recover workloads quickly in the us-west-2 Region. The company wants no more than 24 hours of data loss on the EC2 instances. The company also wants to automate any backups of the EC2 instances. Which solutions will meet these requirements with the LEAST administrative effort? (Choose two.)

**Options:**
1. Create an Amazon EC2-backed Amazon Machine Image (AMI) lifecycle policy to create a backup based on tags. Schedule the backup to run twice daily. Copy the image on demand.

2. Create an Amazon EC2-backed Amazon Machine Image (AMI) lifecycle policy to create a backup based on tags. Schedule the backup to run twice daily. Configure the copy to the us-west-2 Region.

3. Create backup vaults in us-west-1 and in us-west-2 by using AWS Backup. Create a backup plan for the EC2 instances based on tag values. Create an AWS Lambda function to run as a scheduled job to copy the backup data to us-west-2.

4. Create a backup vault by using AWS Backup. Use AWS Backup to create a backup plan for the EC2 instances based on tag values. Define the destination for the copy as us-west-2. Specify the backup schedule to run twice daily.

5. Create a backup vault by using AWS Backup. Use AWS Backup to create a backup plan for the EC2 instances based on tag values. Specify the backup schedule to run twice daily. Copy on demand to us-west-2.

---

### Question 509
A company operates a two-tier application for image processing. The application uses two Availability Zones, each with one public subnet and one private subnet. An Application Load Balancer (ALB) for the web tier uses the public subnets. Amazon EC2 instances for the application tier use the private subnets. Users report that the application is running more slowly than expected. A security audit of the web server log files shows that the application is receiving millions of illegitimate requests from a small number of IP addresses. A solutions architect needs to resolve the immediate performance problem while the company investigates a more permanent solution. What should the solutions architect recommend to meet this requirement?

**Options:**
1. Modify the inbound security group for the web tier. Add a deny rule for the IP addresses that are consuming resources.

2. Modify the network ACL for the web tier subnets. Add an inbound deny rule for the IP addresses that are consuming resources.

3. Modify the inbound security group for the application tier. Add a deny rule for the IP addresses that are consuming resources.

4. Modify the network ACL for the application tier subnets. Add an inbound deny rule for the IP addresses that are consuming resources.

---

### Question 510
A global marketing company has applications that run in the ap-southeast-2 Region and the eu-west-1 Region. Applications that run in a VPC in eu-west-1 need to communicate securely with databases that run in a VPC in ap-southeast-2. Which network design will meet these requirements?

**Options:**
1. Create a VPC peering connection between the eu-west-1 VPC and the ap-southeast-2 VPC. Create an inbound rule in the eu-west-1 application security group that allows traffic from the database server IP addresses in the ap-southeast-2 security group.

2. Configure a VPC peering connection between the ap-southeast-2 VPC and the eu-west-1 VPC. Update the subnet route tables. Create an inbound rule in the ap-southeast-2 database security group that references the security group ID of the application servers in eu-west-1.

3. Configure a VPC peering connection between the ap-southeast-2 VPC and the eu-west-1 VPC. Update the subnet route tables. Create an inbound rule in the ap-southeast-2 database security group that allows traffic from the eu-west-1 application server IP addresses.

4. Create a transit gateway with a peering attachment between the eu-west-1 VPC and the ap-southeast-2 VPC. After the transit gateways are properly peered and routing is configured, create an inbound rule in the database security group that references the security group ID of the application servers in eu-west-1.

---

### Question 511
A company is developing software that uses a PostgreSQL database schema. The company needs to configure multiple development environments and databases for the company's developers. On average, each development environment is used for half of the 8-hour workday. Which solution will meet these requirements MOST cost-effectively?

**Options:**
1. Configure each development environment with its own Amazon Aurora PostgreSQL database

2. Configure each development environment with its own Amazon RDS for PostgreSQL Single-AZ DB instances

3. Configure each development environment with its own Amazon Aurora On-Demand PostgreSQL-Compatible database

4. Configure each development environment with its own Amazon S3 bucket by using Amazon S3 Object Select

---

### Question 512
A company uses AWS Organizations with resources tagged by account. The company also uses AWS Backup to back up its AWS infrastructure resources. The company needs to back up all AWS resources. Which solution will meet these requirements with the LEAST operational overhead?

**Options:**
1. Use AWS Config to identify all untagged resources. Tag the identified resources programmatically. Use tags in the backup plan.

2. Use AWS Config to identify all resources that are not running. Add those resources to the backup vault.

3. Require all AWS account owners to review their resources to identify the resources that need to be backed up.

4. Use Amazon Inspector to identify all noncompliant resources.

---

### Question 513
A social media company wants to allow its users to upload images in an application that is hosted in the AWS Cloud. The company needs a solution that automatically resizes the images so that the images can be displayed on multiple device types. The application experiences unpredictable traffic patterns throughout the day. The company is seeking a highly available solution that maximizes scalability. What should a solutions architect do to meet these requirements?

**Options:**
1. Create a static website hosted in Amazon S3 that invokes AWS Lambda functions to resize the images and store the images in an Amazon S3 bucket.

2. Create a static website hosted in Amazon CloudFront that invokes AWS Step Functions to resize the images and store the images in an Amazon RDS database.

3. Create a dynamic website hosted on a web server that runs on an Amazon EC2 instance. Configure a process that runs on the EC2 instance to resize the images and store the images in an Amazon S3 bucket.

4. Create a dynamic website hosted on an automatically scaling Amazon Elastic Container Service (Amazon ECS) cluster that creates a resize job in Amazon Simple Queue Service (Amazon SQS). Set up an image-resizing program that runs on an Amazon EC2 instance to process the resize jobs.

---

### Question 514
A company is running a microservices application on Amazon EC2 instances. The company wants to migrate the application to an Amazon Elastic Kubernetes Service (Amazon EKS) cluster for scalability. The company must configure the Amazon EKS control plane with endpoint private access set to true and endpoint public access set to false to maintain security compliance. The company must also put the data plane in private subnets. However, the company has received error notifications because the node cannot join the cluster. Which solution will allow the node to join the cluster?

**Options:**
1. Grant the required permission in AWS Identity and Access Management (IAM) to the AmazonEKSNodeRole IAM role.

2. Create interface VPC endpoints to allow nodes to access the control plane.

3. Recreate nodes in the public subnet. Restrict security groups for EC2 nodes.

4. Allow outbound traffic in the security group of the nodes.

---

### Question 515
A company is migrating an on-premises application to AWS. The company wants to use Amazon Redshift as a solution. Which use cases are suitable for Amazon Redshift in this scenario? (Choose three.)

**Options:**
1. Supporting data APIs to access data with traditional, containerized, and event-driven applications

2. Supporting client-side and server-side encryption

3. Building analytics workloads during specified hours and when the application is not active

4. Caching data to reduce the pressure on the backend database

5. Scaling globally to support petabytes of data and tens of millions of requests per minute

6. Creating a secondary replica of the cluster by using the AWS Management Console

---

### Question 516
A company provides an API interface to customers so the customers can retrieve their financial information. The company expects a larger number of requests during peak usage times of the year. The company requires the API to respond consistently with low latency to ensure customer satisfaction. The company needs to provide a compute host for the API. Which solution will meet these requirements with the LEAST operational overhead?

**Options:**
1. Use an Application Load Balancer and Amazon Elastic Container Service (Amazon ECS).

2. Use Amazon API Gateway and AWS Lambda functions with provisioned concurrency.

3. Use an Application Load Balancer and an Amazon Elastic Kubernetes Service (Amazon EKS) cluster.

4. Use Amazon API Gateway and AWS Lambda functions with reserved concurrency.

---

### Question 517
A company wants to send all AWS Systems Manager Session Manager logs to an Amazon S3 bucket for archival purposes. Which solution will meet this requirement with the MOST operational efficiency?

**Options:**
1. Enable S3 logging in the Systems Manager console. Choose an S3 bucket to send the session data to.

2. Install the Amazon CloudWatch agent. Push all logs to a CloudWatch log group. Export the logs to an S3 bucket from the group for archival purposes.

3. Create a Systems Manager document to upload all server logs to a central S3 bucket. Use Amazon EventBridge to run the Systems Manager document against all servers that are in the account daily.

4. Install an Amazon CloudWatch agent. Push all logs to a CloudWatch log group. Create a CloudWatch logs subscription that pushes any incoming log events to an Amazon Kinesis Data Firehose delivery stream. Set Amazon S3 as the destination.

---

### Question 518
An application uses an Amazon RDS MySQL DB instance. The RDS database is becoming low on disk space. A solutions architect wants to increase the disk space without downtime. Which solution meets these requirements with the LEAST amount of effort?

**Options:**
1. Enable storage autoscaling in RDS
2. Increase the RDS database instance size

3. Change the RDS database instance storage type to Provisioned IOPS

4. Back up the RDS database, increase the storage capacity, restore the database, and stop the previous instance

---

### Question 519
A consulting company provides professional services to customers worldwide. The company provides solutions and tools for customers to expedite gathering and analyzing data on AWS. The company needs to centrally manage and deploy a common set of solutions and tools for customers to use for self-service purposes. Which solution will meet these requirements?

**Options:**
1. Create AWS CloudFormation templates for the customers.

2. Create AWS Service Catalog products for the customers.

3. Create AWS Systems Manager templates for the customers.

4. Create AWS Config items for the customers.

---

### Question 520
A company is designing a new web application that will run on Amazon EC2 Instances. The application will use Amazon DynamoDB for backend data storage. The application traffic will be unpredictable. The company expects that the application read and write throughput to the database will be moderate to high. The company needs to scale in response to application traffic. Which DynamoDB table configuration will meet these requirements MOST cost-effectively?

**Options:**
1. Configure DynamoDB with provisioned read and write by using the DynamoDB Standard table class. Set DynamoDB auto scaling to a maximum defined capacity.

2. Configure DynamoDB in on-demand mode by using the DynamoDB Standard table class.

3. Configure DynamoDB with provisioned read and write by using the DynamoDB Standard Infrequent Access (DynamoDB Standard-IA) table class. Set DynamoDB auto scaling to a maximum defined capacity.

4. Configure DynamoDB in on-demand mode by using the DynamoDB Standard Infrequent Access (DynamoDB Standard-IA) table class.

---

## Answer Key

| Question | Answer | Explanation |
|----------|--------|-------------|
| 456 | 3 | AWS Backup provides automated, cost-effective cross-region backup for EC2 instances |
| 457 | 3 | AWS Transfer Family supports AS2 protocol and can integrate with custom IdP via Lambda |
| 458 | 2, 3 | Lambda (1GB memory) + RDS (relational data) with minimal admin overhead |
| 459 | 1 | User-defined tags from management account provide centralized cost allocation |
| 460 | 3 | Amazon AppFlow natively supports Salesforce integration with encryption |
| 461 | 2 | Global Accelerator + NLB supports both TCP/UDP for gaming applications |
| 462 | 2 | SQS queue + Auto Scaling group provides reliable order processing during high traffic |
| 463 | 3 | Lambda is most cost-effective for short-duration (30s), small data processing |
| 464 | 1 | Converting to Multi-AZ requires no application code changes |
| 465 | 3 | io2 volumes support EBS Multi-Attach for simultaneous access |
| 466 | 1 | Multi-AZ Auto Scaling + ALB provides high availability for stateless apps |
| 467 | 2 | Discount sharing must be enabled from the management account |
| 468 | 2 | REST API + private VPC link enables secure access to private ECS services |
| 469 | 3 | S3 Intelligent-Tiering automatically optimizes costs for unpredictable access patterns |
| 470 | 4 | Egress-only IGW allows IPv6 outbound traffic while blocking inbound connections |
| 471 | 3 | Gateway VPC endpoint for S3 eliminates internet traffic and reduces costs |
| 472 | 1 | DynamoDB DAX provides microsecond latency with minimal application changes |
| 473 | 1 | CloudFront distribution reduces costs by caching static content at edge locations |
| 474 | 3 | Transit Gateway provides the least administrative effort for multi-region VPC connectivity |
| 475 | 3 | Amazon EFS supports cross-AZ mount targets and AWS Backup integration |
| 476 | 3 | IAM policies attached to groups provide least privilege permissions securely |
| 477 | 2 | Snowball Edge is most efficient for large data migration with limited bandwidth |
| 478 | 2 | S3 Object Lock with versioning prevents modifications while allowing public read access |
| 479 | 2 | CloudFormation templates enable automated infrastructure deployment |
| 480 | 2 | VPC endpoints keep traffic between EC2 and S3 within AWS network |
| 481 | 2 | Write-through caching ensures cache and database data consistency |
| 482 | 1 | AWS CLI s3 sync provides encryption in transit with least operational overhead |
| 483 | 3 | ECS Fargate with scheduled tasks is most cost-effective for regular container jobs |
| 484 | 1, 5 | Organizations + IAM Identity Center enables centralized account management and authentication |
| 485 | 1 | S3 Glacier with Expedited retrieval meets 5-minute requirement cost-effectively |
| 486 | 1 | S3 for static hosting, ECS Fargate for containers, RDS for database - simplest deployment |
| 487 | 3 | EFS with multiple mount targets supports Linux, on-premises access via VPN |
| 488 | 3 | SCP at root OU level restricts billing access across all member accounts |
| 489 | 3 | SNS dead letter queue with SQS target retains failed messages for analysis |
| 490 | 2 | DynamoDB export to S3 provides continuous backup without affecting RCUs |
| 491 | 1 | Standard SQS + SSE-KMS is most cost-effective for at-least-once processing |
| 492 | 2 | Organizations with SCP provides centralized resource restrictions with least effort |
| 493 | 4, 5, 6 | Transcribe (audio to text) + Translate (to English) + Comprehend (sentiment) |
| 494 | 4 | 403 error likely due to IP condition in policy not matching request origin |
| 495 | 3 | Amazon Macie specializes in PII and sensitive data discovery in S3 |
| 496 | 2, 4 | Storage Gateway file gateway (NFS) + volume gateway (block storage) |
| 497 | 3 | VPC gateway endpoint eliminates NAT gateway costs for S3 traffic |
| 498 | 1 | S3 Lifecycle rules automatically manage object versions with least overhead |
| 499 | 4 | Direct Connect Partner hosted connection reduces cost for low utilization |
| 500 | 1, 4 | DataSync agents preserve permissions; Snowcone for large datasets |
| 501 | 3 | Kinesis Data Firehose + Analytics provides operational efficiency for streaming data |
| 502 | 3, 5 | EFS for shared storage + Auto Scaling with CloudFront for performance/resilience |
| 503 | 1 | Cross-account IAM roles with trust policies provide secure access |
| 504 | 3 | Transit Gateway from networking account provides centralized VPC connectivity |
| 505 | 3 | Spot Instances are most cost-effective for fault-tolerant batch jobs |
| 506 | 3 | S3 presigned URLs provide direct, scalable file uploads |
| 507 | 1 | DynamoDB Global Tables provide global consistency with sub-second latency |
| 508 | 2, 4 | AMI lifecycle with cross-region copy + AWS Backup with automated scheduling |
| 509 | 2 | Network ACL deny rules at web tier subnet level block malicious traffic |
| 510 | 2 | VPC peering + route tables + security group references enable secure cross-region communication |
| 511 | 3 | Aurora On-Demand is most cost-effective for part-time development usage |
| 512 | 1 | AWS Config identifies untagged resources for comprehensive backup coverage |
| 513 | 1 | S3 static hosting + Lambda for image processing provides scalable, serverless solution |
| 514 | 2 | Interface VPC endpoints required for private EKS nodes to access control plane |
| 515 | 1, 2, 3 | Redshift supports data APIs, encryption, and analytics workloads |
| 516 | 2 | API Gateway + Lambda with provisioned concurrency ensures consistent low latency |
| 517 | 4 | CloudWatch agent + Kinesis Data Firehose provides automated log streaming to S3 |
| 518 | 1 | RDS storage autoscaling increases space automatically without downtime |
| 519 | 2 | AWS Service Catalog provides centralized, self-service solution deployment |
| 520 | 2 | DynamoDB on-demand mode automatically scales for unpredictable traffic patterns |

---

## Contributing
Feel free to contribute additional questions, corrections, or improvements to this collection.

## License
This content is for educational purposes only and is not affiliated with AWS or Amazon.
