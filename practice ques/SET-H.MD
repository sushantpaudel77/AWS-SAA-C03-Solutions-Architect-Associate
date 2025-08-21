# AWS Solutions Architect Associate (SAA) Practice Questions

This repository contains a comprehensive collection of AWS Solutions Architect Associate certification practice questions covering various AWS services and architectural patterns.

## Table of Contents
- [Overview](#overview)
- [Question Categories](#question-categories)
- [How to Use](#how-to-use)
- [Questions](#questions)
- [Answer Key](#answer-key)

## Overview
This collection includes 30 practice questions (Questions 456-485) designed to test your knowledge of AWS services, architectural best practices, and cost optimization strategies for the AWS Solutions Architect Associate certification exam.

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

---

## Contributing
Feel free to contribute additional questions, corrections, or improvements to this collection.

## License
This content is for educational purposes only and is not affiliated with AWS or Amazon.