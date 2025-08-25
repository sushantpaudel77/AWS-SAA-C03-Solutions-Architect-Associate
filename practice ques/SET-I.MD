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

---

## Answer Key

### Questions 521-548

| Question | Correct Answer | Explanation |
|----------|---------------|-------------|
| 521 | C | Cross-account IAM roles with assume role is the most secure approach for cross-account access |
| 522 | B, C | Kubernetes Metrics Server enables HPA, Cluster Autoscaler manages node scaling |
| 523 | A | AWS AppSync pipeline resolvers provide efficient data aggregation from multiple DynamoDB tables |
| 524 | C | Amazon Athena can directly query CloudTrail logs stored in S3 with minimal setup |
| 525 | A | AWS Cost Explorer API provides programmatic access to cost data with forecasting capabilities |
| 526 | D | Amazon RDS Proxy provides connection pooling and reduces failover downtime |
| 527 | D | Aurora Global Database with multi-region deployment provides the highest fault tolerance |
| 528 | D | AWS Transfer Family + S3 + Lambda provides serverless, event-driven file processing |
| 529 | B | Amazon RDS with encryption at rest provides managed security with minimal overhead |
| 530 | C | AWS Global Accelerator optimizes TCP/UDP traffic routing and reduces latency |
| 531 | A | Lambda function URLs provide the simplest way to expose Lambda functions to external services |
| 532 | A, D, F | Wildcard domain + ACM certificate in same region + API Gateway custom domain |
| 533 | A | Amazon Macie detects PII and integrates with EventBridge for notifications |
| 534 | C | S3 Standard → S3 Glacier after 30 days, delete after 90 days is most cost-effective |
| 535 | B | EKS KMS secrets encryption encrypts etcd key-value store |
| 536 | D | Multi-AZ cluster deployment with readable standby instances provides HA and read scaling |
| 537 | A | RDS Multi-AZ + ElastiCache Redis + Auto Scaling provides best scalability and HA |
| 538 | A | CloudFront geographic restrictions with allow list controls content access by region |
| 539 | C | AWS Elastic Disaster Recovery provides RPO of seconds and RTO of minutes cost-effectively |
| 540 | C | RDS Multi-AZ cluster deployment provides HA and dedicated reader instances for reporting |
| 541 | A, C, E | Lambda + DynamoDB + Cognito User Pool + AWS Amplify for cost-effective serverless solution |
| 542 | B | CloudFront signed URLs provide secure, time-limited access to premium content |
| 543 | A, E | Turn on discount sharing from management account + create organization with existing account |
| 544 | A | Canary release deployment allows gradual rollout with minimal customer impact |
| 545 | B | Route 53 active-passive failover with health checks provides automatic failover to S3 error page |
| 546 | D | AWS Storage Gateway with VTL interface replaces physical tapes with virtual ones |
| 547 | A | Kinesis Data Firehose provides managed streaming data delivery to S3 |
| 548 | B | AWS Organizations with SCPs provides centralized service control with minimal overhead |

### Questions 549-585

| Question | Correct Answer | Explanation |
|----------|---------------|-------------|
| 549 | B | NAT Gateway in public subnet allows private subnet resources to access internet securely |
| 550 | B, D | Lambda execution role needs KMS permissions, and role must be allowed in KMS key policy |
| 551 | A | S3 Standard → S3 Glacier after 7 days meets 6-hour retrieval requirement cost-effectively |
| 552 | B | Compute Savings Plan provides flexibility to change instance families every 2-3 months |
| 553 | A | Amazon Macie in each region provides automated PII discovery with minimal overhead |
| 554 | C | Memory optimized instances for both application and database due to high memory utilization |
| 555 | A | Interface VPC endpoint in private subnets with proper security groups ensures secure connectivity |
| 556 | B | IAM role with instance profile provides secure access without exposing credentials |
| 557 | A | Amazon Athena for parallel processing + AWS Glue for data enrichment from Redshift |
| 558 | C | VPC Peering is most cost-effective for same-region, same-account VPC connectivity |
| 559 | B, E | Select user-defined tags in billing console and activate from management account |
| 560 | A | AWS Control Tower account drift notifications provide automated OU hierarchy monitoring |
| 561 | A | DynamoDB Accelerator (DAX) provides microsecond latency with minimal operational overhead |
| 562 | A, B | Gateway endpoint for DynamoDB + route table entry enables private connectivity |
| 563 | B | EKS Connector allows centralized management of both EKS and on-premises Kubernetes clusters |
| 564 | B | RDS with KMS client-side encryption protects data even from database administrators |
| 565 | C | AWS DMS to Aurora + Auto Scaling provides MySQL compatibility with automatic scaling |
| 566 | B | Amazon EFS provides shared, concurrent file system access across multiple instances |
| 567 | A | API Gateway + Lambda + DynamoDB provides fully managed serverless solution |
| 568 | A | S3 for petabyte storage + CloudFront for global caching of engineering drawings |
| 569 | A | CloudWatch metrics in AWS/Events namespace show EventBridge rule execution status |
| 570 | B | Auto Scaling scheduled actions automatically scale based on predictable patterns |
| 571 | A | Third-party CA certificates must be created locally and imported into ACM |
| 572 | C | Aurora Serverless v2 provides MySQL compatibility with automatic scaling capabilities |
| 573 | D | Lambda SnapStart reduces Java cold start times most cost-effectively |
| 574 | A | Aurora Serverless v2 automatically scales down when not in use, optimizing costs |
| 575 | C | RDS Multi-AZ cluster deployment provides HA and read scaling for PostgreSQL |
| 576 | D | Edge-optimized endpoint uses CloudFront to reduce latency for distributed users |
| 577 | C | ACM with DNS validation provides automated certificate creation and renewal |
| 578 | A | DynamoDB Accelerator (DAX) provides microsecond response times with minimal overhead |
| 579 | A | Instance Scheduler on AWS automatically starts/stops RDS based on schedules |
| 580 | D | EBS GP3 provides cost-effective performance for lift-and-shift applications |
| 581 | B | Four instances across two AZs ensures at least two instances remain available during AZ failure |
| 582 | A | Geolocation routing policy directs users to nearest infrastructure based on location |
| 583 | C | Snowball with Tape Gateway handles large data migration most cost-effectively |
| 584 | A | Spread placement group ensures instances run on different underlying hardware |
| 585 | D | Capacity Reservations guarantee EC2 capacity availability in disaster recovery region |

## Study Tips

- Focus on understanding the scenario requirements (security, cost-optimization, performance, operational efficiency)
- Pay attention to keywords like "MOST secure," "LEAST operational overhead," "cost-effective"
- Consider AWS Well-Architected Framework principles
- Practice identifying the best service for each use case
- Review AWS service integrations and limitations
- **Use the answer explanations to understand the reasoning behind each correct answer**
- **Practice questions multiple times and review incorrect answers thoroughly**

---

### Question 549
**Scenario:** A company has created a multi-tier application for its ecommerce website. The website uses an Application Load Balancer that resides in the public subnets, a web tier in the public subnets, and a MySQL cluster hosted on Amazon EC2 instances in the private subnets. The MySQL database needs to retrieve product catalog and pricing information that is hosted on the internet by a third-party provider. A solutions architect must devise a strategy that maximizes security without increasing operational overhead.

**What should the solutions architect do to meet these requirements?**

A) Deploy a NAT instance in the VPC. Route all the internet-based traffic through the NAT instance.

B) Deploy a NAT gateway in the public subnets. Modify the private subnet route table to direct all internet-bound traffic to the NAT gateway.

C) Configure an internet gateway and attach it to the VPC. Modify the private subnet route table to direct internet-bound traffic to the internet gateway.

D) Configure a virtual private gateway and attach it to the VPC. Modify the private subnet route table to direct internet-bound traffic to the virtual private gateway.

---

### Question 550
**Scenario:** A company is using AWS Key Management Service (AWS KMS) keys to encrypt AWS Lambda environment variables. A solutions architect needs to ensure that the required permissions are in place to decrypt and use the environment variables.

**Which steps must the solutions architect take to implement the correct permissions? (Choose two.)**

A) Add AWS KMS permissions in the Lambda resource policy.

B) Add AWS KMS permissions in the Lambda execution role.

C) Add AWS KMS permissions in the Lambda function policy.

D) Allow the Lambda execution role in the AWS KMS key policy.

E) Allow the Lambda resource policy in the AWS KMS key policy.

---

### Question 551
**Scenario:** A company has a financial application that produces reports. The reports average 50 KB in size and are stored in Amazon S3. The reports are frequently accessed during the first week after production and must be stored for several years. The reports must be retrievable within 6 hours.

**Which solution meets these requirements MOST cost-effectively?**

A) Use S3 Standard. Use an S3 Lifecycle rule to transition the reports to S3 Glacier after 7 days.

B) Use S3 Standard. Use an S3 Lifecycle rule to transition the reports to S3 Standard-Infrequent Access (S3 Standard-IA) after 7 days.

C) Use S3 Intelligent-Tiering. Configure S3 Intelligent-Tiering to transition the reports to S3 Standard-Infrequent Access (S3 Standard-IA) and S3 Glacier.

D) Use S3 Standard. Use an S3 Lifecycle rule to transition the reports to S3 Glacier Deep Archive after 7 days.

---

### Question 552
**Scenario:** A company needs to optimize the cost of its Amazon EC2 instances. The company also needs to change the type and family of its EC2 instances every 2-3 months.

**What should the company do to meet these requirements?**

A) Purchase Partial Upfront Reserved Instances for a 3-year term.

B) Purchase a No Upfront Compute Savings Plan for a 1-year term.

C) Purchase All Upfront Reserved Instances for a 1-year term.

D) Purchase an All Upfront EC2 Instance Savings Plan for a 1-year term.

---

### Question 553
**Scenario:** A solutions architect needs to review a company's Amazon S3 buckets to discover personally identifiable information (PII). The company stores the PII data in the us-east-1 Region and us-west-2 Region.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Configure Amazon Macie in each Region. Create a job to analyze the data that is in Amazon S3.

B) Configure AWS Security Hub for all Regions. Create an AWS Config rule to analyze the data that is in Amazon S3.

C) Configure Amazon Inspector to analyze the data that is in Amazon S3.

D) Configure Amazon GuardDuty to analyze the data that is in Amazon S3.

---

### Question 554
**Scenario:** A company's SAP application has a backend SQL Server database in an on-premises environment. The company wants to migrate its on-premises application and database server to AWS. The company needs an instance type that meets the high demands of its SAP database. On-premises performance data shows that both the SAP application and the database have high memory utilization.

**Which solution will meet these requirements?**

A) Use the compute optimized instance family for the application. Use the memory optimized instance family for the database.

B) Use the storage optimized instance family for both the application and the database.

C) Use the memory optimized instance family for both the application and the database.

D) Use the high performance computing (HPC) optimized instance family for the application. Use the memory optimized instance family for the database.

---

### Question 555
**Scenario:** A company runs an application in a VPC with public and private subnets. The VPC extends across multiple Availability Zones. The application runs on Amazon EC2 instances in private subnets. The application uses an Amazon Simple Queue Service (Amazon SQS) queue. A solutions architect needs to design a secure solution to establish a connection between the EC2 instances and the SQS queue.

**Which solution will meet these requirements?**

A) Implement an interface VPC endpoint for Amazon SQS. Configure the endpoint to use the private subnets. Add to the endpoint a security group that has an inbound access rule that allows traffic from the EC2 instances that are in the private subnets.

B) Implement an interface VPC endpoint for Amazon SQS. Configure the endpoint to use the public subnets. Attach to the interface endpoint a VPC endpoint policy that allows access from the EC2 instances that are in the private subnets.

C) Implement an interface VPC endpoint for Amazon SQS. Configure the endpoint to use the public subnets. Attach an Amazon SQS access policy to the interface VPC endpoint that allows requests from only a specified VPC endpoint.

D) Implement a gateway endpoint for Amazon SQS. Add a NAT gateway to the private subnets. Attach an IAM role to the EC2 instances that allows access to the SQS queue.

---

### Question 556
**Scenario:** A solutions architect is using an AWS CloudFormation template to deploy a three-tier web application. The web application consists of a web tier and an application tier that stores and retrieves user data in Amazon DynamoDB tables. The web and application tiers are hosted on Amazon EC2 instances, and the database tier is not publicly accessible. The application EC2 instances need to access the DynamoDB tables without exposing API credentials in the template.

**What should the solutions architect do to meet these requirements?**

A) Create an IAM role to read the DynamoDB tables. Associate the role with the application instances by referencing an instance profile.

B) Create an IAM role that has the required permissions to read and write from the DynamoDB tables. Add the role to the EC2 instance profile, and associate the instance profile with the application instances.

C) Use the parameter section in the AWS CloudFormation template to have the user input access and secret keys from an already-created IAM user that has the required permissions to read and write from the DynamoDB tables.

D) Create an IAM user in the AWS CloudFormation template that has the required permissions to read and write from the DynamoDB tables. Use the GetAtt function to retrieve the access and secret keys, and pass them to the application instances through the user data.

---

### Question 557
**Scenario:** A solutions architect manages an analytics application. The application stores large amounts of semistructured data in an Amazon S3 bucket. The solutions architect wants to use parallel data processing to process the data more quickly. The solutions architect also wants to use information that is stored in an Amazon Redshift database to enrich the data.

**Which solution will meet these requirements?**

A) Use Amazon Athena to process the S3 data. Use AWS Glue with the Amazon Redshift data to enrich the S3 data.

B) Use Amazon EMR to process the S3 data. Use Amazon EMR with the Amazon Redshift data to enrich the S3 data.

C) Use Amazon EMR to process the S3 data. Use Amazon Kinesis Data Streams to move the S3 data into Amazon Redshift so that the data can be enriched.

D) Use AWS Glue to process the S3 data. Use AWS Lake Formation with the Amazon Redshift data to enrich the S3 data.

---

### Question 558
**Scenario:** A company has two VPCs that are located in the us-west-2 Region within the same AWS account. The company needs to allow network traffic between these VPCs. Approximately 500 GB of data transfer will occur between the VPCs each month.

**What is the MOST cost-effective solution to connect these VPCs?**

A) Implement AWS Transit Gateway to connect the VPCs. Update the route tables of each VPC to use the transit gateway for inter-VPC communication.

B) Implement an AWS Site-to-Site VPN tunnel between the VPCs. Update the route tables of each VPC to use the VPN tunnel for inter-VPC communication.

C) Set up a VPC peering connection between the VPCs. Update the route tables of each VPC to use the VPC peering connection for inter-VPC communication.

D) Set up a 1 GB AWS Direct Connect connection between the VPCs. Update the route tables of each VPC to use the Direct Connect connection for inter-VPC communication.

---

### Question 559
**Scenario:** A company hosts multiple applications on AWS for different product lines. The applications use different compute resources, including Amazon EC2 instances and Application Load Balancers. The applications run in different AWS accounts under the same organization in AWS Organizations across multiple AWS Regions. Teams for each product line have tagged each compute resource in the individual accounts. The company wants more details about the cost for each product line from the consolidated billing feature in Organizations.

**Which combination of steps will meet these requirements? (Choose two.)**

A) Select a specific AWS generated tag in the AWS Billing console.

B) Select a specific user-defined tag in the AWS Billing console.

C) Select a specific user-defined tag in the AWS Resource Groups console.

D) Activate the selected tag from each AWS account.

E) Activate the selected tag from the Organizations management account.

---

### Question 560
**Scenario:** A company's solutions architect is designing an AWS multi-account solution that uses AWS Organizations. The solutions architect has organized the company's accounts into organizational units (OUs). The solutions architect needs a solution that will identify any changes to the OU hierarchy. The solution also needs to notify the company's operations team of any changes.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Provision the AWS accounts by using AWS Control Tower. Use account drift notifications to identify the changes to the OU hierarchy.

B) Provision the AWS accounts by using AWS Control Tower. Use AWS Config aggregated rules to identify the changes to the OU hierarchy.

C) Use AWS Service Catalog to create accounts in Organizations. Use an AWS CloudTrail organization trail to identify the changes to the OU hierarchy.

D) Use AWS CloudFormation templates to create accounts in Organizations. Use the drift detection operation on a stack to identify the changes to the OU hierarchy.

---

### Question 561
**Scenario:** A company's website handles millions of requests each day, and the number of requests continues to increase. A solutions architect needs to improve the response time of the web application. The solutions architect determines that the application needs to decrease latency when retrieving product details from the Amazon DynamoDB table.

**Which solution will meet these requirements with the LEAST amount of operational overhead?**

A) Set up a DynamoDB Accelerator (DAX) cluster. Route all read requests through DAX.

B) Set up Amazon ElastiCache for Redis between the DynamoDB table and the web application. Route all read requests through Redis.

C) Set up Amazon ElastiCache for Memcached between the DynamoDB table and the web application. Route all read requests through Memcached.

D) Set up Amazon DynamoDB Streams on the table, and have AWS Lambda read from the table and populate Amazon ElastiCache. Route all read requests through ElastiCache.

---

### Question 562
**Scenario:** A solutions architect needs to ensure that API calls to Amazon DynamoDB from Amazon EC2 instances in a VPC do not travel across the internet.

**Which combination of steps should the solutions architect take to meet this requirement? (Choose two.)**

A) Create a route table entry for the endpoint.

B) Create a gateway endpoint for DynamoDB.

C) Create an interface endpoint for Amazon EC2.

D) Create an elastic network interface for the endpoint in each of the subnets of the VPC.

E) Create a security group entry in the endpoint's security group to provide access.

---

### Question 563
**Scenario:** A company runs its applications on both Amazon Elastic Kubernetes Service (Amazon EKS) clusters and on-premises Kubernetes clusters. The company wants to view all clusters and workloads from a central location.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Use Amazon CloudWatch Container Insights to collect and group the cluster information.

B) Use Amazon EKS Connector to register and connect all Kubernetes clusters.

C) Use AWS Systems Manager to collect and view the cluster information.

D) Use Amazon EKS Anywhere as the primary cluster to view the other clusters with native Kubernetes commands.

---

### Question 564
**Scenario:** A company is building an ecommerce application and needs to store sensitive customer information. The company needs to give customers the ability to complete purchase transactions on the website. The company also needs to ensure that sensitive customer data is protected, even from database administrators.

**Which solution meets these requirements?**

A) Store sensitive data in an Amazon Elastic Block Store (Amazon EBS) volume. Use EBS encryption to encrypt the data. Use an IAM instance role to restrict access.

B) Store sensitive data in Amazon RDS for MySQL. Use AWS Key Management Service (AWS KMS) client-side encryption to encrypt the data.

C) Store sensitive data in Amazon S3. Use AWS Key Management Service (AWS KMS) server-side encryption to encrypt the data. Use S3 bucket policies to restrict access.

D) Store sensitive data in Amazon FSx for Windows Server. Mount the file share on application servers. Use Windows file permissions to restrict access.

---

### Question 565
**Scenario:** A company has an on-premises MySQL database that handles transactional data. The company is migrating the database to the AWS Cloud. The migrated database must maintain compatibility with the company's applications that use the database. The migrated database also must scale automatically during periods of increased demand.

**Which migration solution will meet these requirements?**

A) Use native MySQL tools to migrate the database to Amazon RDS for MySQL. Configure elastic storage scaling.

B) Migrate the database to Amazon Redshift by using the mysqldump utility. Turn on Auto Scaling for the Amazon Redshift cluster.

C) Use AWS Database Migration Service (AWS DMS) to migrate the database to Amazon Aurora. Turn on Aurora Auto Scaling.

D) Use AWS Database Migration Service (AWS DMS) to migrate the database to Amazon DynamoDB. Configure an Auto Scaling policy.

---

### Question 566
**Scenario:** A company runs multiple Amazon EC2 Linux instances in a VPC across two Availability Zones. The instances host applications that use a hierarchical directory structure. The applications need to read and write rapidly and concurrently to shared storage.

**What should a solutions architect do to meet these requirements?**

A) Create an Amazon S3 bucket. Allow access from all the EC2 instances in the VPC.

B) Create an Amazon Elastic File System (Amazon EFS) file system. Mount the EFS file system from each EC2 instance.

C) Create a file system on a Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volume. Attach the EBS volume to all the EC2 instances.

D) Create file systems on Amazon Elastic Block Store (Amazon EBS) volumes that are attached to each EC2 instance. Synchronize the EBS volumes across the different EC2 instances.

---

### Question 567
**Scenario:** A solutions architect is designing a workload that will store hourly energy consumption by business tenants in a building. The sensors will feed a database through HTTP requests that will add up usage for each tenant. The solutions architect must use managed services when possible. The workload will receive more features in the future as the solutions architect adds independent components.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Use Amazon API Gateway with AWS Lambda functions to receive the data from the sensors, process the data, and store the data in an Amazon DynamoDB table.

B) Use an Elastic Load Balancer that is supported by an Auto Scaling group of Amazon EC2 instances to receive and process the data from the sensors. Use an Amazon S3 bucket to store the processed data.

C) Use Amazon API Gateway with AWS Lambda functions to receive the data from the sensors, process the data, and store the data in a Microsoft SQL Server Express database on an Amazon EC2 instance.

D) Use an Elastic Load Balancer that is supported by an Auto Scaling group of Amazon EC2 instances to receive and process the data from the sensors. Use an Amazon Elastic File System (Amazon EFS) shared file system to store the processed data.

---

### Question 568
**Scenario:** A solutions architect is designing the storage architecture for a new web application used for storing and viewing engineering drawings. All application components will be deployed on the AWS infrastructure. The application design must support caching to minimize the amount of time that users wait for the engineering drawings to load. The application must be able to store petabytes of data.

**Which combination of storage and caching should the solutions architect use?**

A) Amazon S3 with Amazon CloudFront

B) Amazon S3 Glacier with Amazon ElastiCache

C) Amazon Elastic Block Store (Amazon EBS) volumes with Amazon CloudFront

D) AWS Storage Gateway with Amazon ElastiCache

---

### Question 569
**Scenario:** An Amazon EventBridge rule targets a third-party API. The third-party API has not received any incoming traffic. A solutions architect needs to determine whether the rule conditions are being met and if the rule's target is being invoked.

**Which solution will meet these requirements?**

A) Check for metrics in Amazon CloudWatch in the namespace for AWS/Events.

B) Review events in the Amazon Simple Queue Service (Amazon SQS) dead-letter queue.

C) Check for the events in Amazon CloudWatch Logs.

D) Check the trails in AWS CloudTrail for the EventBridge events.

---

### Question 570
**Scenario:** A company has a large workload that runs every Friday evening. The workload runs on Amazon EC2 instances that are in two Availability Zones in the us-east-1 Region. Normally, the company must run no more than two instances at all times. However, the company wants to scale up to six instances each Friday to handle a regularly repeating increased workload.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Create a reminder in Amazon EventBridge to scale the instances.

B) Create an Auto Scaling group that has a scheduled action.

C) Create an Auto Scaling group that uses manual scaling.

D) Create an Auto Scaling group that uses automatic scaling.

---

### Question 571
**Scenario:** A company is creating a REST API. The company has strict requirements for the use of TLS. The company requires TLSv1.3 on the API endpoints. The company also requires a specific public third-party certificate authority (CA) to sign the TLS certificate.

**Which solution will meet these requirements?**

A) Use a local machine to create a certificate that is signed by the third-party CA. Import the certificate into AWS Certificate Manager (ACM). Create an HTTP API in Amazon API Gateway with a custom domain. Configure the custom domain to use the certificate.

B) Create a certificate in AWS Certificate Manager (ACM) that is signed by the third-party CA. Create an HTTP API in Amazon API Gateway with a custom domain. Configure the custom domain to use the certificate.

C) Use AWS Certificate Manager (ACM) to create a certificate that is signed by the third-party CA. Import the certificate into AWS Certificate Manager (ACM). Create an AWS Lambda function with a Lambda function URL. Configure the Lambda function URL to use the certificate.

D) Create a certificate in AWS Certificate Manager (ACM) that is signed by the third-party CA. Create an AWS Lambda function with a Lambda function URL. Configure the Lambda function URL to use the certificate.

---

### Question 572
**Scenario:** A company runs an application on AWS. The application receives inconsistent amounts of usage. The application uses AWS Direct Connect to connect to an on-premises MySQL-compatible database. The on-premises database consistently uses a minimum of 2 GiB of memory. The company wants to migrate the on-premises database to a managed AWS service. The company wants to use auto scaling capabilities to manage unexpected workload increases.

**Which solution will meet these requirements with the LEAST administrative overhead?**

A) Provision an Amazon DynamoDB database with default read and write capacity settings.

B) Provision an Amazon Aurora database with a minimum capacity of 1 Aurora capacity unit (ACU).

C) Provision an Amazon Aurora Serverless v2 database with a minimum capacity of 1 Aurora capacity unit (ACU).

D) Provision an Amazon RDS for MySQL database with 2 GiB of memory.

---

### Question 573
**Scenario:** A company wants to use an event-driven programming model with AWS Lambda. The company wants to reduce startup latency for Lambda functions that run on Java 11. The company does not have strict latency requirements for the applications. The company wants to reduce cold starts and outlier latencies when a function scales up.

**Which solution will meet these requirements MOST cost-effectively?**

A) Configure Lambda provisioned concurrency.

B) Increase the timeout of the Lambda functions.

C) Increase the memory of the Lambda functions.

D) Configure Lambda SnapStart.

---

### Question 574
**Scenario:** A financial services company launched a new application that uses an Amazon RDS for MySQL database. The company uses the application to track stock market trends. The company needs to operate the application for only 2 hours at the end of each week. The company needs to optimize the cost of running the database.

**Which solution will meet these requirements MOST cost-effectively?**

A) Migrate the existing RDS for MySQL database to an Aurora Serverless v2 MySQL database cluster.

B) Migrate the existing RDS for MySQL database to an Aurora MySQL database cluster.

C) Migrate the existing RDS for MySQL database to an Amazon EC2 instance that runs MySQL. Purchase an instance reservation for the EC2 instance.

D) Migrate the existing RDS for MySQL database to an Amazon Elastic Container Service (Amazon ECS) cluster that uses MySQL container images to run tasks.

---

### Question 575
**Scenario:** A company deploys its applications on Amazon Elastic Kubernetes Service (Amazon EKS) behind an Application Load Balancer in an AWS Region. The application needs to store data in a PostgreSQL database engine. The company wants the data in the database to be highly available. The company also needs increased capacity for read workloads.

**Which solution will meet these requirements with the MOST operational efficiency?**

A) Create an Amazon DynamoDB database table configured with global tables.

B) Create an Amazon RDS database with Multi-AZ deployments.

C) Create an Amazon RDS database with Multi-AZ DB cluster deployment.

D) Create an Amazon RDS database configured with cross-Region read replicas.

---

### Question 576
**Scenario:** A company is building a RESTful serverless web application on AWS by using Amazon API Gateway and AWS Lambda. The users of this web application will be geographically distributed, and the company wants to reduce the latency of API requests to these users.

**Which type of endpoint should a solutions architect use to meet these requirements?**

A) Private endpoint

B) Regional endpoint

C) Interface VPC endpoint

D) Edge-optimized endpoint

---

### Question 577
**Scenario:** A company uses an Amazon CloudFront distribution to serve content pages for its website. The company needs to ensure that clients use a TLS certificate when accessing the company's website. The company wants to automate the creation and renewal of the TLS certificates.

**Which solution will meet these requirements with the MOST operational efficiency?**

A) Use a CloudFront security policy to create a certificate.

B) Use a CloudFront origin access control (OAC) to create a certificate.

C) Use AWS Certificate Manager (ACM) to create a certificate. Use DNS validation for the domain.

D) Use AWS Certificate Manager (ACM) to create a certificate. Use email validation for the domain.

---

### Question 578
**Scenario:** A company deployed a serverless application that uses Amazon DynamoDB as a database layer. The application has experienced a large increase in users. The company wants to improve database response time from milliseconds to microseconds and to cache requests to the database.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Use DynamoDB Accelerator (DAX).

B) Migrate the database to Amazon Redshift.

C) Migrate the database to Amazon RDS.

D) Use Amazon ElastiCache for Redis.

---

### Question 579
**Scenario:** A company runs an application that uses Amazon RDS for PostgreSQL. The application receives traffic only on weekdays during business hours. The company wants to optimize costs and reduce operational overhead based on this usage.

**Which solution will meet these requirements?**

A) Use the Instance Scheduler on AWS to configure start and stop schedules.

B) Turn off automatic backups. Create weekly manual snapshots of the database.

C) Create a custom AWS Lambda function to start and stop the database based on minimum CPU utilization.

D) Purchase All Upfront reserved DB instances.

---

### Question 580
**Scenario:** A company uses locally attached storage to run a latency-sensitive application on premises. The company is using a lift and shift method to move the application to the AWS Cloud. The company does not want to change the application architecture.

**Which solution will meet these requirements MOST cost-effectively?**

A) Configure an Auto Scaling group with an Amazon EC2 instance. Use an Amazon FSx for Lustre file system to run the application.

B) Host the application on an Amazon EC2 instance. Use an Amazon Elastic Block Store (Amazon EBS) GP2 volume to run the application.

C) Configure an Auto Scaling group with an Amazon EC2 instance. Use an Amazon FSx for OpenZFS file system to run the application.

D) Host the application on an Amazon EC2 instance. Use an Amazon Elastic Block Store (Amazon EBS) GP3 volume to run the application.

---

### Question 581
**Scenario:** A company runs a stateful production application on Amazon EC2 instances. The application requires at least two EC2 instances to always be running. A solutions architect needs to design a highly available and fault-tolerant architecture for the application. The solutions architect creates an Auto Scaling group of EC2 instances.

**Which set of additional steps should the solutions architect take to meet these requirements?**

A) Set the Auto Scaling group's minimum capacity to two. Deploy one On-Demand Instance in one Availability Zone and one On-Demand Instance in a second Availability Zone.

B) Set the Auto Scaling group's minimum capacity to four. Deploy two On-Demand Instances in one Availability Zone and two On-Demand Instances in a second Availability Zone.

C) Set the Auto Scaling group's minimum capacity to two. Deploy four Spot Instances in one Availability Zone.

D) Set the Auto Scaling group's minimum capacity to four. Deploy two On-Demand Instances in one Availability Zone and two Spot Instances in a second Availability Zone.

---

### Question 582
**Scenario:** An ecommerce company uses Amazon Route 53 as its DNS provider. The company hosts its website on premises and in the AWS Cloud. The company's on-premises data center is near the us-west-1 Region. The company uses the eu-central-1 Region to host the website. The company wants to minimize load time for the website as much as possible.

**Which solution will meet these requirements?**

A) Set up a geolocation routing policy. Send the traffic that is near us-west-1 to the on-premises data center. Send the traffic that is near eu-central-1 to eu-central-1.

B) Set up a simple routing policy that routes all traffic that is near eu-central-1 to eu-central-1 and routes all traffic that is near the on-premises datacenter to the on-premises data center.

C) Set up a latency routing policy. Associate the policy with us-west-1.

D) Set up a weighted routing policy. Split the traffic evenly between eu-central-1 and the on-premises data center.

---

### Question 583
**Scenario:** A company has 5 PB of archived data on physical tapes. The company needs to preserve the data on the tapes for another 10 years for compliance purposes. The company wants to migrate to AWS in the next 6 months. The data center that stores the tapes has a 1 Gbps uplink internet connectivity.

**Which solution will meet these requirements MOST cost-effectively?**

A) Read the data from the tapes on premises. Stage the data in a local NFS storage. Use AWS DataSync to migrate the data to Amazon S3 Glacier Flexible Retrieval.

B) Use an on-premises backup application to read the data from the tapes and to write directly to Amazon S3 Glacier Deep Archive.

C) Order multiple AWS Snowball devices that have Tape Gateway. Copy the physical tapes to virtual tapes in Snowball. Ship the Snowball devices to AWS. Create a lifecycle policy to move the tapes to Amazon S3 Glacier Deep Archive.

D) Configure an on-premises Tape Gateway. Create virtual tapes in the AWS Cloud. Use backup software to copy the physical tape to the virtual tape.

---

### Question 584
**Scenario:** A company is deploying an application that processes large quantities of data in parallel. The company plans to use Amazon EC2 instances for the workload. The network architecture must be configurable to prevent groups of nodes from sharing the same underlying hardware.

**Which networking solution meets these requirements?**

A) Run the EC2 instances in a spread placement group.

B) Group the EC2 instances in separate accounts.

C) Configure the EC2 instances with dedicated tenancy.

D) Configure the EC2 instances with shared tenancy.

---

### Question 585
**Scenario:** A solutions architect is designing a disaster recovery (DR) strategy to provide Amazon EC2 capacity in a failover AWS Region. Business requirements state that the DR strategy must meet capacity in the failover Region.

**Which solution will meet these requirements?**

A) Purchase On-Demand Instances in the failover Region.

B) Purchase an EC2 Savings Plan in the failover Region.

C) Purchase regional Reserved Instances in the failover Region.

D) Purchase a Capacity Reservation in the failover Region.

---

## Study Tips

- Focus on understanding the scenario requirements (security, cost-optimization, performance, operational efficiency)
- Pay attention to keywords like "MOST secure," "LEAST operational overhead," "cost-effective"
- Consider AWS Well-Architected Framework principles
- Practice identifying the best service for each use case
- Review AWS service integrations and limitations

## Contributing

Feel free to add more questions or improve existing ones by submitting a pull request.

## Disclaimer

These questions are for educational purposes only and may not reflect the exact format or content of the actual AWS certification exam.

# AWS Solutions Architect Practice Questions - Complete Answer Key

## Questions 521-585 Answer Key

| Question | Answer | Explanation |
|----------|--------|-------------|
| 521 | C | Cross-account IAM roles with assume role is the most secure approach for cross-account access. Avoids long-term credentials and provides fine-grained access control. |
| 522 | B, C | Kubernetes Metrics Server enables horizontal pod autoscaling (HPA), while Cluster Autoscaler manages node scaling with minimal operational overhead. |
| 523 | A | AWS AppSync pipeline resolvers provide efficient data aggregation from multiple DynamoDB tables without impacting baseline performance. |
| 524 | C | Amazon Athena can directly query CloudTrail logs stored in S3 with minimal setup and SQL-based queries for Access Denied errors. |
| 525 | A | AWS Cost Explorer API provides programmatic access to current cost data and 12-month forecasting capabilities with pagination support. |
| 526 | D | Amazon RDS Proxy provides connection pooling and significantly reduces failover downtime during scaling exercises. |
| 527 | D | Aurora Global Database with multi-region deployment provides the highest fault tolerance with automatic failover capabilities. |
| 528 | D | AWS Transfer Family + S3 + Lambda provides serverless, event-driven file processing that scales automatically and processes files immediately upon arrival. |
| 529 | B | Amazon RDS with encryption at rest provides managed database security with minimal operational overhead compared to self-managed EC2 solutions. |
| 530 | C | AWS Global Accelerator optimizes TCP/UDP traffic routing globally and reduces latency for gaming applications better than CloudFront (which doesn't support TCP/UDP). |
| 531 | A | Lambda function URLs provide the simplest way to expose Lambda functions to external services without additional infrastructure. |
| 532 | A, D, F | Wildcard domain in Route 53 + ACM certificate in same region + API Gateway custom domain provides secure, scalable solution for individual customer URLs. |
| 533 | A | Amazon Macie detects PII automatically and integrates with EventBridge to send SNS notifications to security teams. |
| 534 | C | S3 Standard → S3 Glacier Flexible Retrieval after 30 days, delete after 90 days meets availability requirements most cost-effectively. |
| 535 | B | EKS KMS secrets encryption specifically encrypts secrets in the Kubernetes etcd key-value store. |
| 536 | D | Multi-AZ cluster deployment with readable standby instances provides high availability and dedicated read capacity for data scientists. |
| 537 | A | RDS Multi-AZ + ElastiCache Redis (supports HA) + Auto Scaling provides best combination of scalability, session management, and high availability. |
| 538 | A | CloudFront geographic restrictions with allow list controls content access by specific countries with custom error messages. |
| 539 | C | AWS Elastic Disaster Recovery provides RPO of seconds and RTO of minutes cost-effectively for SQL Server workloads. |
| 540 | C | RDS Multi-AZ cluster deployment provides high availability and dedicated reader instances for offloading reporting workloads. |
| 541 | A, C, E | Lambda + DynamoDB + Cognito User Pool + AWS Amplify provides cost-effective serverless solution for unpredictable traffic patterns. |
| 542 | B | CloudFront signed URLs provide secure, time-limited access to premium content with granular control over access permissions. |
| 543 | A, E | Turn on discount sharing from management account + create organization with existing Savings Plan account enables sharing across accounts. |
| 544 | A | Canary release deployment allows gradual API rollout with traffic splitting and easy rollback, minimizing customer impact. |
| 545 | B | Route 53 active-passive failover with health checks provides automatic failover to S3-hosted error page when ALB becomes unhealthy. |
| 546 | D | AWS Storage Gateway with VTL (Virtual Tape Library) interface replaces physical tapes while preserving existing backup workflows. |
| 547 | A | Kinesis Data Firehose provides fully managed streaming data delivery to S3 with automatic scaling and minimal operational overhead. |
| 548 | B | AWS Organizations with Service Control Policies (SCPs) provides centralized service control across accounts with minimal operational overhead. |
| 549 | B | NAT Gateway in public subnet allows private subnet resources to access internet securely while remaining private. |
| 550 | B, D | Lambda execution role needs KMS decrypt permissions, and the role must be explicitly allowed in the KMS key policy. |
| 551 | A | S3 Standard → S3 Glacier after 7 days meets 6-hour retrieval requirement cost-effectively (Glacier retrieval: 1-5 minutes to 12 hours). |
| 552 | B | Compute Savings Plan provides flexibility to change instance families every 2-3 months while maintaining cost optimization. |
| 553 | A | Amazon Macie in each region provides automated PII discovery and classification with minimal operational overhead. |
| 554 | C | Memory optimized instances (R5, X1) for both application and database due to high memory utilization requirements from SAP workloads. |
| 555 | A | Interface VPC endpoint in private subnets with proper security groups ensures secure SQS connectivity without internet traversal. |
| 556 | B | IAM role with instance profile provides secure access to DynamoDB without exposing credentials in CloudFormation templates. |
| 557 | A | Amazon Athena enables parallel S3 data processing, while AWS Glue can enrich data using Redshift information efficiently. |
| 558 | C | VPC Peering is most cost-effective for same-region, same-account VPC connectivity with 500GB monthly transfer. |
| 559 | B, E | Select user-defined tags in billing console and activate from Organizations management account enables cost allocation by product line. |
| 560 | A | AWS Control Tower account drift notifications provide automated monitoring of OU hierarchy changes with built-in notifications. |
| 561 | A | DynamoDB Accelerator (DAX) provides microsecond latency caching with minimal operational overhead and native DynamoDB integration. |
| 562 | A, B | Gateway endpoint for DynamoDB + route table entry enables private connectivity without internet traversal or additional NICs. |
| 563 | B | EKS Connector allows centralized management and viewing of both EKS and on-premises Kubernetes clusters from a single console. |
| 564 | B | RDS with KMS client-side encryption protects data even from database administrators who have database access but not encryption keys. |
| 565 | C | AWS DMS to Aurora + Auto Scaling provides MySQL compatibility with automatic scaling for transactional workloads. |
| 566 | B | Amazon EFS provides shared, concurrent POSIX-compliant file system access across multiple EC2 instances with high performance. |
| 567 | A | API Gateway + Lambda + DynamoDB provides fully managed serverless solution with automatic scaling and modular architecture. |
| 568 | A | S3 for petabyte-scale storage + CloudFront for global caching and fast delivery of engineering drawings to distributed users. |
| 569 | A | CloudWatch metrics in AWS/Events namespace show EventBridge rule execution metrics including invocation success/failure. |
| 570 | B | Auto Scaling scheduled actions automatically scale instances based on predictable time-based patterns with minimal overhead. |
| 571 | A | Third-party CA certificates must be created locally/externally and imported into ACM, then configured with API Gateway custom domain. |
| 572 | C | Aurora Serverless v2 provides MySQL compatibility with automatic scaling and 1 ACU minimum meets memory requirements efficiently. |
| 573 | D | Lambda SnapStart reduces Java cold start times most cost-effectively by pre-initializing execution environments. |
| 574 | A | Aurora Serverless v2 automatically scales to zero when not in use, making it ideal for 2-hour weekly workloads. |
| 575 | C | RDS Multi-AZ cluster deployment provides high availability and dedicated read replicas for PostgreSQL workloads. |
| 576 | D | Edge-optimized endpoint uses CloudFront edge locations to reduce latency for geographically distributed users. |
| 577 | C | ACM with DNS validation provides automated certificate creation, deployment, and renewal with operational efficiency. |
| 578 | A | DynamoDB Accelerator (DAX) provides microsecond response times with minimal operational overhead and seamless DynamoDB integration. |
| 579 | A | Instance Scheduler on AWS automatically starts/stops RDS instances based on schedules, optimizing costs for business-hours-only usage. |
| 580 | D | EBS GP3 provides cost-effective baseline performance suitable for lift-and-shift applications requiring local storage. |
| 581 | B | Four instances across two AZs ensures at least two instances remain available during single AZ failure, meeting HA requirements. |
| 582 | A | Geolocation routing policy directs users to nearest infrastructure based on geographic location, minimizing load time. |
| 583 | C | Snowball with Tape Gateway handles large data migration most cost-effectively given 1 Gbps limitation and 5 PB volume. |
| 584 | A | Spread placement group ensures instances run on different underlying hardware across distinct racks/hosts. |
| 585 | D | Capacity Reservations guarantee EC2 capacity availability in disaster recovery region when needed for failover. |

## Key Study Areas

### Security & IAM
- Cross-account role assumption (Q521)
- KMS encryption and permissions (Q535, Q550, Q564)
- VPC endpoints and private connectivity (Q555, Q562)
- CloudFront access controls and signed URLs (Q538, Q542)

### High Availability & Disaster Recovery
- Multi-AZ deployments and Aurora Global Database (Q527, Q536, Q540, Q575)
- RDS Proxy for reduced failover times (Q526)
- Route 53 failover configurations (Q545)
- AWS Elastic Disaster Recovery (Q539)

### Cost Optimization
- Savings Plans vs Reserved Instances (Q543, Q552)
- S3 lifecycle policies and storage classes (Q534, Q551)
- Auto Scaling and serverless architectures (Q541, Q570, Q574)
- Aurora Serverless for variable workloads (Q572, Q574)

### Performance & Scalability
- DynamoDB performance optimization with DAX (Q561, Q578)
- EKS scaling with HPA and Cluster Autoscaler (Q522)
- Global Accelerator for gaming applications (Q530)
- Aurora cluster deployments (Q536, Q575)

### Serverless & Event-Driven Architecture
- Lambda optimization techniques (Q573)
- API Gateway configurations (Q531, Q544, Q576)
- Event-driven processing with S3 + Lambda (Q528)
- AppSync for data aggregation (Q523)

### Data Processing & Analytics
- Kinesis Data Firehose for streaming (Q547)
- Athena for log analysis (Q524, Q557)
- Macie for PII detection (Q533, Q553)

### Migration Strategies
- Database migration with DMS (Q565)
- Large data migration with Snowball (Q583)
- Storage Gateway for hybrid scenarios (Q546)

## Tips for Exam Success

1. **Identify Keywords**: Look for "MOST secure," "LEAST operational overhead," "cost-effective," "minimal changes"
2. **Well-Architected Framework**: Consider all five pillars when evaluating options
3. **Service Limitations**: Understand what each AWS service can and cannot do
4. **Regional Services**: Know which services are global vs regional
5. **Integration Patterns**: Understand how services work together
6. **Scaling Patterns**: Differentiate between horizontal, vertical, and automatic scaling approaches