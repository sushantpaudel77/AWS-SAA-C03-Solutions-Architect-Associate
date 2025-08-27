# AWS Solutions Architect Associate (SAA-C03) Practice Questions

This repository contains 35 comprehensive practice questions for the AWS Certified Solutions Architect Associate exam. These questions cover various AWS services and architectural patterns commonly tested in the certification exam.

## Table of Contents
- [Security & IAM](#security--iam)
- [Compute & Auto Scaling](#compute--auto-scaling)
- [Storage](#storage)
- [Networking & Content Delivery](#networking--content-delivery)
- [Database](#database)
- [Analytics & Big Data](#analytics--big-data)
- [Monitoring & Management](#monitoring--management)
- [Containers](#containers)

---

## Questions

### 1. AWS Root User Security Best Practices
**Question:** An IT consultant is helping the owner of a medium-sized business set up an AWS account. What are the security recommendations he must follow while creating the AWS account root user? (Select two)

**Options:**
- A) Create a strong password for the AWS account root user
- B) Encrypt the access keys and save them on Amazon S3
- C) Enable Multi Factor Authentication (MFA) for the AWS account root user account
- D) Send an email to the business owner with details of the login username and password for the AWS root user
- E) Create AWS account root user access keys and share those keys only with the business owner

**Correct Answers:** A, C

---

### 2. Cross-Account Access
**Question:** An organization wants to delegate access to a set of users from the development environment so that they can access some resources in the production environment which is managed under another AWS account. As a solutions architect, which of the following steps would you recommend?

**Options:**
- A) Create a new IAM role with the required permissions to access the resources in the production environment. The users can then assume this IAM role while accessing the resources from the production environment
- B) It is not possible to access cross-account resources
- C) Create new IAM user credentials for the production environment and share these credentials with the set of users from the development environment
- D) Both IAM roles and IAM users can be used interchangeably for cross-account access

**Correct Answer:** A

---

### 3. In-Memory Data Store for Live Leaderboard
**Question:** The engineering team at an in-home fitness company is evaluating multiple in-memory data stores with the ability to power its on-demand, live leaderboard. The company's leaderboard requires high availability, low latency, and real-time processing to deliver customizable user data for the community of users working out together virtually from the comfort of their home. As a solutions architect, which of the following solutions would you recommend? (Select two)

**Options:**
- A) Power the on-demand, live leaderboard using Amazon DynamoDB as it meets the in-memory, high availability, low latency requirements
- B) Power the on-demand, live leaderboard using Amazon DynamoDB with DynamoDB Accelerator (DAX) as it meets the in-memory, high availability, low latency requirements
- C) Power the on-demand, live leaderboard using Amazon ElastiCache for Redis as it meets the in-memory, high availability, low latency requirements
- D) Power the on-demand, live leaderboard using Amazon RDS for Aurora as it meets the in-memory, high availability, low latency requirements
- E) Power the on-demand, live leaderboard using Amazon Neptune as it meets the in-memory, high availability, low latency requirements

**Correct Answers:** B, C

---

### 4. AWS KMS Key Recovery
**Question:** A social photo-sharing company uses Amazon S3 to store the images uploaded by the users. These images are kept encrypted in Amazon S3 using AWS KMS and the company manages its own KMS keys for encryption. A member of the DevOps team accidentally deleted the AWS KMS key a day ago, thereby rendering the user's photo data unrecoverable. You have been contacted by the company to consult them on possible solutions to this crisis. As a solutions architect, which of the following steps would you recommend?

**Options:**
- A) Contact AWS support to retrieve the AWS KMS key from their backup
- B) The AWS KMS key can be recovered by the AWS root account user
- C) The company should issue a notification on its web application informing the users about the loss of their data
- D) As the AWS KMS key was deleted a day ago, it must be in the 'pending deletion' status and hence you can just cancel the KMS key deletion and recover the key

**Correct Answer:** D

---

### 5. Geographic Access Restriction
**Question:** A media company runs a photo-sharing web application that is accessed across three different countries. The application is deployed on several Amazon EC2 instances running behind an Application Load Balancer. With new government regulations, the company has been asked to block access from two countries and allow access only from the home country of the company. Which configuration should be used to meet this changed requirement?

**Options:**
- A) Configure the security group for the Amazon EC2 instances
- B) Use Geo Restriction feature of Amazon CloudFront in a Amazon VPC
- C) Configure AWS Web Application Firewall (AWS WAF) on the Application Load Balancer in a Amazon VPC
- D) Configure the security group on the Application Load Balancer

**Correct Answer:** C

---

### 6. SNS and Lambda Scaling Issues
**Question:** The engineering team at a Spanish professional football club has built a notification system for its website using Amazon SNS notifications which are then handled by an AWS Lambda function for end-user delivery. During the off-season, the notification systems need to handle about 100 requests per second. During the peak football season, the rate touches about 5000 requests per second and it is noticed that a significant number of the notifications are not being delivered to the end-users on the website. As a solutions architect, which of the following would you suggest as the BEST possible solution?

**Options:**
- A) Amazon SNS message deliveries to AWS Lambda have crossed the account concurrency quota for AWS Lambda, so the team needs to contact AWS support to raise the account limit
- B) The engineering team needs to provision more servers running the Amazon SNS service
- C) Amazon SNS has hit a scalability limit, so the team needs to contact AWS support to raise the account limit
- D) The engineering team needs to provision more servers running the AWS Lambda service

**Correct Answer:** A

---

### 7. Global Application with Regional Failover
**Question:** A gaming company is looking at improving the availability and performance of its global flagship application which utilizes User Datagram Protocol and needs to support fast regional failover in case an AWS Region goes down. The company wants to continue using its own custom DNS service. Which of the following AWS services represents the best solution for this use-case?

**Options:**
- A) AWS Elastic Load Balancing (ELB)
- B) Amazon Route 53
- C) AWS Global Accelerator
- D) Amazon CloudFront

**Correct Answer:** C

---

### 8. Cost-Effective Data Processing Pipeline
**Question:** A geological research agency maintains the seismological data for the last 100 years. The data has a velocity of 1GB per minute. You would like to store the data with only the most relevant attributes to build a predictive model for earthquakes. What AWS services would you use to build the most cost-effective solution with the LEAST amount of infrastructure maintenance?

**Options:**
- A) Ingest the data in Amazon Kinesis Data Streams and use an intermediary AWS Lambda function to filter and transform the incoming stream before the output is dumped on Amazon S3
- B) Ingest the data in Amazon Kinesis Data Analytics and use SQL queries to filter and transform the data before writing to Amazon S3
- C) Ingest the data in a Spark Streaming Cluster on Amazon EMR and use Spark Streaming transformations before writing to Amazon S3
- D) Ingest the data in Amazon Kinesis Data Firehose and use an intermediary AWS Lambda function to filter and transform the incoming stream before the output is dumped on Amazon S3

**Correct Answer:** D

---

### 9. CloudFront Regional Edge Cache Bypass
**Question:** Amazon CloudFront offers a multi-tier cache in the form of regional edge caches that improve latency. However, there are certain content types that bypass the regional edge cache, and go directly to the origin. Which of the following content types skip the regional edge cache? (Select two)

**Options:**
- A) Dynamic content, as determined at request time (cache-behavior configured to forward all headers)
- B) E-commerce assets such as product photos
- C) Static content such as style sheets, JavaScript files
- D) User-generated videos
- E) Proxy methods PUT/POST/PATCH/OPTIONS/DELETE go directly to the origin

**Correct Answers:** A, E

---

### 10. Application Load Balancer Routing
**Question:** The development team at an e-commerce startup has set up multiple microservices running on Amazon EC2 instances under an Application Load Balancer. The team wants to route traffic to multiple back-end services based on the URL path of the HTTP header. So it wants requests for `https://www.example.com/orders` to go to a specific microservice and requests for `https://www.example.com/products` to go to another microservice. Which of the following features of Application Load Balancers can be used for this use-case?

**Options:**
- A) Query string parameter-based routing
- B) Host-based Routing
- C) HTTP header-based routing
- D) Path-based Routing

**Correct Answer:** D

---

### 11. Auto Scaling Target Tracking
**Question:** The engineering team at a data analytics company has observed that its flagship application functions at its peak performance when the underlying Amazon EC2 instances have a CPU utilization of about 50%. The application is built on a fleet of Amazon EC2 instances managed under an Auto Scaling group. The workflow requests are handled by an internal Application Load Balancer that routes the requests to the instances. As a solutions architect, what would you recommend so that the application runs near its peak performance state?

**Options:**
- A) Configure the Auto Scaling group to use a Amazon CloudWatch alarm triggered on a CPU utilization threshold of 50%
- B) Configure the Auto Scaling group to use simple scaling policy and set the CPU utilization as the target metric with a target value of 50%
- C) Configure the Auto Scaling group to use target tracking policy and set the CPU utilization as the target metric with a target value of 50%
- D) Configure the Auto Scaling group to use step scaling policy and set the CPU utilization as the target metric with a target value of 50%

**Correct Answer:** C

---

### 12. High Availability Architecture
**Question:** An e-commerce company is looking for a solution with high availability, as it plans to migrate its flagship application to a fleet of Amazon EC2 instances. The solution should allow for content-based routing as part of the architecture. As a Solutions Architect, which of the following will you suggest for the company?

**Options:**
- A) Use a Network Load Balancer for distributing traffic to the Amazon EC2 instances spread across different Availability Zones (AZs). Configure a Private IP address to mask any failure of an instance
- B) Use an Application Load Balancer for distributing traffic to the Amazon EC2 instances spread across different Availability Zones (AZs). Configure Auto Scaling group to mask any failure of an instance
- C) Use an Auto Scaling group for distributing traffic to the Amazon EC2 instances spread across different Availability Zones (AZs). Configure a Public IP address to mask any failure of an instance
- D) Use an Auto Scaling group for distributing traffic to the Amazon EC2 instances spread across different Availability Zones (AZs). Configure an elastic IP address (EIP) to mask any failure of an instance

**Correct Answer:** B

---

### 13. S3 Object Lock Configuration
**Question:** A company uses Amazon S3 buckets for storing sensitive customer data. The company has defined different retention periods for different objects present in the Amazon S3 buckets, based on the compliance requirements. But, the retention rules do not seem to work as expected. Which of the following options represent a valid configuration for setting up retention periods for objects in Amazon S3 buckets? (Select two)

**Options:**
- A) Different versions of a single object can have different retention modes and periods
- B) When you apply a retention period to an object version explicitly, you specify a Retain Until Date for the object version
- C) The bucket default settings will override any explicit retention mode or period you request on an object version
- D) You cannot place a retention period on an object version through a bucket default setting
- E) When you use bucket default settings, you specify a Retain Until Date for the object version

**Correct Answers:** A, B

---

### 14. GuardDuty Data Deletion
**Question:** A financial services company uses Amazon GuardDuty for analyzing its AWS account metadata to meet the compliance guidelines. However, the company has now decided to stop using Amazon GuardDuty service. All the existing findings have to be deleted and cannot persist anywhere on AWS Cloud. Which of the following techniques will help the company meet this requirement?

**Options:**
- A) Raise a service request with Amazon to completely delete the data from all their backups
- B) Disable the service in the general settings
- C) De-register the service under services tab
- D) Suspend the service in the general settings

**Correct Answer:** B

---

### 15. Oracle Database Customization on AWS
**Question:** A healthcare company uses its on-premises infrastructure to run legacy applications that require specialized customizations to the underlying Oracle database as well as its host operating system (OS). The company also wants to improve the availability of the Oracle database layer. The company has hired you as an AWS Certified Solutions Architect – Associate to build a solution on AWS that meets these requirements while minimizing the underlying infrastructure maintenance effort. Which of the following options represents the best solution for this use case?

**Options:**
- A) Leverage cross AZ read-replica configuration of Amazon RDS for Oracle that allows the Database Administrator (DBA) to access and customize the database environment and the underlying operating system
- B) Leverage multi-AZ configuration of Amazon RDS Custom for Oracle that allows the Database Administrator (DBA) to access and customize the database environment and the underlying operating system
- C) Leverage multi-AZ configuration of Amazon RDS for Oracle that allows the Database Administrator (DBA) to access and customize the database environment and the underlying operating system
- D) Deploy the Oracle database layer on multiple Amazon EC2 instances spread across two Availability Zones (AZs). This deployment configuration guarantees high availability and also allows the Database Administrator (DBA) to access and customize the database environment and the underlying operating system

**Correct Answer:** B

---

### 16. IAM Permissions Boundary
**Question:** An IT company wants to review its security best-practices after an incident was reported where a new developer on the team was assigned full access to Amazon DynamoDB. The developer accidentally deleted a couple of tables from the production environment while building out a new feature. Which is the MOST effective way to address this issue so that such incidents do not recur?

**Options:**
- A) Use permissions boundary to control the maximum permissions employees can grant to the IAM principals
- B) Remove full database access for all IAM users in the organization
- C) Only root user should have full database access in the organization
- D) The CTO should review the permissions for each new developer's IAM user so that such incidents don't recur

**Correct Answer:** A

---

### 17. HPC Placement Groups
**Question:** An ivy-league university is assisting NASA to find potential landing sites for exploration vehicles of unmanned missions to our neighboring planets. The university uses High Performance Computing (HPC) driven application architecture to identify these landing sites. Which of the following Amazon EC2 instance topologies should this application be deployed on?

**Options:**
- A) The Amazon EC2 instances should be deployed in a cluster placement group so that the underlying workload can benefit from low network latency and high network throughput
- B) The Amazon EC2 instances should be deployed in a spread placement group so that there are no correlated failures
- C) The Amazon EC2 instances should be deployed in a partition placement group so that distributed workloads can be handled effectively
- D) The Amazon EC2 instances should be deployed in an Auto Scaling group so that application meets high availability requirements

**Correct Answer:** A

---

### 18. IAM Best Practices
**Question:** A new DevOps engineer has joined a large financial services company recently. As part of his onboarding, the IT department is conducting a review of the checklist for tasks related to AWS Identity and Access Management (AWS IAM). As an AWS Certified Solutions Architect – Associate, which best practices would you recommend? (Select two)

**Options:**
- A) Grant maximum privileges to avoid assigning privileges again
- B) Configure AWS CloudTrail to log all AWS Identity and Access Management (AWS IAM) actions
- C) Use user credentials to provide access specific permissions for Amazon EC2 instances
- D) Create a minimum number of accounts and share these account credentials among employees
- E) Enable AWS Multi-Factor Authentication (AWS MFA) for privileged users

**Correct Answers:** B, E

---

### 19. AMI Cross-Region Copy
**Question:** The solo founder at a tech startup has just created a brand new AWS account. The founder has provisioned an Amazon EC2 instance 1A which is running in AWS Region A. Later, he takes a snapshot of the instance 1A and then creates a new Amazon Machine Image (AMI) in Region A from this snapshot. This AMI is then copied into another Region B. The founder provisions an instance 1B in Region B using this new AMI in Region B. At this point in time, what entities exist in Region B?

**Options:**
- A) 1 Amazon EC2 instance and 1 AMI exist in Region B
- B) 1 Amazon EC2 instance and 1 snapshot exist in Region B
- C) 1 Amazon EC2 instance and 2 AMIs exist in Region B
- D) 1 Amazon EC2 instance, 1 AMI and 1 snapshot exist in Region B

**Correct Answer:** D

---

### 20. Traffic Throttling Services
**Question:** A Big Data analytics company wants to set up an AWS cloud architecture that throttles requests in case of sudden traffic spikes. The company is looking for AWS services that can be used for buffering or throttling to handle such traffic variations. Which of the following services can be used to support this requirement?

**Options:**
- A) Elastic Load Balancer, Amazon Simple Queue Service (Amazon SQS), AWS Lambda
- B) Amazon API Gateway, Amazon Simple Queue Service (Amazon SQS) and Amazon Kinesis
- C) Amazon Simple Queue Service (Amazon SQS), Amazon Simple Notification Service (Amazon SNS) and AWS Lambda
- D) Amazon Gateway Endpoints, Amazon Simple Queue Service (Amazon SQS) and Amazon Kinesis

**Correct Answer:** B

---

### 21. Real-time Analytics API
**Question:** A logistics company is building a multi-tier application to track the location of its trucks during peak operating hours. The company wants these data points to be accessible in real-time in its analytics platform via a REST API. The company has hired you as an AWS Certified Solutions Architect Associate to build a multi-tier solution to store and retrieve this location data for analysis. Which of the following options addresses the given use case?

**Options:**
- A) Leverage Amazon QuickSight with Amazon Redshift
- B) Leverage Amazon API Gateway with Amazon Kinesis Data Analytics
- C) Leverage Amazon API Gateway with AWS Lambda
- D) Leverage Amazon Athena with Amazon S3

**Correct Answer:** B

---

### 22. Storage Cost Comparison
**Question:** A technology blogger wants to write a review on the comparative pricing for various storage types available on AWS Cloud. The blogger has created a test file of size 1 GB with some random data. Next he copies this test file into AWS S3 Standard storage class, provisions an Amazon EBS volume (General Purpose SSD (gp2)) with 100 GB of provisioned storage and copies the test file into the Amazon EBS volume, and lastly copies the test file into an Amazon EFS Standard Storage filesystem. At the end of the month, he analyzes the bill for costs incurred on the respective storage types for the test file. What is the correct order of the storage charges incurred for the test file on these three storage types?

**Options:**
- A) Cost of test file storage on Amazon EFS < Cost of test file storage on Amazon S3 Standard < Cost of test file storage on Amazon EBS
- B) Cost of test file storage on Amazon S3 Standard < Cost of test file storage on Amazon EFS < Cost of test file storage on Amazon EBS
- C) Cost of test file storage on Amazon S3 Standard < Cost of test file storage on Amazon EBS < Cost of test file storage on Amazon EFS
- D) Cost of test file storage on Amazon EBS < Cost of test file storage on Amazon S3 Standard < Cost of test file storage on Amazon EFS

**Correct Answer:** B

---

### 23. GuardDuty Data Sources
**Question:** A retail company uses Amazon EC2 instances, Amazon API Gateway, Amazon RDS, Elastic Load Balancer and Amazon CloudFront services. To improve the security of these services, the Risk Advisory group has suggested a feasibility check for using the Amazon GuardDuty service. Which of the following would you identify as data sources supported by Amazon GuardDuty?

**Options:**
- A) Elastic Load Balancing logs, Domain Name System (DNS) logs, AWS CloudTrail events
- B) VPC Flow Logs, Domain Name System (DNS) logs, AWS CloudTrail events
- C) Amazon CloudFront logs, Amazon API Gateway logs, AWS CloudTrail events
- D) VPC Flow Logs, Amazon API Gateway logs, Amazon S3 access logs

**Correct Answer:** B

---

### 24. Aurora Failover Priority
**Question:** A gaming company uses Amazon Aurora as its primary database service. The company has now deployed 5 multi-AZ read replicas to increase the read throughput and for use as failover target. The replicas have been assigned the following failover priority tiers and corresponding instance sizes are given in parentheses: tier-1 (16 TB), tier-1 (32 TB), tier-10 (16 TB), tier-15 (16 TB), tier-15 (32 TB). In the event of a failover, Amazon Aurora will promote which of the following read replicas?

**Options:**
- A) Tier-10 (16 TB)
- B) Tier-1 (16 TB)
- C) Tier-1 (32 TB)
- D) Tier-15 (32 TB)

**Correct Answer:** C

---

### 25. Security Monitoring Services
**Question:** An IT security consultancy is working on a solution to protect data stored in Amazon S3 from any malicious activity as well as check for any vulnerabilities on Amazon EC2 instances. As a solutions architect, which of the following solutions would you suggest to help address the given requirement?

**Options:**
- A) Use Amazon Inspector to monitor any malicious activity on data stored in Amazon S3. Use security assessments provided by Amazon GuardDuty to check for vulnerabilities on Amazon EC2 instances
- B) Use Amazon Inspector to monitor any malicious activity on data stored in Amazon S3. Use security assessments provided by Amazon Inspector to check for vulnerabilities on Amazon EC2 instances
- C) Use Amazon GuardDuty to monitor any malicious activity on data stored in Amazon S3. Use security assessments provided by Amazon GuardDuty to check for vulnerabilities on Amazon EC2 instances
- D) Use Amazon GuardDuty to monitor any malicious activity on data stored in Amazon S3. Use security assessments provided by Amazon Inspector to check for vulnerabilities on Amazon EC2 instances

**Correct Answer:** D

---

### 26. S3 Storage Class Lifecycle
**Question:** A media agency stores its re-creatable assets on Amazon S3 buckets. The assets are accessed by a large number of users for the first few days and the frequency of access falls down drastically after a week. Although the assets would be accessed occasionally after the first week, they must continue to be immediately accessible when required. The cost of maintaining all the assets on Amazon S3 storage is turning out to be very expensive and the agency is looking at reducing costs as much as possible. As an AWS Certified Solutions Architect – Associate, can you suggest a way to lower the storage costs while fulfilling the business requirements?

**Options:**
- A) Configure a lifecycle policy to transition the objects to Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA) after 7 days
- B) Configure a lifecycle policy to transition the objects to Amazon S3 Standard-Infrequent Access (S3 Standard-IA) after 30 days
- C) Configure a lifecycle policy to transition the objects to Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA) after 30 days
- D) Configure a lifecycle policy to transition the objects to Amazon S3 Standard-Infrequent Access (S3 Standard-IA) after 7 days

**Correct Answer:** D

---

### 27. High I/O Performance Instance Storage
**Question:** A research group runs its flagship application on a fleet of Amazon EC2 instances for a specialized task that must deliver high random I/O performance. Each instance in the fleet would have access to a dataset that is replicated across the instances by the application itself. Because of the resilient application architecture, the specialized task would continue to be processed even if any instance goes down, as the underlying application would ensure the replacement instance has access to the required dataset. Which of the following options is the MOST cost-optimal and resource-efficient solution to build this fleet of Amazon EC2 instances?

**Options:**
- A) Use Amazon EC2 instances with access to Amazon S3 based storage
- B) Use Amazon EC2 instances with Amazon EFS mount points
- C) Use Amazon Elastic Block Store (Amazon EBS) based EC2 instances
- D) Use Instance Store based Amazon EC2 instances

**Correct Answer:** D

---

### 28. S3 Upload Speed Optimization
**Question:** A news network uses Amazon S3 to aggregate the raw video footage from its reporting teams across the US. The news network has recently expanded into new geographies in Europe and Asia. The technical teams at the overseas branch offices have reported huge delays in uploading large video files to the destination Amazon S3 bucket. Which of the following are the MOST cost-effective options to improve the file upload speed into Amazon S3? (Select two)

**Options:**
- A) Use multipart uploads for faster file uploads into the destination Amazon S3 bucket
- B) Create multiple AWS Site-to-Site VPN connections between the AWS Cloud and branch offices in Europe and Asia. Use these VPN connections for faster file uploads into Amazon S3
- C) Use Amazon S3 Transfer Acceleration (Amazon S3TA) to enable faster file uploads into the destination S3 bucket
- D) Use AWS Global Accelerator for faster file uploads into the destination Amazon S3 bucket
- E) Create multiple AWS Direct Connect connections between the AWS Cloud and branch offices in Europe and Asia. Use the direct connect connections for faster file uploads into Amazon S3

**Correct Answers:** A, C

---

### 29. Intermediary Query Data Storage
**Question:** A leading video streaming service delivers billions of hours of content from Amazon S3 to customers around the world. Amazon S3 also serves as the data lake for its big data analytics solution. The data lake has a staging zone where intermediary query results are kept only for 24 hours. These results are also heavily referenced by other parts of the analytics pipeline. Which of the following is the MOST cost-effective strategy for storing this intermediary query data?

**Options:**
- A) Store the intermediary query results in Amazon S3 Standard storage class
- B) Store the intermediary query results in Amazon S3 Glacier Instant Retrieval storage class
- C) Store the intermediary query results in Amazon S3 One Zone-Infrequent Access storage class
- D) Store the intermediary query results in Amazon S3 Standard-Infrequent Access storage class

**Correct Answer:** A

---

### 30. S3 Request Rate Optimization
**Question:** A file-hosting service uses Amazon S3 under the hood to power its storage offerings. Currently all the customer files are uploaded directly under a single Amazon S3 bucket. The engineering team has started seeing scalability issues where customer file uploads have started failing during the peak access hours with more than 5000 requests per second. Which of the following is the MOST resource efficient and cost-optimal way of addressing this issue?

**Options:**
- A) Change the application architecture to create a new Amazon S3 bucket for each customer and then upload each customer's files directly under the respective buckets
- B) Change the application architecture to create customer-specific custom prefixes within the single Amazon S3 bucket and then upload the daily files into those prefixed locations
- C) Change the application architecture to create a new Amazon S3 bucket for each day's data and then upload the daily files directly under that day's bucket
- D) Change the application architecture to use Amazon Elastic File System (Amazon EFS) instead of Amazon S3 for storing the customers' uploaded files

**Correct Answer:** B

---

### 31. EDA Application File System
**Question:** An Electronic Design Automation (EDA) application produces massive volumes of data that can be divided into two categories. The 'hot data' needs to be both processed and stored quickly in a parallel and distributed fashion. The 'cold data' needs to be kept for reference with quick access for reads and updates at a low cost. Which of the following AWS services is BEST suited to accelerate the aforementioned chip design process?

**Options:**
- A) Amazon FSx for Windows File Server
- B) Amazon EMR
- C) Amazon FSx for Lustre
- D) AWS Glue

**Correct Answer:** C

---

### 32. Mobile Game Leaderboard Processing
**Question:** A gaming company is developing a mobile game that streams score updates to a backend processor and then publishes results on a leaderboard. The company has hired you as an AWS Certified Solutions Architect Associate to design a solution that can handle major traffic spikes, process the mobile game updates in the order of receipt, and store the processed updates in a highly available database. The company wants to minimize the management overhead required to maintain the solution. Which of the following will you recommend to meet these requirements?

**Options:**
- A) Push score updates to Amazon Kinesis Data Streams which uses an AWS Lambda function to process these updates and then store these processed updates in Amazon DynamoDB
- B) Push score updates to an Amazon SNS topic, subscribe an AWS Lambda function to this Amazon SNS topic to process the updates and then store these processed updates in a SQL database running on Amazon EC2 instance
- C) Push score updates to an Amazon SQS queue which uses a fleet of Amazon EC2 instances (with Auto Scaling) to process these updates in the Amazon SQS queue and then store these processed updates in an Amazon RDS MySQL database
- D) Push score updates to Amazon Kinesis Data Streams which uses a fleet of Amazon EC2 instances (with Auto Scaling) to process the updates in Amazon Kinesis Data Streams and then store these processed updates in Amazon DynamoDB

**Correct Answer:** A

---

### 33. AWS Shield Advanced Billing
**Question:** A financial services company recently launched an initiative to improve the security of its AWS resources and it had enabled AWS Shield Advanced across multiple AWS accounts owned by the company. Upon analysis, the company has found that the costs incurred are much higher than expected. Which of the following would you attribute as the underlying reason for the unexpectedly high costs for AWS Shield Advanced service?

**Options:**
- A) AWS Shield Advanced also covers AWS Shield Standard plan, thereby resulting in increased costs
- B) AWS Shield Advanced is being used for custom servers, that are not part of AWS Cloud, thereby resulting in increased costs
- C) Consolidated billing has not been enabled. All the AWS accounts should fall under a single consolidated billing for the monthly fee to be charged only once
- D) Savings Plans has not been enabled for the AWS Shield Advanced service across all the AWS accounts

**Correct Answer:** C

---

### 34. S3 Versioning Feature
**Question:** Which of the following features of an Amazon S3 bucket can only be suspended and not disabled once it has been enabled?

**Options:**
- A) Requester Pays
- B) Versioning
- C) Static Website Hosting
- D) Server Access Logging

**Correct Answer:** B

---

### 35. ECS Pricing Models
**Question:** A leading social media analytics company is contemplating moving its dockerized application stack into AWS Cloud. The company is not sure about the pricing for using Amazon ECS with the EC2 launch type compared to the Amazon ECS with the Fargate launch type. Which of the following is correct regarding the pricing for these two services?

**Options:**
- A) Both Amazon ECS with EC2 launch type and Amazon ECS with Fargate launch type are charged based on Amazon EC2 instances and Amazon EBS Elastic Volumes used
- B) Amazon ECS with EC2 launch type is charged based on EC2 instances and EBS volumes used. Amazon ECS with Fargate launch type is charged based on vCPU and memory resources that the containerized application requests
- C) Both Amazon ECS with EC2 launch type and Amazon ECS with Fargate launch type are just charged based on Elastic Container Service used per hour
- D) Both Amazon ECS with EC2 launch type and Amazon ECS with Fargate launch type are charged based on vCPU and memory resources that the containerized application requests

**Correct Answer:** B

---

## Answer Key
1. A, C
2. A
3. B, C
4. D
5. C
6. A
7. C
8. D
9. A, E
10. D
11. C
12. B
13. A, B
14. B
15. B
16. A
17. A
18. B, E
19. D
20. B
21. B
22. B
23. B
24. C
25. D
26. D
27. D
28. A, C
29. A
30. B
31. C
32. A
33. C
34. B
35. B

---

## Study Tips

### Key Topics to Focus On

1. **Security & IAM**
   - Root user security best practices
   - Cross-account access using IAM roles
   - Permissions boundaries
   - MFA implementation
   - AWS KMS key management and recovery

2. **Storage Solutions**
   - S3 storage classes and lifecycle policies
   - S3 performance optimization (multipart uploads, Transfer Acceleration)
   - S3 Object Lock and versioning
   - EBS vs EFS vs Instance Store use cases
   - Storage cost optimization

3. **Compute & Auto Scaling**
   - EC2 placement groups for different use cases
   - Auto Scaling policies (target tracking, step scaling, simple scaling)
   - Load balancer types and routing methods
   - High availability architecture patterns

4. **Networking & Content Delivery**
   - CloudFront caching behavior and regional edge caches
   - AWS WAF for geographic restrictions
   - Global Accelerator vs CloudFront use cases
   - VPC Flow Logs and DNS logging

5. **Database Services**
   - Aurora failover mechanisms and read replica priorities
   - RDS Custom vs standard RDS
   - DynamoDB with DAX for in-memory caching
   - Database high availability patterns

6. **Analytics & Streaming**
   - Kinesis services (Data Streams, Data Firehose, Data Analytics)
   - Real-time data processing architectures
   - Cost-effective data pipeline designs

7. **Monitoring & Security**
   - GuardDuty data sources and capabilities
   - Inspector for vulnerability assessments
   - CloudTrail for API logging
   - Shield Advanced billing and consolidated accounts

8. **Containers & Serverless**
   - ECS pricing models (EC2 vs Fargate)
   - Lambda concurrency limits and scaling
   - Serverless architecture patterns

### Common Exam Patterns

- **Cost Optimization**: Always consider the most cost-effective solution
- **High Availability**: Multi-AZ deployments and fault tolerance
- **Performance**: Right-sizing and performance optimization techniques
- **Security**: Principle of least privilege and defense in depth
- **Scalability**: Auto-scaling and managed services for reduced operational overhead

### Recommended Study Resources

- AWS Well-Architected Framework
- AWS Architecture Center
- AWS Whitepapers on specific services
- AWS CLI and Console hands-on practice
- AWS Solutions Architect Associate Official Study Guide

### Practice Tips

1. Read each question carefully and identify the key requirements
2. Eliminate obviously incorrect answers first
3. Look for keywords that indicate specific AWS services or features
4. Consider cost, performance, and operational overhead in your answers
5. Practice with AWS Free Tier to gain hands-on experience

---

## Contributing

Feel free to contribute additional questions or corrections by submitting a pull request. Please ensure that:

- Questions follow the same format as existing ones
- Correct answers are provided with brief explanations where helpful
- Questions cover different AWS services and architectural patterns
- Content is accurate and up-to-date with current AWS offerings

## License

This collection of practice questions is provided for educational purposes. Please ensure you comply with AWS certification policies when using these materials for exam preparation.

---

## Disclaimer

These practice questions are created for study purposes and may not reflect the exact format or content of the actual AWS Certified Solutions Architect Associate exam. Always refer to official AWS documentation and training materials for the most accurate and up-to-date information.