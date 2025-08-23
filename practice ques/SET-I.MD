# AWS Solutions Architect Practice Questions

This repository contains practice questions for AWS Solutions Architect certification exam preparation. Each question focuses on core AWS services and architectural best practices.

## Questions 521-548

### Question 521
**Scenario:** A retail company has several businesses. The IT team for each business manages its own AWS account. Each team account is part of an organization in AWS Organizations. Each team monitors its product inventory levels in an Amazon DynamoDB table in the team's own AWS account. The company is deploying a central inventory reporting application into a shared AWS account. The application must be able to read items from all the teams' DynamoDB tables.

**Which authentication option will meet these requirements MOST securely?**

A) Integrate DynamoDB with AWS Secrets Manager in the inventory application account. Configure the application to use the correct secret from Secrets Manager to authenticate and read the DynamoDB table. Schedule secret rotation for every 30 days.

B) In every business account, create an IAM user that has programmatic access. Configure the application to use the correct IAM user access key ID and secret access key to authenticate and read the DynamoDB table. Manually rotate IAM access keys every 30 days.

C) In every business account, create an IAM role named BU_ROLE with a policy that gives the role access to the DynamoDB table and a trust policy to trust a specific role in the inventory application account. In the inventory account, create a role named APP_ROLE that allows access to the STS AssumeRole API operation. Configure the application to use APP_ROLE and assume the cross-account role BU_ROLE to read the DynamoDB table.

D) Integrate DynamoDB with AWS Certificate Manager (ACM). Generate identity certificates to authenticate DynamoDB. Configure the application to use the correct certificate to authenticate and read the DynamoDB table.

---

### Question 522
**Scenario:** A company runs container applications by using Amazon Elastic Kubernetes Service (Amazon EKS). The company's workload is not consistent throughout the day. The company wants Amazon EKS to scale in and out according to the workload.

**Which combination of steps will meet these requirements with the LEAST operational overhead? (Choose two.)**

A) Use an AWS Lambda function to resize the EKS cluster.

B) Use the Kubernetes Metrics Server to activate horizontal pod autoscaling.

C) Use the Kubernetes Cluster Autoscaler to manage the number of nodes in the cluster.

D) Use Amazon API Gateway and connect it to Amazon EKS.

E) Use AWS App Mesh to observe network activity.

---

### Question 523
**Scenario:** A company runs a microservice-based serverless web application. The application must be able to retrieve data from multiple Amazon DynamoDB tables. A solutions architect needs to give the application the ability to retrieve the data with no impact on the baseline performance of the application.

**Which solution will meet these requirements in the MOST operationally efficient way?**

A) AWS AppSync pipeline resolvers

B) Amazon CloudFront with Lambda@Edge functions

C) Edge-optimized Amazon API Gateway with AWS Lambda functions

D) Amazon Athena Federated Query with a DynamoDB connector

---

### Question 524
**Scenario:** A company wants to analyze and troubleshoot Access Denied errors and Unauthorized errors that are related to IAM permissions. The company has AWS CloudTrail turned on.

**Which solution will meet these requirements with the LEAST effort?**

A) Use AWS Glue and write custom scripts to query CloudTrail logs for the errors.

B) Use AWS Batch and write custom scripts to query CloudTrail logs for the errors.

C) Search CloudTrail logs with Amazon Athena queries to identify the errors.

D) Search CloudTrail logs with Amazon QuickSight. Create a dashboard to identify the errors.

---

### Question 525
**Scenario:** A company wants to add its existing AWS usage cost to its operation cost dashboard. A solutions architect needs to recommend a solution that will give the company access to its usage cost programmatically. The company must be able to access cost data for the current year and forecast costs for the next 12 months.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Access usage cost-related data by using the AWS Cost Explorer API with pagination.

B) Access usage cost-related data by using downloadable AWS Cost Explorer report .csv files.

C) Configure AWS Budgets actions to send usage cost data to the company through FTP.

D) Create AWS Budgets reports for usage cost data. Send the data to the company through SMTP.

---

### Question 526
**Scenario:** A solutions architect is reviewing the resilience of an application. The solutions architect notices that a database administrator recently failed over the application's Amazon Aurora PostgreSQL database writer instance as part of a scaling exercise. The failover resulted in 3 minutes of downtime for the application.

**Which solution will reduce the downtime for scaling exercises with the LEAST operational overhead?**

A) Create more Aurora PostgreSQL read replicas in the cluster to handle the load during failover.

B) Set up a secondary Aurora PostgreSQL cluster in the same AWS Region. During failover, update the application to use the secondary cluster's writer endpoint.

C) Create an Amazon ElastiCache for Memcached cluster to handle the load during failover.

D) Set up an Amazon RDS proxy for the database. Update the application to use the proxy endpoint.

---

### Question 527
**Scenario:** A company has a regional subscription-based streaming service that runs in a single AWS Region. The architecture consists of web servers and application servers on Amazon EC2 instances. The EC2 instances are in Auto Scaling groups behind Elastic Load Balancers. The architecture includes an Amazon Aurora global database cluster that extends across multiple Availability Zones. The company wants to expand globally and to ensure that its application has minimal downtime.

**Which solution will provide the MOST fault tolerance?**

A) Extend the Auto Scaling groups for the web tier and the application tier to deploy instances in Availability Zones in a second Region. Use an Aurora global database to deploy the database in the primary Region and the second Region. Use Amazon Route 53 health checks with a failover routing policy to the second Region.

B) Deploy the web tier and the application tier to a second Region. Add an Aurora PostgreSQL cross-Region Aurora Replica in the second Region. Use Amazon Route 53 health checks with a failover routing policy to the second Region. Promote the secondary to primary as needed.

C) Deploy the web tier and the application tier to a second Region. Create an Aurora PostgreSQL database in the second Region. Use AWS Database Migration Service (AWS DMS) to replicate the primary database to the second Region. Use Amazon Route 53 health checks with a failover routing policy to the second Region.

D) Deploy the web tier and the application tier to a second Region. Use an Amazon Aurora global database to deploy the database in the primary Region and the second Region. Use Amazon Route 53 health checks with a failover routing policy to the second Region. Promote the secondary to primary as needed.

---

### Question 528
**Scenario:** A data analytics company wants to migrate its batch processing system to AWS. The company receives thousands of small data files periodically during the day through FTP. An on-premises batch job processes the data files overnight. However, the batch job takes hours to finish running. The company wants the AWS solution to process incoming data files as soon as possible with minimal changes to the FTP clients that send the files. The solution must delete the incoming data files after the files have been processed successfully. Processing for each file needs to take 3-8 minutes.

**Which solution will meet these requirements in the MOST operationally efficient way?**

A) Use an Amazon EC2 instance that runs an FTP server to store incoming files as objects in Amazon S3 Glacier Flexible Retrieval. Configure a job queue in AWS Batch. Use Amazon EventBridge rules to invoke the job to process the objects nightly from S3 Glacier Flexible Retrieval. Delete the objects after the job has processed the objects.

B) Use an Amazon EC2 instance that runs an FTP server to store incoming files on an Amazon Elastic Block Store (Amazon EBS) volume. Configure a job queue in AWS Batch. Use Amazon EventBridge rules to invoke the job to process the files nightly from the EBS volume. Delete the files after the job has processed the files.

C) Use AWS Transfer Family to create an FTP server to store incoming files on an Amazon Elastic Block Store (Amazon EBS) volume. Configure a job queue in AWS Batch. Use an Amazon S3 event notification when each file arrives to invoke the job in AWS Batch. Delete the files after the job has processed the files.

D) Use AWS Transfer Family to create an FTP server to store incoming files in Amazon S3 Standard. Create an AWS Lambda function to process the files and to delete the files after they are processed. Use an S3 event notification to invoke the Lambda function when the files arrive.

---

### Question 529
**Scenario:** A company is migrating its workloads to AWS. The company has transactional and sensitive data in its databases. The company wants to use AWS Cloud solutions to increase security and reduce operational overhead for the databases.

**Which solution will meet these requirements?**

A) Migrate the databases to Amazon EC2. Use an AWS Key Management Service (AWS KMS) AWS managed key for encryption.

B) Migrate the databases to Amazon RDS. Configure encryption at rest.

C) Migrate the data to Amazon S3. Use Amazon Macie for data security and protection.

D) Migrate the database to Amazon RDS. Use Amazon CloudWatch Logs for data security and protection.

---

### Question 530
**Scenario:** A company has an online gaming application that has TCP and UDP multiplayer gaming capabilities. The company uses Amazon Route 53 to point the application traffic to multiple Network Load Balancers (NLBs) in different AWS Regions. The company needs to improve application performance and decrease latency for the online game in preparation for user growth.

**Which solution will meet these requirements?**

A) Add an Amazon CloudFront distribution in front of the NLBs. Increase the Cache-Control max-age parameter.

B) Replace the NLBs with Application Load Balancers (ALBs). Configure Route 53 to use latency-based routing.

C) Add AWS Global Accelerator in front of the NLBs. Configure a Global Accelerator endpoint to use the correct listener ports.

D) Add an Amazon API Gateway endpoint behind the NLBs. Enable API caching. Override method caching for the different stages.

---

### Question 531
**Scenario:** A company needs to integrate with a third-party data feed. The data feed sends a webhook to notify an external service when new data is ready for consumption. A developer wrote an AWS Lambda function to retrieve data when the company receives a webhook callback. The developer must make the Lambda function available for the third party to call.

**Which solution will meet these requirements with the MOST operational efficiency?**

A) Create a function URL for the Lambda function. Provide the Lambda function URL to the third party for the webhook.

B) Deploy an Application Load Balancer (ALB) in front of the Lambda function. Provide the ALB URL to the third party for the webhook.

C) Create an Amazon Simple Notification Service (Amazon SNS) topic. Attach the topic to the Lambda function. Provide the public hostname of the SNS topic to the third party for the webhook.

D) Create an Amazon Simple Queue Service (Amazon SQS) queue. Attach the queue to the Lambda function. Provide the public hostname of the SQS queue to the third party for the webhook.

---

### Question 532
**Scenario:** A company has a workload in an AWS Region. Customers connect to and access the workload by using an Amazon API Gateway REST API. The company uses Amazon Route 53 as its DNS provider. The company wants to provide individual and secure URLs for all customers.

**Which combination of steps will meet these requirements with the MOST operational efficiency? (Choose three.)**

A) Register the required domain in a registrar. Create a wildcard custom domain name in a Route 53 hosted zone and record in the zone that points to the API Gateway endpoint.

B) Request a wildcard certificate that matches the domains in AWS Certificate Manager (ACM) in a different Region.

C) Create hosted zones for each customer as required in Route 53. Create zone records that point to the API Gateway endpoint.

D) Request a wildcard certificate that matches the custom domain name in AWS Certificate Manager (ACM) in the same Region.

E) Create multiple API endpoints for each customer in API Gateway.

F) Create a custom domain name in API Gateway for the REST API. Import the certificate from AWS Certificate Manager (ACM).

---

### Question 533
**Scenario:** A company stores data in Amazon S3. According to regulations, the data must not contain personally identifiable information (PII). The company recently discovered that S3 buckets have some objects that contain PII. The company needs to automatically detect PII in S3 buckets and to notify the company's security team.

**Which solution will meet these requirements?**

A) Use Amazon Macie. Create an Amazon EventBridge rule to filter the SensitiveData event type from Macie findings and to send an Amazon Simple Notification Service (Amazon SNS) notification to the security team.

B) Use Amazon GuardDuty. Create an Amazon EventBridge rule to filter the CRITICAL event type from GuardDuty findings and to send an Amazon Simple Notification Service (Amazon SNS) notification to the security team.

C) Use Amazon Macie. Create an Amazon EventBridge rule to filter the SensitiveData:S3Object/Personal event type from Macie findings and to send an Amazon Simple Queue Service (Amazon SQS) notification to the security team.

D) Use Amazon GuardDuty. Create an Amazon EventBridge rule to filter the CRITICAL event type from GuardDuty findings and to send an Amazon Simple Queue Service (Amazon SQS) notification to the security team.

---

### Question 534
**Scenario:** A company wants to build a logging solution for its multiple AWS accounts. The company currently stores the logs from all accounts in a centralized account. The company has created an Amazon S3 bucket in the centralized account to store the VPC flow logs and AWS CloudTrail logs. All logs must be highly available for 30 days for frequent analysis, retained for an additional 60 days for backup purposes, and deleted 90 days after creation.

**Which solution will meet these requirements MOST cost-effectively?**

A) Transition objects to the S3 Standard storage class 30 days after creation. Write an expiration action that directs Amazon S3 to delete objects after 90 days.

B) Transition objects to the S3 Standard-Infrequent Access (S3 Standard-IA) storage class 30 days after creation. Move all objects to the S3 Glacier Flexible Retrieval storage class after 90 days. Write an expiration action that directs Amazon S3 to delete objects after 90 days.

C) Transition objects to the S3 Glacier Flexible Retrieval storage class 30 days after creation. Write an expiration action that directs Amazon S3 to delete objects after 90 days.

D) Transition objects to the S3 One Zone-Infrequent Access (S3 One Zone-IA) storage class 30 days after creation. Move all objects to the S3 Glacier Flexible Retrieval storage class after 90 days. Write an expiration action that directs Amazon S3 to delete objects after 90 days.

---

### Question 535
**Scenario:** A company is building an Amazon Elastic Kubernetes Service (Amazon EKS) cluster for its workloads. All secrets that are stored in Amazon EKS must be encrypted in the Kubernetes etcd key-value store.

**Which solution will meet these requirements?**

A) Create a new AWS Key Management Service (AWS KMS) key. Use AWS Secrets Manager to manage, rotate, and store all secrets in Amazon EKS.

B) Create a new AWS Key Management Service (AWS KMS) key. Enable Amazon EKS KMS secrets encryption on the Amazon EKS cluster.

C) Create the Amazon EKS cluster with default options. Use the Amazon Elastic Block Store (Amazon EBS) Container Storage Interface (CSI) driver as an add-on.

D) Create a new AWS Key Management Service (AWS KMS) key with the alias/aws/ebs alias. Enable default Amazon Elastic Block Store (Amazon EBS) volume encryption for the account.

---

### Question 536
**Scenario:** A company wants to provide data scientists with near real-time read-only access to the company's production Amazon RDS for PostgreSQL database. The database is currently configured as a Single-AZ database. The data scientists use complex queries that will not affect the production database. The company needs a solution that is highly available.

**Which solution will meet these requirements MOST cost-effectively?**

A) Scale the existing production database in a maintenance window to provide enough power for the data scientists.

B) Change the setup from a Single-AZ to a Multi-AZ instance deployment with a larger secondary standby instance. Provide the data scientists access to the secondary instance.

C) Change the setup from a Single-AZ to a Multi-AZ instance deployment. Provide two additional read replicas for the data scientists.

D) Change the setup from a Single-AZ to a Multi-AZ cluster deployment with two readable standby instances. Provide read endpoints to the data scientists.

---

### Question 537
**Scenario:** A company runs a three-tier web application in the AWS Cloud that operates across three Availability Zones. The application architecture has an Application Load Balancer, an Amazon EC2 web server that hosts user session states, and a MySQL database that runs on an EC2 instance. The company expects sudden increases in application traffic. The company wants to be able to scale to meet future application capacity demands and to ensure high availability across all three Availability Zones.

**Which solution will meet these requirements?**

A) Migrate the MySQL database to Amazon RDS for MySQL with a Multi-AZ DB cluster deployment. Use Amazon ElastiCache for Redis with high availability to store session data and to cache reads. Migrate the web server to an Auto Scaling group that is in three Availability Zones.

B) Migrate the MySQL database to Amazon RDS for MySQL with a Multi-AZ DB cluster deployment. Use Amazon ElastiCache for Memcached with high availability to store session data and to cache reads. Migrate the web server to an Auto Scaling group that is in three Availability Zones.

C) Migrate the MySQL database to Amazon DynamoDB. Use DynamoDB Accelerator (DAX) to cache reads. Store the session data in DynamoDB. Migrate the web server to an Auto Scaling group that is in three Availability Zones.

D) Migrate the MySQL database to Amazon RDS for MySQL in a single Availability Zone. Use Amazon ElastiCache for Redis with high availability to store session data and to cache reads. Migrate the web server to an Auto Scaling group that is in three Availability Zones.

---

### Question 538
**Scenario:** A global video streaming company uses Amazon CloudFront as a content distribution network (CDN). The company wants to roll out content in a phased manner across multiple countries. The company needs to ensure that viewers who are outside the countries to which the company rolls out content are not able to view the content.

**Which solution will meet these requirements?**

A) Add geographic restrictions to the content in CloudFront by using an allow list. Set up a custom error message.

B) Set up a new URL for restricted content. Authorize access by using a signed URL and cookies. Set up a custom error message.

C) Encrypt the data for the content that the company distributes. Set up a custom error message.

D) Create a new URL for restricted content. Set up a time-restricted access policy for signed URLs.

---

### Question 539
**Scenario:** A company wants to use the AWS Cloud to improve its on-premises disaster recovery (DR) configuration. The company's core production business application uses Microsoft SQL Server Standard, which runs on a virtual machine (VM). The application has a recovery point objective (RPO) of 30 seconds or fewer and a recovery time objective (RTO) of 60 minutes. The DR solution needs to minimize costs wherever possible.

**Which solution will meet these requirements?**

A) Configure a multi-site active/active setup between the on-premises server and AWS by using Microsoft SQL Server Enterprise with Always On availability groups.

B) Configure a warm standby Amazon RDS for SQL Server database on AWS. Configure AWS Database Migration Service (AWS DMS) to use change data capture (CDC).

C) Use AWS Elastic Disaster Recovery configured to replicate disk changes to AWS as a pilot light.

D) Use third-party backup software to capture backups every night. Store a secondary set of backups in Amazon S3.

---

### Question 540
**Scenario:** A company has an on-premises server that uses an Oracle database to process and store customer information. The company wants to use an AWS database service to achieve higher availability and to improve application performance. The company also wants to offload reporting from its primary database system.

**Which solution will meet these requirements in the MOST operationally efficient way?**

A) Use AWS Database Migration Service (AWS DMS) to create an Amazon RDS DB instance in multiple AWS Regions. Point the reporting functions toward a separate DB instance from the primary DB instance.

B) Use Amazon RDS in a Single-AZ deployment to create an Oracle database. Create a read replica in the same zone as the primary DB instance. Direct the reporting functions to the read replica.

C) Use Amazon RDS deployed in a Multi-AZ cluster deployment to create an Oracle database. Direct the reporting functions to use the reader instance in the cluster deployment.

D) Use Amazon RDS deployed in a Multi-AZ instance deployment to create an Amazon Aurora database. Direct the reporting functions to the reader instances.

---

### Question 541
**Scenario:** A company wants to build a web application on AWS. Client access requests to the website are not predictable and can be idle for a long time. Only customers who have paid a subscription fee can have the ability to sign in and use the web application.

**Which combination of steps will meet these requirements MOST cost-effectively? (Choose three.)**

A) Create an AWS Lambda function to retrieve user information from Amazon DynamoDB. Create an Amazon API Gateway endpoint to accept RESTful APIs. Send the API calls to the Lambda function.

B) Create an Amazon Elastic Container Service (Amazon ECS) service behind an Application Load Balancer to retrieve user information from Amazon RDS. Create an Amazon API Gateway endpoint to accept RESTful APIs. Send the API calls to the Lambda function.

C) Create an Amazon Cognito user pool to authenticate users.

D) Create an Amazon Cognito identity pool to authenticate users.

E) Use AWS Amplify to serve the frontend web content with HTML, CSS, and JS. Use an integrated Amazon CloudFront configuration.

---

### Question 542
**Scenario:** A media company uses an Amazon CloudFront distribution to deliver content over the internet. The company wants only premium customers to have access to the media streams and file content. The company stores all content in an Amazon S3 bucket. The company also delivers content on demand to customers for a specific purpose, such as movie rentals or music downloads.

**Which solution will meet these requirements?**

A) Generate and provide S3 signed cookies to premium customers.

B) Generate and provide CloudFront signed URLs to premium customers.

C) Use origin access control (OAC) to limit the access of non-premium customers.

D) Generate and activate field-level encryption to block non-premium customers.

---

### Question 543
**Scenario:** A company runs Amazon EC2 instances in multiple AWS accounts that are individually billed. The company recently purchased a Savings Plan. Because of changes in the company's business requirements, the company has decommissioned a large number of EC2 instances. The company wants to use its Savings Plan discounts on its other AWS accounts.

**Which combination of steps will meet these requirements? (Choose two.)**

A) From the AWS Account Management Console of the management account, turn on discount sharing from the billing preferences section.

B) From the AWS Account Management Console of the account that purchased the existing Savings Plan, turn on discount sharing from the billing preferences section. Include all accounts.

C) From the AWS Organizations management account, use AWS Resource Access Manager (AWS RAM) to share the Savings Plan with other accounts.

D) Create an organization in AWS Organizations in a new payer account. Invite the other AWS accounts to join the organization from the management account.

E) Create an organization in AWS Organizations in the existing AWS account with the existing EC2 instances and Savings Plan. Invite the other AWS accounts to join the organization from the management account.

---

### Question 544
**Scenario:** A retail company uses a regional Amazon API Gateway API for its public REST APIs. The API Gateway endpoint is a custom domain name that points to an Amazon Route 53 alias record. A solutions architect needs to create a solution that has minimal effects on customers and minimal data loss to release the new version of APIs.

**Which solution will meet these requirements?**

A) Create a canary release deployment stage for API Gateway. Deploy the latest API version. Point an appropriate percentage of traffic to the canary stage. After API verification, promote the canary stage to the production stage.

B) Create a new API Gateway endpoint with a new version of the API in OpenAPI YAML file format. Use the import-to-update operation in merge mode into the API in API Gateway. Deploy the new version of the API to the production stage.

C) Create a new API Gateway endpoint with a new version of the API in OpenAPI JSON file format. Use the import-to-update operation in overwrite mode into the API in API Gateway. Deploy the new version of the API to the production stage.

D) Create a new API Gateway endpoint with new versions of the API definitions. Create a custom domain name for the new API Gateway API. Point the Route 53 alias record to the new API Gateway API custom domain name.

---

### Question 545
**Scenario:** A company wants to direct its users to a backup static error page if the company's primary website is unavailable. The primary website's DNS records are hosted in Amazon Route 53. The domain is pointing to an Application Load Balancer (ALB). The company needs a solution that minimizes changes and infrastructure overhead.

**Which solution will meet these requirements?**

A) Update the Route 53 records to use a latency routing policy. Add a static error page that is hosted in an Amazon S3 bucket to the records so that the traffic is sent to the most responsive endpoints.

B) Set up a Route 53 active-passive failover configuration. Direct traffic to a static error page that is hosted in an Amazon S3 bucket when Route 53 health checks determine that the ALB endpoint is unhealthy.

C) Set up a Route 53 active-active configuration with the ALB and an Amazon EC2 instance that hosts a static error page as endpoints. Configure Route 53 to send requests to the instance only if the health checks fail for the ALB.

D) Update the Route 53 records to use a multivalue answer routing policy. Create a health check. Direct traffic to the website if the health check passes. Direct traffic to a static error page that is hosted in Amazon S3 if the health check does not pass.

---

### Question 546
**Scenario:** A recent analysis of a company's IT expenses highlights the need to reduce backup costs. The company's chief information officer wants to simplify the on-premises backup infrastructure and reduce costs by eliminating the use of physical backup tapes. The company must preserve the existing investment in the on-premises backup applications and workflows.

**What should a solutions architect recommend?**

A) Set up AWS Storage Gateway to connect with the backup applications using the NFS interface.

B) Set up an Amazon EFS file system that connects with the backup applications using the NFS interface.

C) Set up an Amazon EFS file system that connects with the backup applications using the iSCSI interface.

D) Set up AWS Storage Gateway to connect with the backup applications using the iSCSI-virtual tape library (VTL) interface.

---

### Question 547
**Scenario:** A company has data collection sensors at different locations. The data collection sensors stream a high volume of data to the company. The company wants to design a platform on AWS to ingest and process high-volume streaming data. The solution must be scalable and support data collection in near real time. The company must store the data in Amazon S3 for future reporting.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Use Amazon Kinesis Data Firehose to deliver streaming data to Amazon S3.

B) Use AWS Glue to deliver streaming data to Amazon S3.

C) Use AWS Lambda to deliver streaming data and store the data to Amazon S3.

D) Use AWS Database Migration Service (AWS DMS) to deliver streaming data to Amazon S3.

---

### Question 548
**Scenario:** A company has separate AWS accounts for its finance, data analytics, and development departments. Because of costs and security concerns, the company wants to control which services each AWS account can use.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Use AWS Systems Manager templates to control which AWS services each department can use.

B) Create organization units (OUs) for each department in AWS Organizations. Attach service control policies (SCPs) to the OUs.

C) Use AWS CloudFormation to automatically provision only the AWS services that each department can use.

D) Set up a list of products in AWS Service Catalog in the AWS accounts to manage and control the usage of specific AWS services.

---

