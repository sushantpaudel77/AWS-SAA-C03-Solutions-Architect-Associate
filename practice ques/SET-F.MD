# AWS Solutions Architect Associate (SAA-C03) Practice Questions

This repository contains practice questions for the AWS Certified Solutions Architect Associate exam. These questions cover various AWS services and architectural patterns commonly tested in the certification exam.

## Table of Contents

- [Question Categories](#question-categories)
- [How to Use](#how-to-use)
- [Questions](#questions)
- [Answer Key](#answer-key)
- [Contributing](#contributing)

## Question Categories

The questions in this collection cover the following AWS services and concepts:

- **Storage Services**: S3, EBS, EFS, FSx, Storage Gateway
- **Compute Services**: EC2, Lambda, Auto Scaling, Elastic Beanstalk
- **Database Services**: RDS, Aurora, DynamoDB
- **Networking**: VPC, ALB, CloudFront, API Gateway, Route 53
- **Security**: IAM, KMS, Secrets Manager, WAF, GuardDuty
- **Monitoring & Management**: CloudWatch, Systems Manager, Inspector
- **Analytics**: Kinesis, Athena, QuickSight
- **Migration & Transfer**: DataSync, Snowball, Database Migration Service
- **Application Integration**: SQS, EventBridge, Step Functions

## How to Use

1. Read each question carefully
2. Consider all the requirements mentioned
3. Think about AWS Well-Architected Framework principles
4. Select the best answer(s) that meet the requirements
5. Check your answers against the answer key
6. Review explanations for questions you got wrong

## Questions

### Question 326: S3 Storage Optimization
An image hosting company uploads its large assets to Amazon S3 Standard buckets. The company uses multipart upload in parallel by using S3 APIs and overwrites if the same object is uploaded again. For the first 30 days after upload, the objects will be accessed frequently. The objects will be used less frequently after 30 days, but the access patterns for each object will be inconsistent. The company must optimize its S3 storage costs while maintaining high availability and resiliency of stored assets.

Which combination of actions should a solutions architect recommend to meet these requirements? (Choose two.)

A) Move assets to S3 Intelligent-Tiering after 30 days  
B) Configure an S3 Lifecycle policy to clean up incomplete multipart uploads  
C) Configure an S3 Lifecycle policy to clean up expired object delete markers  
D) Move assets to S3 Standard-Infrequent Access (S3 Standard-IA) after 30 days  
E) Move assets to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 30 days

---

### Question 327: VPC Security with Network Firewall
A solutions architect must secure a VPC network that hosts Amazon EC2 instances. The EC2 instances contain highly sensitive data and run in a private subnet. According to company policy, the EC2 instances that run in the VPC can access only approved third-party software repositories on the internet for software product updates that use the third party's URL. Other internet traffic must be blocked.

Which solution meets these requirements?

A) Update the route table for the private subnet to route the outbound traffic to an AWS Network Firewall firewall. Configure domain list rule groups  
B) Set up an AWS WAF web ACL. Create a custom set of rules that filter traffic requests based on source and destination IP address range sets  
C) Implement strict inbound security group rules. Configure an outbound rule that allows traffic only to the authorized software repositories on the internet by specifying the URLs  
D) Configure an Application Load Balancer (ALB) in front of the EC2 instances. Direct all outbound traffic to the ALB. Use a URL-based rule listener in the ALB's target group for outbound access to the internet

---

### Question 328: E-commerce Application Scaling
A company is hosting a three-tier ecommerce application in the AWS Cloud. The company hosts the website on Amazon S3 and integrates the website with an API that handles sales requests. The company hosts the API on three Amazon EC2 instances behind an Application Load Balancer (ALB). The API consists of static and dynamic front-end content along with backend workers that process sales requests asynchronously.

The company is expecting a significant and sudden increase in the number of sales requests during events for the launch of new products.

What should a solutions architect recommend to ensure that all the requests are processed successfully?

A) Add an Amazon CloudFront distribution for the dynamic content. Increase the number of EC2 instances to handle the increase in traffic  
B) Add an Amazon CloudFront distribution for the static content. Place the EC2 instances in an Auto Scaling group to launch new instances based on network traffic  
C) Add an Amazon CloudFront distribution for the dynamic content. Add an Amazon ElastiCache instance in front of the ALB to reduce traffic for the API to handle  
D) Add an Amazon CloudFront distribution for the static content. Add an Amazon Simple Queue Service (Amazon SQS) queue to receive requests from the website for later processing by the EC2 instances

---

### Question 329: EC2 Patch Management
A security audit reveals that Amazon EC2 instances are not being patched regularly. A solutions architect needs to provide a solution that will run regular security scans across a large fleet of EC2 instances. The solution should also patch the EC2 instances on a regular schedule and provide a report of each instance's patch status.

Which solution will meet these requirements?

A) Set up Amazon Macie to scan the EC2 instances for software vulnerabilities. Set up a cron job on each EC2 instance to patch the instance on a regular schedule  
B) Turn on Amazon GuardDuty in the account. Configure GuardDuty to scan the EC2 instances for software vulnerabilities. Set up AWS Systems Manager Session Manager to patch the EC2 instances on a regular schedule  
C) Set up Amazon Detective to scan the EC2 instances for software vulnerabilities. Set up an Amazon EventBridge scheduled rule to patch the EC2 instances on a regular schedule  
D) Turn on Amazon Inspector in the account. Configure Amazon Inspector to scan the EC2 instances for software vulnerabilities. Set up AWS Systems Manager Patch Manager to patch the EC2 instances on a regular schedule

---

### Question 330: RDS Encryption at Rest
A company is planning to store data on Amazon RDS DB instances. The company must encrypt the data at rest.

What should a solutions architect do to meet this requirement?

A) Create a key in AWS Key Management Service (AWS KMS). Enable encryption for the DB instances  
B) Create an encryption key. Store the key in AWS Secrets Manager. Use the key to encrypt the DB instances  
C) Generate a certificate in AWS Certificate Manager (ACM). Enable SSL/TLS on the DB instances by using the certificate  
D) Generate a certificate in AWS Identity and Access Management (IAM). Enable SSL/TLS on the DB instances by using the certificate

---

### Question 331: Data Migration with Bandwidth Constraints
A company must migrate 20 TB of data from a data center to the AWS Cloud within 30 days. The company's network bandwidth is limited to 15 Mbps and cannot exceed 70% utilization.

What should a solutions architect do to meet these requirements?

A) Use AWS Snowball  
B) Use AWS DataSync  
C) Use a secure VPN connection  
D) Use Amazon S3 Transfer Acceleration

---

### Question 332: File Server Migration for Remote Access
A company needs to provide its employees with secure access to confidential and sensitive files. The company wants to ensure that the files can be accessed only by authorized users. The files must be downloaded securely to the employees' devices.

The files are stored in an on-premises Windows file server. However, due to an increase in remote usage, the file server is running out of capacity.

Which solution will meet these requirements?

A) Migrate the file server to an Amazon EC2 instance in a public subnet. Configure the security group to limit inbound traffic to the employees' IP addresses  
B) Migrate the files to an Amazon FSx for Windows File Server file system. Integrate the Amazon FSx file system with the on-premises Active Directory. Configure AWS Client VPN  
C) Migrate the files to Amazon S3, and create a private VPC endpoint. Create a signed URL to allow download  
D) Migrate the files to Amazon S3, and create a public VPC endpoint. Allow employees to sign on with AWS IAM Identity Center (AWS Single Sign-On)

---

### Question 333: Auto Scaling for Monthly Batch Processing
A company's application runs on Amazon EC2 instances behind an Application Load Balancer (ALB). The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. On the first day of every month at midnight, the application becomes much slower when the month-end financial calculation batch runs. This causes the CPU utilization of the EC2 instances to immediately peak to 100%, which disrupts the application.

What should a solutions architect recommend to ensure the application is able to handle the workload and avoid downtime?

A) Configure an Amazon CloudFront distribution in front of the ALB  
B) Configure an EC2 Auto Scaling simple scaling policy based on CPU utilization  
C) Configure an EC2 Auto Scaling scheduled scaling policy based on the monthly schedule  
D) Configure Amazon ElastiCache to remove some of the workload from the EC2 instances

---

### Question 334: SFTP with Active Directory Integration
A company wants to give a customer the ability to use on-premises Microsoft Active Directory to download files that are stored in Amazon S3. The customer's application uses an SFTP client to download the files.

Which solution will meet these requirements with the LEAST operational overhead and no changes to the customer's application?

A) Set up AWS Transfer Family with SFTP for Amazon S3. Configure integrated Active Directory authentication  
B) Set up AWS Database Migration Service (AWS DMS) to synchronize the on-premises client with Amazon S3. Configure integrated Active Directory authentication  
C) Set up AWS DataSync to synchronize between the on-premises location and the S3 location by using AWS IAM Identity Center (AWS Single Sign-On)  
D) Set up a Windows Amazon EC2 instance with SFTP to connect the on-premises client with Amazon S3. Integrate AWS Identity and Access Management (IAM)

---

### Question 335: Fast EC2 Instance Provisioning
A company is experiencing sudden increases in demand. The company needs to provision large Amazon EC2 instances from an Amazon Machine Image (AMI). The instances will run in an Auto Scaling group. The company needs a solution that provides minimum initialization latency to meet the demand.

Which solution meets these requirements?

A) Use the aws ec2 register-image command to create an AMI from a snapshot. Use AWS Step Functions to replace the AMI in the Auto Scaling group  
B) Enable Amazon Elastic Block Store (Amazon EBS) fast snapshot restore on a snapshot. Provision an AMI by using the snapshot. Replace the AMI in the Auto Scaling group with the new AMI  
C) Enable AMI creation and define lifecycle rules in Amazon Data Lifecycle Manager (Amazon DLM). Create an AWS Lambda function that modifies the AMI in the Auto Scaling group  
D) Use Amazon EventBridge to invoke AWS Backup lifecycle policies that provision AMIs. Configure Auto Scaling group capacity limits as an event source in EventBridge

---

### Question 336: Database Credential Rotation
A company hosts a multi-tier web application that uses an Amazon Aurora MySQL DB cluster for storage. The application tier is hosted on Amazon EC2 instances. The company's IT security guidelines mandate that the database credentials be encrypted and rotated every 14 days.

What should a solutions architect do to meet this requirement with the LEAST operational effort?

A) Create a new AWS Key Management Service (AWS KMS) encryption key. Use AWS Secrets Manager to create a new secret that uses the KMS key with the appropriate credentials. Associate the secret with the Aurora DB cluster. Configure a custom rotation period of 14 days  
B) Create two parameters in AWS Systems Manager Parameter Store: one for the user name as a string parameter and one that uses the SecureString type for the password. Select AWS Key Management Service (AWS KMS) encryption for the password parameter, and load these parameters in the application tier. Implement an AWS Lambda function that rotates the password every 14 days  
C) Store a file that contains the credentials in an AWS Key Management Service (AWS KMS) encrypted Amazon Elastic File System (Amazon EFS) file system. Mount the EFS file system in all EC2 instances of the application tier. Restrict the access to the file on the file system so that the application can read the file and that only super users can modify the file. Implement an AWS Lambda function that rotates the key in Aurora every 14 days and writes new credentials into the file  
D) Store a file that contains the credentials in an AWS Key Management Service (AWS KMS) encrypted Amazon S3 bucket that the application uses to load the credentials. Download the file to the application regularly to ensure that the correct credentials are used. Implement an AWS Lambda function that rotates the Aurora credentials every 14 days and uploads these credentials to the file in the S3 bucket

---

### Question 337: RDS Read Replica Lag Optimization
A company has deployed a web application on AWS. The company hosts the backend database on Amazon RDS for MySQL with a primary DB instance and five read replicas to support scaling needs. The read replicas must lag no more than 1 second behind the primary DB instance. The database routinely runs scheduled stored procedures.

As traffic on the website increases, the replicas experience additional lag during periods of peak load. A solutions architect must reduce the replication lag as much as possible. The solutions architect must minimize changes to the application code and must minimize ongoing operational overhead.

Which solution will meet these requirements?

A) Migrate the database to Amazon Aurora MySQL. Replace the read replicas with Aurora Replicas, and configure Aurora Auto Scaling. Replace the stored procedures with Aurora MySQL native functions  
B) Deploy an Amazon ElastiCache for Redis cluster in front of the database. Modify the application to check the cache before the application queries the database. Replace the stored procedures with AWS Lambda functions  
C) Migrate the database to a MySQL database that runs on Amazon EC2 instances. Choose large, compute optimized EC2 instances for all replica nodes. Maintain the stored procedures on the EC2 instances  
D) Migrate the database to Amazon DynamoDB. Provision a large number of read capacity units (RCUs) to support the required throughput, and configure on-demand capacity scaling. Replace the stored procedures with DynamoDB streams

---

### Question 338: Disaster Recovery for Aurora
A solutions architect must create a disaster recovery (DR) plan for a high-volume software as a service (SaaS) platform. All data for the platform is stored in an Amazon Aurora MySQL DB cluster.

The DR plan must replicate data to a secondary AWS Region.

Which solution will meet these requirements MOST cost-effectively?

A) Use MySQL binary log replication to an Aurora cluster in the secondary Region. Provision one DB instance for the Aurora cluster in the secondary Region  
B) Set up an Aurora global database for the DB cluster. When setup is complete, remove the DB instance from the secondary Region  
C) Use AWS Database Migration Service (AWS DMS) to continuously replicate data to an Aurora cluster in the secondary Region. Remove the DB instance from the secondary Region  
D) Set up an Aurora global database for the DB cluster. Specify a minimum of one DB instance in the secondary Region

---

### Question 339: Application Credential Security
A company has a custom application with embedded credentials that retrieves information from an Amazon RDS MySQL DB instance. Management says the application must be made more secure with the least amount of programming effort.

What should a solutions architect do to meet these requirements?

A) Use AWS Key Management Service (AWS KMS) to create keys. Configure the application to load the database credentials from AWS KMS. Enable automatic key rotation  
B) Create credentials on the RDS for MySQL database for the application user and store the credentials in AWS Secrets Manager. Configure the application to load the database credentials from Secrets Manager. Create an AWS Lambda function that rotates the credentials in Secret Manager  
C) Create credentials on the RDS for MySQL database for the application user and store the credentials in AWS Secrets Manager. Configure the application to load the database credentials from Secrets Manager. Set up a credentials rotation schedule for the application user in the RDS for MySQL database using Secrets Manager  
D) Create credentials on the RDS for MySQL database for the application user and store the credentials in AWS Systems Manager Parameter Store. Configure the application to load the database credentials from Parameter Store. Set up a credentials rotation schedule for the application user in the RDS for MySQL database using Parameter Store

---

### Question 340: SQL Injection Protection
A media company hosts its website on AWS. The website application's architecture includes a fleet of Amazon EC2 instances behind an Application Load Balancer (ALB) and a database that is hosted on Amazon Aurora. The company's cybersecurity team reports that the application is vulnerable to SQL injection.

How should the company resolve this issue?

A) Use AWS WAF in front of the ALB. Associate the appropriate web ACLs with AWS WAF  
B) Create an ALB listener rule to reply to SQL injections with a fixed response  
C) Subscribe to AWS Shield Advanced to block all SQL injection attempts automatically  
D) Set up Amazon Inspector to block all SQL injection attempts automatically

---

### Question 341: Data Lake Visualization with Column-Level Security
A company has an Amazon S3 data lake that is governed by AWS Lake Formation. The company wants to create a visualization in Amazon QuickSight by joining the data in the data lake with operational data that is stored in an Amazon Aurora MySQL database. The company wants to enforce column-level authorization so that the company's marketing team can access only a subset of columns in the database.

Which solution will meet these requirements with the LEAST operational overhead?

A) Use Amazon EMR to ingest the data directly from the database to the QuickSight SPICE engine. Include only the required columns  
B) Use AWS Glue Studio to ingest the data from the database to the S3 data lake. Attach an IAM policy to the QuickSight users to enforce column-level access control. Use Amazon S3 as the data source in QuickSight  
C) Use AWS Glue Elastic Views to create a materialized view for the database in Amazon S3. Create an S3 bucket policy to enforce column-level access control for the QuickSight users. Use Amazon S3 as the data source in QuickSight  
D) Use a Lake Formation blueprint to ingest the data from the database to the S3 data lake. Use Lake Formation to enforce column-level access control for the QuickSight users. Use Amazon Athena as the data source in QuickSight

---

### Question 342: Automated Auto Scaling for Batch Jobs
A transaction processing company has weekly scripted batch jobs that run on Amazon EC2 instances. The EC2 instances are in an Auto Scaling group. The number of transactions can vary, but the baseline CPU utilization that is noted on each run is at least 60%. The company needs to provision the capacity 30 minutes before the jobs run.

Currently, engineers complete this task by manually modifying the Auto Scaling group parameters. The company does not have the resources to analyze the required capacity trends for the Auto Scaling group counts. The company needs an automated way to modify the Auto Scaling group's desired capacity.

Which solution will meet these requirements with the LEAST operational overhead?

A) Create a dynamic scaling policy for the Auto Scaling group. Configure the policy to scale based on the CPU utilization metric. Set the target value for the metric to 60%  
B) Create a scheduled scaling policy for the Auto Scaling group. Set the appropriate desired capacity, minimum capacity, and maximum capacity. Set the recurrence to weekly. Set the start time to 30 minutes before the batch jobs run  
C) Create a predictive scaling policy for the Auto Scaling group. Configure the policy to scale based on forecast. Set the scaling metric to CPU utilization. Set the target value for the metric to 60%. In the policy, set the instances to pre-launch 30 minutes before the jobs run  
D) Create an Amazon EventBridge event to invoke an AWS Lambda function when the CPU utilization metric value for the Auto Scaling group reaches 60%. Configure the Lambda function to increase the Auto Scaling group's desired capacity and maximum capacity by 20%

---

### Question 343: Multi-Region Disaster Recovery
A solutions architect is designing a company's disaster recovery (DR) architecture. The company has a MySQL database that runs on an Amazon EC2 instance in a private subnet with scheduled backup. The DR design needs to include multiple AWS Regions.

Which solution will meet these requirements with the LEAST operational overhead?

A) Migrate the MySQL database to multiple EC2 instances. Configure a standby EC2 instance in the DR Region. Turn on replication  
B) Migrate the MySQL database to Amazon RDS. Use a Multi-AZ deployment. Turn on read replication for the primary DB instance in the different Availability Zones  
C) Migrate the MySQL database to an Amazon Aurora global database. Host the primary DB cluster in the primary Region. Host the secondary DB cluster in the DR Region  
D) Store the scheduled backup of the MySQL database in an Amazon S3 bucket that is configured for S3 Cross-Region Replication (CRR). Use the data backup to restore the database in the DR Region

---

### Question 344: Large Message Processing in SQS
A company has a Java application that uses Amazon Simple Queue Service (Amazon SQS) to parse messages. The application cannot parse messages that are larger than 256 KB in size. The company wants to implement a solution to give the application the ability to parse messages as large as 50 MB.

Which solution will meet these requirements with the FEWEST changes to the code?

A) Use the Amazon SQS Extended Client Library for Java to host messages that are larger than 256 KB in Amazon S3  
B) Use Amazon EventBridge to post large messages from the application instead of Amazon SQS  
C) Change the limit in Amazon SQS to handle messages that are larger than 256 KB  
D) Store messages that are larger than 256 KB in Amazon Elastic File System (Amazon EFS). Configure Amazon SQS to reference this location in the messages

---

### Question 345: Global Serverless Authentication
A company wants to restrict access to the content of one of its main web applications and to protect the content by using authorization techniques available on AWS. The company wants to implement a serverless architecture and an authentication solution for fewer than 100 users. The solution needs to integrate with the main web application and serve web content globally. The solution must also scale as the company's user base grows while providing the lowest login latency possible.

Which solution will meet these requirements MOST cost-effectively?

A) Use Amazon Cognito for authentication. Use Lambda@Edge for authorization. Use Amazon CloudFront to serve the web application globally  
B) Use AWS Directory Service for Microsoft Active Directory for authentication. Use AWS Lambda for authorization. Use an Application Load Balancer to serve the web application globally  
C) Use Amazon Cognito for authentication. Use AWS Lambda for authorization. Use Amazon S3 Transfer Acceleration to serve the web application globally  
D) Use AWS Directory Service for Microsoft Active Directory for authentication. Use Lambda@Edge for authorization. Use AWS Elastic Beanstalk to serve the web application globally

---

### Question 346: NAS Migration to Cloud Storage
A company has an aging network-attached storage (NAS) array in its data center. The NAS array presents SMB shares and NFS shares to client workstations. The company does not want to purchase a new NAS array. The company also does not want to incur the cost of renewing the NAS array's support contract. Some of the data is accessed frequently, but much of the data is inactive.

A solutions architect needs to implement a solution that migrates the data to Amazon S3, uses S3 Lifecycle policies, and maintains the same look and feel for the client workstations. The solutions architect has identified AWS Storage Gateway as part of the solution.

Which type of storage gateway should the solutions architect provision to meet these requirements?

A) Volume Gateway  
B) Tape Gateway  
C) Amazon FSx File Gateway  
D) Amazon S3 File Gateway

---

### Question 347: Cost Optimization for EC2 Instances
A company has an application that is running on Amazon EC2 instances. A solutions architect has standardized the company on a particular instance family and various instance sizes based on the current needs of the company.

The company wants to maximize cost savings for the application over the next 3 years. The company needs to be able to change the instance family and sizes in the next 6 months based on application popularity and usage.

Which solution will meet these requirements MOST cost-effectively?

A) Compute Savings Plan  
B) EC2 Instance Savings Plan  
C) Zonal Reserved Instances  
D) Standard Reserved Instances

---

### Question 348: DynamoDB Cost Optimization
A company collects data from a large number of participants who use wearable devices. The company stores the data in an Amazon DynamoDB table and uses applications to analyze the data. The data workload is constant and predictable. The company wants to stay at or below its forecasted budget for DynamoDB.

Which solution will meet these requirements MOST cost-effectively?

A) Use provisioned mode and DynamoDB Standard-Infrequent Access (DynamoDB Standard-IA). Reserve capacity for the forecasted workload  
B) Use provisioned mode. Specify the read capacity units (RCUs) and write capacity units (WCUs)  
C) Use on-demand mode. Set the read capacity units (RCUs) and write capacity units (WCUs) high enough to accommodate changes in the workload  
D) Use on-demand mode. Specify the read capacity units (RCUs) and write capacity units (WCUs) with reserved capacity

---

### Question 349: Encrypted Database Snapshot Sharing
A company stores confidential data in an Amazon Aurora PostgreSQL database in the ap-southeast-3 Region. The database is encrypted with an AWS Key Management Service (AWS KMS) customer managed key. The company was recently acquired and must securely share a backup of the database with the acquiring company's AWS account in ap-southeast-3.

What should a solutions architect do to meet these requirements?

A) Create a database snapshot. Copy the snapshot to a new unencrypted snapshot. Share the new snapshot with the acquiring company's AWS account  
B) Create a database snapshot. Add the acquiring company's AWS account to the KMS key policy. Share the snapshot with the acquiring company's AWS account  
C) Create a database snapshot that uses a different AWS managed KMS key. Add the acquiring company's AWS account to the KMS key alias. Share the snapshot with the acquiring company's AWS account  
D) Create a database snapshot. Download the database snapshot. Upload the database snapshot to an Amazon S3 bucket. Update the S3 bucket policy to allow access from the acquiring company's AWS account

---

### Question 350: SQL Server High Availability and Reporting
A company uses a 100 GB Amazon RDS for Microsoft SQL Server Single-AZ DB instance in the us-east-1 Region to store customer transactions. The company needs high availability and automatic recovery for the DB instance.

The company must also run reports on the RDS database several times a year. The report process causes transactions to take longer than usual to post to the customers' accounts. The company needs a solution that will improve the performance of the report process.

Which combination of steps will meet these requirements? (Choose two.)

A) Modify the DB instance from a Single-AZ DB instance to a Multi-AZ deployment  
B) Take a snapshot of the current DB instance. Restore the snapshot to a new RDS deployment in another Availability Zone  
C) Create a read replica of the DB instance in a different Availability Zone. Point all requests for reports to the read replica  
D) Migrate the database to RDS Custom  
E) Use RDS Proxy to limit reporting requests to the maintenance window

---

### Question 351: Event-Driven Serverless Architecture
A company is moving its data management application to AWS. The company wants to transition to an event-driven architecture. The architecture needs to be more distributed and to use serverless concepts while performing the different aspects of the workflow. The company also wants to minimize operational overhead.

Which solution will meet these requirements?

A) Build out the workflow in AWS Glue. Use AWS Glue to invoke AWS Lambda functions to process the workflow steps  
B) Build out the workflow in AWS Step Functions. Deploy the application on Amazon EC2 instances. Use Step Functions to invoke the workflow steps on the EC2 instances  
C) Build out the workflow in Amazon EventBridge. Use EventBridge to invoke AWS Lambda functions on a schedule to process the workflow steps  
D) Build out the workflow in AWS Step Functions. Use Step Functions to create a state machine. Use the state machine to invoke AWS Lambda functions to process the workflow steps

---

### Question 352: Gaming Network with Low Latency
A company is designing the network for an online multi-player game. The game uses the UDP networking protocol and will be deployed in eight AWS Regions. The network architecture needs to minimize latency and packet loss to give end users a high-quality gaming experience.

Which solution will meet these requirements?

A) Setup a transit gateway in each Region. Create inter-Region peering attachments between each transit gateway  
B) Set up AWS Global Accelerator with UDP listeners and endpoint groups in each Region  
C) Set up Amazon CloudFront with UDP turned on. Configure an origin in each Region  
D) Set up a VPC peering mesh between each Region. Turn on UDP for each VPC

---

### Question 353: Database Migration to Managed Service
A company hosts a three-tier web application on Amazon EC2 instances in a single Availability Zone. The web application uses a self-managed MySQL database that is hosted on an EC2 instance to store data in an Amazon Elastic Block Store (Amazon EBS) volume. The MySQL database currently uses a 1 TB Provisioned IOPS SSD (io2) EBS volume. The company expects traffic of 1,000 IOPS for both reads and writes at peak traffic.

The company wants to minimize any disruptions, stabilize performance, and reduce costs while retaining the capacity for double the IOPS. The company wants to move the database tier to a fully managed solution that is highly available and fault tolerant.

Which solution will meet these requirements MOST cost-effectively?

A) Use a Multi-AZ deployment of an Amazon RDS for MySQL DB instance with an io2 Block Express EBS volume  
B) Use a Multi-AZ deployment of an Amazon RDS for MySQL DB instance with a General Purpose SSD (gp2) EBS volume  
C) Use Amazon S3 Intelligent-Tiering access tiers  
D) Use two large EC2 instances to host the database in active-passive mode

---

### Question 354: Database Connection Timeout Resolution
A company hosts a serverless application on AWS. The application uses Amazon API Gateway, AWS Lambda, and an Amazon RDS for PostgreSQL database. The company notices an increase in application errors that result from database connection timeouts during times of peak traffic or unpredictable traffic. The company needs a solution that reduces the application failures with the least amount of change to the code.

What should a solutions architect do to meet these requirements?

A) Reduce the Lambda concurrency rate  
B) Enable RDS Proxy on the RDS DB instance  
C) Resize the RDS DB instance class to accept more connections  
D) Migrate the database to Amazon DynamoDB with on-demand scaling

---

### Question 355: CPU-Intensive Batch Job Migration
A company is migrating an old application to AWS. The application runs a batch job every hour and is CPU intensive. The batch job takes 15 minutes on average with an on-premises server. The server has 64 virtual CPU (vCPU) and 512 GiB of memory.

Which solution will run the batch job within 15 minutes with the LEAST operational overhead?

A) Use AWS Lambda with functional scaling  
B) Use Amazon Elastic Container Service (Amazon ECS) with AWS Fargate  
C) Use Amazon Lightsail with AWS Auto Scaling  
D) Use AWS Batch on Amazon EC2

---

### Question 356: S3 Storage Cost Optimization
A company stores its data objects in Amazon S3 Standard storage. A solutions architect has found that 75% of the data is rarely accessed after 30 days. The company needs all the data to remain immediately accessible with the same high availability and resiliency, but the company wants to minimize storage costs.

Which storage solution will meet these requirements?

A) Move the data objects to S3 Glacier Deep Archive after 30 days  
B) Move the data objects to S3 Standard-Infrequent Access (S3 Standard-IA) after 30 days  
C) Move the data objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 30 days  
D) Move the data objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) immediately

---

### Question 357: Gaming Application Storage Architecture
A gaming company is moving its public scoreboard from a data center to the AWS Cloud. The company uses Amazon EC2 Windows Server instances behind an Application Load Balancer to host its dynamic application. The company needs a highly available storage solution for the application. The application consists of static files and dynamic server-side code.

Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)

A) Store the static files on Amazon S3. Use Amazon CloudFront to cache objects at the edge  
B) Store the static files on Amazon S3. Use Amazon ElastiCache to cache objects at the edge  
C) Store the server-side code on Amazon Elastic File System (Amazon EFS). Mount the EFS volume on each EC2 instance to share the files  
D) Store the server-side code on Amazon FSx for Windows File Server. Mount the FSx for Windows File Server volume on each EC2 instance to share the files  
E) Store the server-side code on a General Purpose SSD (gp2) Amazon Elastic Block Store (Amazon EBS) volume. Mount the EBS volume on each EC2 instance to share the files

---

### Question 358: Dynamic Image Processing
A social media company runs its application on Amazon EC2 instances behind an Application Load Balancer (ALB). The ALB is the origin for an Amazon CloudFront distribution. The application has more than a billion images stored in an Amazon S3 bucket and processes thousands of images each second. The company wants to resize the images dynamically and serve appropriate formats to clients.

Which solution will meet these requirements with the LEAST operational overhead?

A) Install an external image management library on an EC2 instance. Use the image management library to process the images  
B) Create a CloudFront origin request policy. Use the policy to automatically resize images and to serve the appropriate format based on the User-Agent HTTP header in the request  
C) Use a Lambda@Edge function with an external image management library. Associate the Lambda@Edge function with the CloudFront behaviors that serve the images  
D) Create a CloudFront response headers policy. Use the policy to automatically resize images and to serve the appropriate format based on the User-Agent HTTP header in the request

---

### Question 359: Healthcare Data Encryption Compliance
A hospital needs to store patient records in an Amazon S3 bucket. The hospital's compliance team must ensure that all protected health information (PHI) is encrypted in transit and at rest. The compliance team must administer the encryption key for data at rest.

Which solution will meet these requirements?

A) Create a public SSL/TLS certificate in AWS Certificate Manager (ACM). Associate the certificate with Amazon S3. Configure default encryption for each S3 bucket to use server-side encryption with AWS KMS keys (SSE-KMS). Assign the compliance team to manage the KMS keys  
B) Use the aws:SecureTransport condition on S3 bucket policies to allow only encrypted connections over HTTPS (TLS). Configure default encryption for each S3 bucket to use server-side encryption with S3 managed encryption keys (SSE-S3). Assign the compliance team to manage the SSE-S3 keys  
C) Use the aws:SecureTransport condition on S3 bucket policies to allow only encrypted connections over HTTPS (TLS). Configure default encryption for each S3 bucket to use server-side encryption with AWS KMS keys (SSE-KMS). Assign the compliance team to manage the KMS keys  
D) Use the aws:SecureTransport condition on S3 bucket policies to allow only encrypted connections over HTTPS (TLS). Use Amazon Macie to protect the sensitive data that is stored in Amazon S3. Assign the compliance team to manage Macie

---

### Question 360: Private API Gateway Communication
A company uses Amazon API Gateway to run a private gateway with two REST APIs in the same VPC. The BuyStock RESTful web service calls the CheckFunds RESTful web service to ensure that enough funds are available before a stock can be purchased. The company has noticed in the VPC flow logs that the BuyStock RESTful web service calls the CheckFunds RESTful web service over the internet instead of through the VPC. A solutions architect must implement a solution so that the APIs communicate through the VPC.

Which solution will meet these requirements with the FEWEST changes to the code?

A) Add an X-API-Key header in the HTTP header for authorization  
B) Use an interface endpoint  
C) Use a gateway endpoint  
D) Add an Amazon Simple Queue Service (Amazon SQS) queue between the two REST APIs

---

### Question 361: Gaming Application Data Storage
A company hosts a multiplayer gaming application on AWS. The company wants the application to read data with sub-millisecond latency and run one-time queries on historical data.

Which solution will meet these requirements with the LEAST operational overhead?

A) Use Amazon RDS for data that is frequently accessed. Run a periodic custom script to export the data to an Amazon S3 bucket  
B) Store the data directly in an Amazon S3 bucket. Implement an S3 Lifecycle policy to move older data to S3 Glacier Deep Archive for long-term storage. Run one-time queries on the data in Amazon S3 by using Amazon Athena  
C) Use Amazon DynamoDB with DynamoDB Accelerator (DAX) for data that is frequently accessed. Export the data to an Amazon S3 bucket by using DynamoDB table export. Run one-time queries on the data in Amazon S3 by using Amazon Athena  
D) Use Amazon DynamoDB for data that is frequently accessed. Turn on streaming to Amazon Kinesis Data Streams. Use Amazon Kinesis Data Firehose to read the data from Kinesis Data Streams. Store the records in an Amazon S3 bucket

---

### Question 362: Payment Processing Message Ordering
A company uses a payment processing system that requires messages for a particular payment ID to be received in the same order that they were sent. Otherwise, the payments might be processed incorrectly.

Which actions should a solutions architect take to meet this requirement? (Choose two.)

A) Write the messages to an Amazon DynamoDB table with the payment ID as the partition key  
B) Write the messages to an Amazon Kinesis data stream with the payment ID as the partition key  
C) Write the messages to an Amazon ElastiCache for Memcached cluster with the payment ID as the key  
D) Write the messages to an Amazon Simple Queue Service (Amazon SQS) queue. Set the message attribute to use the payment ID  
E) Write the messages to an Amazon Simple Queue Service (Amazon SQS) FIFO queue. Set the message group to use the payment ID

---

## Answer Key

| Question | Answer(s) | Explanation |
|----------|-----------|-------------|
| 326 | A, B | S3 Intelligent-Tiering automatically moves objects between storage classes based on access patterns (A). Lifecycle policy to clean up incomplete multipart uploads prevents storage costs from abandoned uploads (B). |
| 327 | A | AWS Network Firewall with domain list rule groups can filter outbound traffic to specific URLs/domains while blocking other internet access. |
| 328 | D | CloudFront for static content reduces load on backend, SQS queue handles request spikes by decoupling processing from request reception. |
| 329 | D | Amazon Inspector scans for vulnerabilities, Systems Manager Patch Manager automates patching with reporting capabilities. |
| 330 | A | RDS encryption at rest requires AWS KMS keys and enabling encryption during instance creation. |
| 331 | A | With 15 Mbps at 70% utilization (10.5 Mbps effective), transferring 20 TB would take ~200 days. AWS Snowball is needed for this timeline. |
| 332 | B | Amazon FSx for Windows File Server integrates with Active Directory and supports secure remote access via Client VPN. |
| 333 | C | Scheduled scaling policy can proactively scale capacity before the predictable monthly batch job runs. |
| 334 | A | AWS Transfer Family provides SFTP access to S3 with Active Directory integration, requiring no application changes. |
| 335 | B | EBS Fast Snapshot Restore enables rapid AMI provisioning by pre-warming snapshots for immediate availability. |
| 336 | A | AWS Secrets Manager with Aurora integration provides automatic credential rotation with minimal operational effort. |
| 337 | A | Aurora MySQL with Aurora Replicas provides better replication performance and Aurora Auto Scaling handles capacity management. |
| 338 | D | Aurora Global Database provides cross-region replication with at least one DB instance in secondary region for cost-effectiveness. |
| 339 | C | AWS Secrets Manager provides automatic credential rotation for RDS with minimal code changes. |
| 340 | A | AWS WAF protects against SQL injection attacks when placed in front of the ALB. |
| 341 | D | Lake Formation blueprint ingests data and enforces column-level security, Athena serves as QuickSight data source. |
| 342 | B | Scheduled scaling policy automatically provisions capacity at specific times without requiring trend analysis. |
| 343 | C | Aurora Global Database provides automated cross-region replication with minimal operational overhead. |
| 344 | A | SQS Extended Client Library automatically stores large messages in S3 with minimal code changes. |
| 345 | A | Amazon Cognito + Lambda@Edge + CloudFront provides global serverless authentication with low latency. |
| 346 | D | S3 File Gateway provides SMB/NFS access to S3 storage with lifecycle policies for cost optimization. |
| 347 | A | Compute Savings Plan allows instance family/size changes while providing cost savings over 3 years. |
| 348 | A | Provisioned mode with reserved capacity and Standard-IA provides predictable costs for constant workloads. |
| 349 | B | Adding the acquiring company's AWS account to the KMS key policy allows them to decrypt the shared snapshot. |
| 350 | A, C | Multi-AZ provides high availability (A), read replica isolates reporting workload from transactions (C). |
| 351 | D | Step Functions with Lambda provides serverless event-driven architecture with minimal operational overhead. |
| 352 | B | AWS Global Accelerator optimizes UDP traffic routing across multiple regions for gaming applications. |
| 353 | B | RDS Multi-AZ with gp2 provides managed service, high availability, and cost-effective performance for the requirements. |
| 354 | B | RDS Proxy manages database connections and reduces timeouts with minimal code changes. |
| 355 | D | AWS Batch on EC2 can provision the required compute capacity (64 vCPU, 512 GiB) for the batch job. |
| 356 | B | S3 Standard-IA maintains immediate accessibility while reducing costs for infrequently accessed data. |
| 357 | A, D | S3 + CloudFront for static files (A), FSx for Windows File Server for shared server-side code (D). |
| 358 | C | Lambda@Edge can process images dynamically at CloudFront edge locations with custom libraries. |
| 359 | C | aws:SecureTransport ensures encryption in transit, SSE-KMS with compliance team management meets requirements. |
| 360 | B | Interface endpoint allows private API Gateway communication within VPC without code changes. |
| 361 | C | DynamoDB + DAX provides sub-millisecond latency, table export + Athena enables historical queries. |
| 362 | B, E | Kinesis with partition key maintains order per payment ID (B), SQS FIFO with message group ensures ordering (E). |

## Study Tips

1. **Focus on the requirements**: Always identify what the question is asking for (cost optimization, high availability, security, etc.)

2. **Consider operational overhead**: AWS prefers managed services over self-managed solutions

3. **Think about scale**: Consider how solutions will perform under load and growth

4. **Security first**: Always choose the most secure option that meets requirements

5. **Cost optimization**: Look for solutions that balance performance with cost-effectiveness

## Contributing

If you find errors in the questions or answers, or want to contribute additional practice questions, please:

1. Fork this repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## Disclaimer

These practice questions are for educational purposes only. They are not official AWS questions and do not guarantee success on the actual AWS Certified Solutions Architect Associate exam. Always refer to official AWS documentation and training materials for the most current information.

## Resources

- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS Architecture Center](https://aws.amazon.com/architecture/)
- [AWS Solutions Library](https://aws.amazon.com/solutions/)
- [AWS Whitepapers](https://aws.amazon.com/whitepapers/)

---

**Happy studying and good luck with your AWS certification!** 🚀