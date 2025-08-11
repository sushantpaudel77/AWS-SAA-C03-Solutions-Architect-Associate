# AWS Solutions Architect Practice Questions

## Overview
This repository contains 30 practice questions (131-160) for AWS Solutions Architect certification exam preparation. These questions cover various AWS services and architectural patterns commonly tested in the certification exam.

## Question Categories
- **Storage & Content Delivery**: S3, CloudFront, Cross-Region Replication
- **Database Solutions**: RDS, Aurora, DynamoDB, Migration Services
- **Networking & Security**: VPC, PrivateLink, WAF, Security Groups
- **Compute & Auto Scaling**: EC2, Lambda, Auto Scaling Groups
- **Monitoring & Management**: CloudWatch, Organizations, Cost Optimization
- **Data Analytics**: Athena, QuickSight, Lake Formation

---

## Questions

### Question 131: S3 + CloudFront Security
**Scenario**: A company is developing a file-sharing application using S3 and CloudFront. Files should not be accessible through direct S3 URLs.

**Question**: What should a solutions architect do to meet these requirements?

**Options**:
1. Write individual policies for each S3 bucket to grant read permission for only CloudFront access
2. Create an IAM user. Grant the user read permission to objects in the S3 bucket. Assign the user to CloudFront
3. Write an S3 bucket policy that assigns the CloudFront distribution ID as the Principal and assigns the target S3 bucket as the Amazon Resource Name (ARN)
4. **Create an origin access identity (OAI). Assign the OAI to the CloudFront distribution. Configure the S3 bucket permissions so that only the OAI has read permission** ✅

---

### Question 132: Global Content Delivery
**Scenario**: A company's website provides downloadable historical performance reports globally with cost-effective scaling and fastest response time.

**Question**: Which combination should a solutions architect recommend?

**Options**:
1. **Amazon CloudFront and Amazon S3** ✅
2. AWS Lambda and Amazon DynamoDB
3. Application Load Balancer with Amazon EC2 Auto Scaling
4. Amazon Route 53 with internal Application Load Balancers

---

### Question 133: Oracle Database Migration
**Scenario**: Company wants to migrate Oracle database to AWS, upgrade to latest version, set up DR, minimize operational overhead, and maintain OS access.

**Question**: Which solution will meet these requirements?

**Options**:
1. Migrate to Amazon EC2 instance with database replication to different AWS Region
2. Migrate to Amazon RDS for Oracle with Cross-Region automated backups
3. **Migrate to Amazon RDS Custom for Oracle. Create a read replica in another AWS Region** ✅
4. Migrate to Amazon RDS for Oracle with standby database in another Availability Zone

---

### Question 134: Serverless Data Analytics
**Scenario**: Move application to serverless solution for SQL analysis of encrypted, replicated S3 data with least operational overhead.

**Question**: Which solution meets the requirements?

**Options**:
1. New S3 bucket + S3 CRR + SSE-KMS multi-Region keys + Amazon Athena
2. New S3 bucket + S3 CRR + SSE-KMS multi-Region keys + Amazon RDS
3. **Existing S3 bucket + S3 CRR + SSE-S3 + Amazon Athena** ✅
4. Existing S3 bucket + S3 CRR + SSE-S3 + Amazon RDS

---

### Question 135: Private Service Connectivity
**Scenario**: Company needs private connectivity to external provider's service, restricted to target service, initiated only from company's VPC.

**Question**: Which solution meets these requirements?

**Options**:
1. Create VPC peering connection and update route table
2. Provider creates virtual private gateway, use AWS PrivateLink
3. Create NAT gateway in public subnet, update route table
4. **Provider creates VPC endpoint for target service, use AWS PrivateLink** ✅

---

### Question 136: PostgreSQL Migration (Multi-select)
**Scenario**: Migrate on-premises PostgreSQL to Aurora PostgreSQL while keeping on-premises online and synchronized.

**Question**: Which combination of actions must be taken? (Choose two)

**Options**:
1. **Create an ongoing replication task** ✅
2. Create a database backup of the on-premises database
3. **Create an AWS Database Migration Service (AWS DMS) replication server** ✅
4. Convert schema using AWS Schema Conversion Tool (AWS SCT)
5. Create EventBridge rule to monitor database synchronization

---

### Question 137: AWS Organizations Notifications
**Scenario**: Company uses AWS Organizations, missed root user notification, wants to ensure future notifications reach account administrators.

**Question**: Which solution will meet these requirements?

**Options**:
1. Configure email server to forward root user emails to all users
2. **Configure root user email addresses as distribution lists, configure AWS account alternate contacts** ✅
3. Configure all root user messages to one administrator
4. Use same root user email for all accounts, configure alternate contacts

---

### Question 138: High Availability E-commerce Architecture
**Scenario**: E-commerce app uses RabbitMQ on single AZ EC2, needs highest availability with least operational overhead.

**Question**: What should a solutions architect do?

**Options**:
1. Migrate to Amazon MQ redundant pair + Multi-AZ Auto Scaling for app + Multi-AZ Auto Scaling for PostgreSQL
2. **Migrate to Amazon MQ redundant pair + Multi-AZ Auto Scaling for app + Multi-AZ RDS for PostgreSQL** ✅
3. Multi-AZ Auto Scaling for RabbitMQ + Multi-AZ Auto Scaling for app + Multi-AZ RDS for PostgreSQL
4. Multi-AZ Auto Scaling for all three components

---

### Question 139: Automated File Processing
**Scenario**: Reporting team wants to automatically move files from initial S3 bucket to analysis bucket, trigger Lambda and SageMaker Pipelines with least operational overhead.

**Question**: Which solution should be implemented?

**Options**:
1. Lambda function to copy + S3 event notification + Lambda/SageMaker as destinations
2. Lambda function to copy + EventBridge + ObjectCreated rule + Lambda/SageMaker as targets
3. **S3 replication + S3 event notification + Lambda/SageMaker as destinations** ✅
4. S3 replication + EventBridge + ObjectCreated rule + Lambda/SageMaker as targets

---

### Question 140: Cost Optimization (Multi-select)
**Scenario**: Application uses EC2 (sporadic, interruptible), Fargate (predictable front-end), Lambda (predictable API). Need most cost-effective solution.

**Question**: Which combination provides the most cost-effective solution? (Choose two)

**Options**:
1. **Use Spot Instances for the data ingestion layer** ✅
2. Use On-Demand Instances for the data ingestion layer
3. **Purchase a 1-year Compute Savings Plan for the front end and API layer** ✅
4. Purchase 1-year All Upfront Reserved instances for data ingestion layer
5. Purchase 1-year EC2 instance Savings Plan for front end and API layer

---

### Question 141: Global Content Delivery with Low Latency
**Scenario**: Web portal with personalized static/dynamic content needs global delivery with least latency.

**Question**: How should the architecture be designed?

**Options**:
1. Single Region + CloudFront for all static and dynamic content
2. Two Regions + Route 53 latency routing policy
3. **Single Region + CloudFront for static content + ALB for dynamic content** ✅
4. Two Regions + Route 53 geolocation routing policy

---

### Question 142: Gaming Application Architecture
**Scenario**: Gaming company needs highly available architecture for modified Linux kernel supporting UDP traffic with low latency, nearest edge location, static IPs.

**Question**: What should a solutions architect do?

**Options**:
1. Route 53 → Application Load Balancer → Lambda with Application Auto Scaling
2. CloudFront → Network Load Balancer → Lambda with Application Auto Scaling
3. **AWS Global Accelerator → Network Load Balancer → EC2 with Auto Scaling** ✅
4. API Gateway → Application Load Balancer → EC2 with Auto Scaling

---

### Question 143: Monolith Migration
**Scenario**: Migrate on-premises monolith to AWS, break into smaller applications, different teams manage each, highly scalable with minimal operational overhead.

**Question**: Which solution meets the requirements?

**Options**:
1. AWS Lambda with API Gateway
2. **AWS Amplify with API Gateway integrated with Lambda** ✅
3. EC2 instances with Application Load Balancer and Auto Scaling
4. Amazon ECS with Application Load Balancer

---

### Question 144: Aurora Performance Optimization
**Scenario**: Aurora database shows ReadIOPS and CPUUtilization spikes during monthly reports, affecting e-commerce application performance.

**Question**: What is the most cost-effective solution?

**Options**:
1. Migrate monthly reporting to Amazon Redshift
2. **Migrate monthly reporting to an Aurora Replica** ✅
3. Migrate Aurora database to larger instance class
4. Increase Provisioned IOPS on Aurora instance

---

### Question 145: Web Application Scaling
**Scenario**: Single EC2 instance hosts PHP analytics app with MySQL, showing performance degradation and 5xx errors during busy times.

**Question**: Which solution will meet requirements most cost-effectively?

**Options**:
1. Migrate to RDS MySQL + AMI + second EC2 + Application Load Balancer
2. Migrate to RDS MySQL + AMI + second EC2 + Route 53 weighted routing
3. Migrate to Aurora MySQL + Lambda function to change instance type + CloudWatch alarm
4. **Migrate to Aurora MySQL + AMI + launch template + Auto Scaling with Spot Fleet + Application Load Balancer** ✅

---

### Question 146: EC2 Cost Optimization
**Scenario**: Stateless web application with heavy 8-hour daily usage, moderate overnight usage, low weekend usage. Minimize costs without affecting availability.

**Question**: Which solution meets the requirements?

**Options**:
1. Use Spot Instances for entire workload
2. **Use Reserved Instances for baseline + Spot Instances for additional capacity** ✅
3. Use On-Demand for baseline + Spot Instances for additional capacity
4. Use Dedicated Instances for baseline + On-Demand for additional capacity

---

### Question 147: Log File Storage Optimization
**Scenario**: Store application logs for 10 years, past month accessed regularly for troubleshooting, >10TB per month generated.

**Question**: Which storage option is most cost-effective?

**Options**:
1. S3 + AWS Backup to move old logs to S3 Glacier Deep Archive
2. **S3 + S3 Lifecycle policies to move old logs to S3 Glacier Deep Archive** ✅
3. CloudWatch Logs + AWS Backup to move old logs to S3 Glacier Deep Archive
4. CloudWatch Logs + S3 Lifecycle policies to move old logs to S3 Glacier Deep Archive

---

### Question 148: Data Ingestion Reliability
**Scenario**: Data ingestion workflow with SNS topic and Lambda occasionally fails due to network issues. Need to ensure all notifications are eventually processed.

**Question**: What should a solutions architect do?

**Options**:
1. Configure Lambda for deployment across multiple Availability Zones
2. Modify Lambda configuration to increase CPU and memory allocations
3. Configure SNS topic's retry strategy to increase retries and wait time
4. **Configure Amazon SQS queue as on-failure destination. Modify Lambda to process queue messages** ✅

---

### Question 149: Event Data Processing
**Scenario**: Process event data in specific order as received with minimal operational overhead.

**Question**: How should a solutions architect accomplish this?

**Options**:
1. **Amazon SQS FIFO queue + AWS Lambda function** ✅
2. Amazon SNS topic + AWS Lambda subscriber
3. Amazon SQS standard queue + AWS Lambda function
4. Amazon SNS topic + Amazon SQS queue subscriber

---

### Question 150: Infrastructure Metric Alarms
**Scenario**: Set up alarms for EC2 migration. No action needed for CPU >50% short bursts, but act quickly if CPU >50% AND high read IOPS occur together. Reduce false alarms.

**Question**: What should the solutions architect do?

**Options**:
1. **Create Amazon CloudWatch composite alarms where possible** ✅
2. Create CloudWatch dashboards to visualize metrics
3. Create CloudWatch Synthetics canaries to monitor application
4. Create single CloudWatch metric alarms with multiple thresholds

---

### Question 151: Compliance and Regional Restrictions (Multi-select)
**Scenario**: Migrate on-premises data center to AWS. Compliance requires only ap-northeast-3 Region. Administrators cannot connect VPCs to internet.

**Question**: Which solutions meet these requirements? (Choose two)

**Options**:
1. **Use AWS Control Tower to implement data residency guardrails** ✅
2. Use AWS WAF rules to prevent internet access
3. **Use AWS Organizations service control policies (SCPs) to prevent VPC internet access** ✅
4. Create network ACL outbound rules to deny traffic from 0.0.0.0/0
5. Use AWS Config managed rules to detect internet gateways

---

### Question 152: Training Application Cost Optimization
**Scenario**: Three-tier training application accessed 12 hours daily using RDS MySQL. Want to minimize costs.

**Question**: What should a solutions architect do?

**Options**:
1. Configure IAM policy for Systems Manager Session Manager with automatic start/stop
2. Create ElastiCache Redis cluster for data access when DB stopped
3. Launch EC2 instance with IAM role and cron job to start/stop DB
4. **Create Lambda functions to start/stop DB with EventBridge scheduled rules** ✅

---

### Question 153: Ringtone Storage Optimization
**Scenario**: Millions of ringtone files (≥128 KB) in S3 Standard. Downloads infrequent for files >90 days old. Need cost-effective storage with accessibility.

**Question**: Which action should the company take?

**Options**:
1. Configure S3 Standard-IA for initial storage tier
2. Move files to S3 Intelligent-Tiering with 90-day configuration
3. Configure S3 inventory to manage objects and move to S3 Standard-IA after 90 days
4. **Implement S3 Lifecycle policy to move objects to S3 Standard-IA after 90 days** ✅

---

### Question 154: Medical Trial Repository
**Scenario**: Medical trial results repository. Few scientists add files, all others read-only access. No modifications/deletions allowed. Keep all files minimum 1 year.

**Question**: Which solution meets the requirements?

**Options**:
1. Use S3 Object Lock in governance mode with 1-year legal hold
2. **Use S3 Object Lock in compliance mode with 365-day retention period** ✅
3. Use IAM role to restrict deletions/changes with S3 bucket policy
4. Configure S3 bucket to invoke Lambda function to track object hashes

---

### Question 155: Global Media File Caching
**Scenario**: Large media company wants to cache confidential media files globally for reliable access. Content in S3 buckets, need quick delivery regardless of geographic location.

**Question**: Which solution meets the requirements?

**Options**:
1. Use AWS DataSync to connect S3 buckets to web application
2. Deploy AWS Global Accelerator to connect S3 buckets to web application
3. **Deploy Amazon CloudFront to connect S3 buckets to CloudFront edge servers** ✅
4. Use Amazon SQS to connect S3 buckets to web application

---

### Question 156: Data Consolidation and Analytics (Multi-select)
**Scenario**: Consolidate batch data from databases and live stream data for business analytics. Process and stage in S3 buckets for one-time queries and BI tool KPIs with least operational overhead.

**Question**: Which combination of steps meets requirements? (Choose two)

**Options**:
1. **Use Amazon Athena for one-time queries. Use Amazon QuickSight for KPI dashboards** ✅
2. Use Amazon Kinesis Data Analytics for one-time queries. Use QuickSight for KPI dashboards
3. Create custom Lambda functions to move records to Amazon Redshift cluster
4. Use AWS Glue ETL job to convert to JSON format and load into OpenSearch Service clusters
5. **Use AWS Lake Formation blueprints to identify data for data lake ingestion. Use AWS Glue to crawl, extract, and load data into S3 in Apache Parquet format** ✅

---

### Question 157: Aurora Data Retention and Audit (Multi-select)
**Scenario**: Aurora PostgreSQL cluster must store data for 5 years, delete after 5 years, indefinitely keep audit logs of database actions. Currently has automated backups.

**Question**: Which combination of steps should be taken? (Choose two)

**Options**:
1. Take manual snapshot of DB cluster
2. Create lifecycle policy for automated backups
3. Configure automated backup retention for 5 years
4. **Configure Amazon CloudWatch Logs export for the DB cluster** ✅
5. **Use AWS Backup to take backups and keep for 5 years** ✅

---

### Question 158: Musical Event Streaming Performance
**Scenario**: Website for musical event with real-time streaming and on-demand videos for global audience.

**Question**: Which service improves performance for both real-time and on-demand streaming?

**Options**:
1. **Amazon CloudFront** ✅
2. AWS Global Accelerator
3. Amazon Route 53
4. Amazon S3 Transfer Acceleration

---

### Question 159: API Protection from Fraudulent Requests (Multi-select)
**Scenario**: Serverless application using API Gateway and Lambda experiencing traffic spike from fraudulent botnet requests.

**Question**: Which steps should block unauthorized users? (Choose two)

**Options**:
1. **Create usage plan with API key shared with genuine users only** ✅
2. Integrate logic within Lambda function to ignore fraudulent IP addresses
3. **Implement AWS WAF rule to target malicious requests and filter them out** ✅
4. Convert public API to private API and update DNS records
5. Create IAM role for each user attempting to access the API

---

### Question 160: Disaster Recovery for Analytics Data
**Scenario**: Analytics application generates 300 MB monthly JSON data. Need disaster recovery backup accessible in milliseconds, kept for 30 days, most cost-effective.

**Question**: Which solution meets these requirements?

**Options**:
1. Amazon OpenSearch Service (Amazon Elasticsearch Service)
2. Amazon S3 Glacier
3. **Amazon S3 Standard** ✅
4. Amazon RDS for PostgreSQL

---

### Question 161: Python Application Migration
**Scenario**: Small Python application processes JSON documents thousands of times daily, outputs to on-premises SQL database. Need highly available, scalable solution with minimal operational overhead.

**Question**: Which solution will meet these requirements?

**Options**:
1. S3 bucket for JSON + multiple EC2 instances + Aurora DB cluster
2. **S3 bucket for JSON + Lambda function triggered by S3 events + Aurora DB cluster** ✅
3. EBS volume with Multi-Attach + multiple EC2 instances + RDS DB instance
4. SQS queue for JSON messages + ECS cluster with EC2 launch type + RDS DB instance

---

### Question 162: HPC Financial Risk Modeling
**Scenario**: HPC workloads on Linux, hundreds of EC2 Spot Instances, short-lived workflows, thousands of output files. Need high-performance file system integrated with persistent storage.

**Question**: Which combination of AWS services meets these requirements?

**Options**:
1. **Amazon FSx for Lustre integrated with Amazon S3** ✅
2. Amazon FSx for Windows File Server integrated with Amazon S3
3. Amazon S3 Glacier integrated with Amazon EBS
4. Amazon S3 bucket with VPC endpoint integrated with EBS gp2 volume

---

### Question 163: Containerized Application Deployment
**Scenario**: Containerized application moving to AWS, thousands of users expected, need highly available architecture with minimal operational overhead and automatic scaling.

**Question**: Which solution will meet these requirements?

**Options**:
1. **ECR repository + ECS cluster with Fargate launch type + target tracking scaling** ✅
2. ECR repository + ECS cluster with EC2 launch type + target tracking scaling
3. EC2-based container repository + EC2 instances across multiple AZs + CloudWatch monitoring
4. AMI with container image + Auto Scaling group + CloudWatch alarms

---

### Question 164: Message Processing Between Applications
**Scenario**: Sender application sends 1,000 messages/hour, processing can take up to 2 days, failed messages must be retained without impacting remaining messages.

**Question**: Which solution is most operationally efficient?

**Options**:
1. EC2 instance running Redis database for both applications
2. Amazon Kinesis data stream with Kinesis Client Library (KCL)
3. **Amazon SQS queue with dead-letter queue for failed messages** ✅
4. Amazon SNS topic with processing application subscribed

---

### Question 165: CloudFront + WAF Integration
**Scenario**: CloudFront with S3 origin for static website. Security policy requires all website traffic inspected by AWS WAF.

**Question**: How should the solutions architect comply with these requirements?

**Options**:
1. Configure S3 bucket policy to accept requests from AWS WAF ARN only
2. Configure CloudFront to forward all requests to AWS WAF before requesting from S3
3. Configure security group for CloudFront IP addresses, associate AWS WAF to CloudFront
4. **Configure CloudFront and S3 with OAI, enable AWS WAF on the distribution** ✅

---

### Question 166: Global Static Content Delivery
**Scenario**: Global event organizers want daily reports online as static HTML pages, expecting millions of views worldwide, files stored in S3 bucket.

**Question**: Which action should the solutions architect take?

**Options**:
1. Generate presigned URLs for the files
2. Use cross-Region replication to all Regions
3. Use geoproximity feature of Amazon Route 53
4. **Use Amazon CloudFront with S3 bucket as origin** ✅

---

### Question 167: SQS Message Processing Cost Optimization
**Scenario**: Production application reads from SQS queue, processes messages in parallel, unpredictable volume with intermittent traffic, requires continuous processing without downtime.

**Question**: Which solution is most cost-effective?

**Options**:
1. Use Spot Instances exclusively for maximum capacity
2. Use Reserved Instances exclusively for maximum capacity
3. **Use Reserved Instances for baseline + Spot Instances for additional capacity** ✅
4. Use Reserved Instances for baseline + On-Demand for additional capacity

---

### Question 168: AWS Organizations Service Control
**Scenario**: Security team wants to limit access to specific services/actions across all AWS accounts in large AWS Organizations. Need scalable solution with single point of maintenance.

**Question**: What should a solutions architect do?

**Options**:
1. Create ACL to provide access to services or actions
2. Create security group for accounts and attach to user groups
3. Create cross-account roles in each account to deny access
4. **Create service control policy in root organizational unit to deny access** ✅

---

### Question 169: DDoS Protection for Web Application
**Scenario**: Public web application using Application Load Balancer, company concerned about security due to recent web attacks, need to reduce DDoS attack risk.

**Question**: What should the solutions architect do?

**Options**:
1. Add Amazon Inspector agent to the ALB
2. Configure Amazon Macie to prevent attacks
3. **Enable AWS Shield Advanced to prevent attacks** ✅
4. Configure Amazon GuardDuty to monitor the ALB

---

### Question 170: Geographic Access Restriction
**Scenario**: Web application behind ALB, company policy now requires application access from one specific country only.

**Question**: Which configuration will meet this requirement?

**Options**:
1. Configure security group for EC2 instances
2. Configure security group on Application Load Balancer
3. **Configure AWS WAF on the Application Load Balancer in VPC** ✅
4. Configure network ACL for subnet containing EC2 instances

---

### Question 171: Scalable API for Tax Computations
**Scenario**: API for tax computations based on item prices, larger inquiries during holiday season cause slower response times, need scalable and elastic solution.

**Question**: What should the solutions architect do?

**Options**:
1. API hosted on single EC2 instance performing computations
2. **REST API using API Gateway passing item names to Lambda for tax computations** ✅
3. Application Load Balancer with two EC2 instances computing tax
4. REST API using API Gateway connecting to API hosted on EC2 instance

---

### Question 172: CloudFront Field-Level Encryption
**Scenario**: CloudFront distribution for application with sensitive user information, uses HTTPS but needs another security layer, sensitive info protected throughout stack with restricted access.

**Question**: Which action should the solutions architect take?

**Options**:
1. Configure CloudFront signed URL
2. Configure CloudFront signed cookie
3. **Configure CloudFront field-level encryption profile** ✅
4. Configure CloudFront Origin Protocol Policy to HTTPS Only

---

### Question 173: Gaming Media Content Delivery
**Scenario**: Browser-based gaming application, users consume large number of videos/images from S3, same content for all users, millions of worldwide users, reduce load on origin cost-effectively.

**Question**: Which solution is most cost-effective?

**Options**:
1. Deploy AWS Global Accelerator in front of web servers
2. **Deploy Amazon CloudFront web distribution in front of S3 bucket** ✅
3. Deploy ElastiCache for Redis instance in front of web servers
4. Deploy ElastiCache for Memcached instance in front of web servers

---

### Question 174: High Availability Multi-Tier Application
**Scenario**: Multi-tier application with six front-end web servers in Auto Scaling group in single AZ behind ALB, need high availability without modifying application.

**Question**: Which architecture provides high availability?

**Options**:
1. Auto Scaling group using three instances across two Regions
2. **Modify Auto Scaling group to use three instances across two Availability Zones** ✅
3. Create Auto Scaling template for quick instance creation in another Region
4. Change ALB to round-robin configuration for traffic balancing

---

### Question 175: Database Connection Management
**Scenario**: Order-processing application using API Gateway and Lambda with Aurora PostgreSQL, sudden surge caused timeouts due to high CPU/memory from many open connections.

**Question**: Which solution prevents timeouts with least changes?

**Options**:
1. Configure provisioned concurrency for Lambda, make database global across regions
2. **Use Amazon RDS Proxy, modify Lambda to use RDS Proxy endpoint** ✅
3. Create read replica in different region, use query parameters to route traffic
4. Migrate from Aurora PostgreSQL to DynamoDB using DMS

---

### Question 176: Secure DynamoDB Access
**Scenario**: Application runs on EC2 instances in private subnets, needs to access DynamoDB table securely without traffic leaving AWS network.

**Question**: What is the most secure way to access the table?

**Options**:
1. **Use a VPC endpoint for DynamoDB** ✅
2. Use NAT gateway in public subnet
3. Use NAT instance in private subnet
4. Use internet gateway attached to VPC

---

### Question 177: DynamoDB Performance Optimization
**Scenario**: Entertainment company using DynamoDB for media metadata, read-intensive application experiencing delays, need improved performance without operational overhead or reconfiguration.

**Question**: What should a solutions architect recommend?

**Options**:
1. Use Amazon ElastiCache for Redis
2. **Use Amazon DynamoDB Accelerator (DAX)** ✅
3. Replicate data using DynamoDB global tables
4. Use Amazon ElastiCache for Memcached with Auto Discovery

---

### Question 178: Cross-Region Backup Strategy
**Scenario**: Infrastructure with EC2 instances and RDS DB instance in single region, want to back up data in separate region with least operational overhead.

**Question**: Which solution meets requirements?

**Options**:
1. **Use AWS Backup to copy EC2 and RDS backups to separate region** ✅
2. Use Amazon Data Lifecycle Manager (DLM) to copy backups to separate region
3. Create AMIs of EC2 instances, copy to separate region, create RDS read replica
4. Create EBS snapshots and copy, create RDS snapshots and export to S3 with CRR

---

### Question 179: Secure Parameter Storage
**Scenario**: Store database username/password securely for application running on EC2 that accesses RDS, create secure parameter in Systems Manager Parameter Store.

**Question**: What should the solutions architect do?

**Options**:
1. **Create IAM role with Parameter Store read access and KMS decrypt access, assign to EC2** ✅
2. Create IAM policy with Parameter Store read access and KMS decrypt access, assign to EC2
3. Create IAM trust relationship between Parameter Store parameter and EC2 instance
4. Create IAM trust relationship between DB instance and EC2 instance

---

### Question 180: API Platform Protection (Multi-select)
**Scenario**: Cloud communications platform using EC2 behind NLB, API Gateway for external access, protect against SQL injection and detect/mitigate sophisticated DDoS attacks.

**Question**: Which combination provides most protection? (Choose two)

**Options**:
1. Use AWS WAF to protect the NLB
2. **Use AWS Shield Advanced with the NLB** ✅
3. **Use AWS WAF to protect Amazon API Gateway** ✅
4. Use Amazon GuardDuty with AWS Shield Standard
5. Use AWS Shield Standard with Amazon API Gateway

---

### Question 181: Microservices Communication Pattern
**Scenario**: Legacy monolithic data processing application being rewritten to microservices on ECS, data processed sequentially but order of results doesn't matter.

**Question**: What should a solutions architect recommend for microservices communication?

**Options**:
1. **Create Amazon SQS queue, add code to producers to send data to queue, consumers to process from queue** ✅
2. Create Amazon SNS topic, add code to producers to publish, consumers to subscribe
3. Create AWS Lambda function to pass messages between producers and consumers
4. Create DynamoDB table with DynamoDB Streams for communication

---

### Question 182: MySQL High Availability Migration
**Scenario**: Migrate MySQL database from on-premises to AWS, recent outage significantly impacted business, need reliable solution that minimizes data loss and stores every transaction on at least two nodes.

**Question**: Which solution meets these requirements?

**Options**:
1. Create RDS instance with synchronous replication to three nodes in three AZs
2. **Create Amazon RDS MySQL instance with Multi-AZ functionality enabled** ✅
3. Create RDS MySQL instance with read replica in separate region with synchronous replication
4. Create EC2 instance with MySQL triggering Lambda function to replicate to RDS

---

### Question 183: Dynamic Website with Minimal Maintenance
**Scenario**: Building dynamic ordering website, minimize server maintenance and patching, highly available, scale read/write capacity quickly to meet user demand changes.

**Question**: Which solution meets requirements?

**Options**:
1. **S3 for static content + API Gateway/Lambda for dynamic content + DynamoDB on-demand + CloudFront** ✅
2. S3 for static content + API Gateway/Lambda for dynamic content + Aurora with Auto Scaling + CloudFront
3. EC2 instances for all content + Auto Scaling group + ALB + DynamoDB with provisioned capacity
4. EC2 instances for all content + Auto Scaling group + ALB + Aurora with Auto Scaling

---

### Question 184: Lambda VPC Database Access
**Scenario**: AWS account with Direct Connect to on-premises, Lambda function needs access to database in private subnet in company's data center.

**Question**: Which solution will meet these requirements?

**Options**:
1. **Configure Lambda function to run in VPC with appropriate security group** ✅
2. Set up VPN connection from AWS to data center, route Lambda traffic through VPN
3. Update VPC route tables to allow Lambda access to on-premises through Direct Connect
4. Create Elastic IP address for Lambda function without elastic network interface

---

### Question 185: ECS S3 Access Permissions
**Scenario**: Application running on Amazon ECS creates resized images and makes S3 API calls to store resized images in S3.

**Question**: How can a solutions architect ensure application has S3 permissions?

**Options**:
1. Update S3 role in IAM to allow read/write from ECS, relaunch container
2. **Create IAM role with S3 permissions, specify role as taskRoleArn in task definition** ✅
3. Create security group allowing ECS to S3 access, update ECS cluster launch configuration
4. Create IAM user with S3 permissions, relaunch EC2 instances while logged in as this user

---

### Question 186: Windows Shared File System
**Scenario**: Windows-based application migration to AWS, requires shared Windows file system attached to multiple EC2 Windows instances across multiple Availability Zones.

**Question**: What should a solutions architect do?

**Options**:
1. Configure AWS Storage Gateway in volume gateway mode, mount to each Windows instance
2. **Configure Amazon FSx for Windows File Server, mount to each Windows instance** ✅
3. Configure Amazon EFS file system, mount to each Windows instance
4. Configure EBS volume with required size, attach to each EC2 instance

---

### Question 187: Highly Available E-commerce Solution (Multi-select)
**Scenario**: E-commerce application with load-balanced front end, container-based application, relational database. Need highly available solution with minimal manual intervention.

**Question**: Which solutions meet these requirements? (Choose two)

**Options**:
1. **Create Amazon RDS DB instance in Multi-AZ mode** ✅
2. Create RDS DB instance with replicas in another Availability Zone
3. Create EC2 instance-based Docker cluster for dynamic application load
4. **Create Amazon ECS cluster with Fargate launch type for dynamic application load** ✅
5. Create Amazon ECS cluster with EC2 launch type for dynamic application load

---

### Question 188: SFTP Solution for Data Lake
**Scenario**: Company uses S3 as data lake, new partner must use SFTP to upload data files, need highly available SFTP solution with minimal operational overhead.

**Question**: Which solution will meet these requirements?

**Options**:
1. **Use AWS Transfer Family to configure SFTP-enabled server with publicly accessible endpoint, S3 as destination** ✅
2. Use Amazon S3 File Gateway as SFTP server, expose endpoint to partner
3. Launch EC2 instance in private subnet, partner uploads via VPN, cron job uploads to S3
4. Launch EC2 instances behind NLB with SFTP listener, cron job uploads to S3

---

### Question 189: Contract Document Storage with Encryption (Multi-select)
**Scenario**: Store contract documents for 5 years, documents cannot be overwritten or deleted during this period, encrypt at rest with automatic annual key rotation, least operational overhead.

**Question**: Which combination of steps meets requirements? (Choose two)

**Options**:
1. Store documents in S3, use S3 Object Lock in governance mode
2. **Store documents in S3, use S3 Object Lock in compliance mode** ✅
3. Use server-side encryption with S3 managed keys (SSE-S3) with key rotation
4. **Use server-side encryption with AWS KMS customer managed keys with key rotation** ✅
5. Use server-side encryption with KMS customer provided keys with key rotation

---

### Question 190: Java/PHP Web Application Migration
**Scenario**: Java and PHP web application migration from on-premises, need ability to test new site features frequently, highly available managed solution with minimum operational overhead.

**Question**: Which solution will meet these requirements?

**Options**:
1. S3 bucket with static web hosting + Lambda for dynamic content
2. **Deploy to AWS Elastic Beanstalk environment, use URL swapping for feature testing** ✅
3. Deploy to EC2 instances with Auto Scaling groups and Application Load Balancer
4. Containerize and deploy to EC2 instances with AWS Load Balancer Controller

---

### Question 191: Database Read Query Optimization
**Scenario**: Ordering application with RDS for MySQL, employees run reporting queries during business hours causing timeouts in order processing, need to eliminate timeouts without preventing queries.

**Question**: What should a solutions architect do?

**Options**:
1. **Create read replica, move reporting queries to read replica** ✅
2. Create read replica, distribute ordering application to primary and read replica
3. Migrate ordering application to DynamoDB with on-demand capacity
4. Schedule reporting queries for non-peak hours

---

### Question 192: Medical Document Analysis (Multi-select)
**Scenario**: Hospital wants digital copies of historical records, scan and upload hundreds of documents daily, analyze documents, extract medical information, store for SQL queries, maximize scalability and operational efficiency.

**Question**: Which combination of steps meets requirements? (Choose two)

**Options**:
1. Write document information to EC2 instance running MySQL database
2. **Write document information to S3 bucket, use Amazon Athena to query data** ✅
3. Create Auto Scaling group of EC2 instances running custom application for processing
4. Create Lambda function using Amazon Rekognition and Transcribe Medical
5. **Create Lambda function using Amazon Textract and Comprehend Medical** ✅

---

### Question 193: Database Read Performance Optimization
**Scenario**: Batch application on EC2 instances with multiple RDS databases backend, application causing high number of database reads, need to reduce reads while ensuring high availability.

**Question**: What should the solutions architect do?

**Options**:
1. Add Amazon RDS read replicas
2. **Use Amazon ElastiCache for Redis** ✅
3. Use Amazon Route 53 DNS caching
4. Use Amazon ElastiCache for Memcached

---

### Question 194: Critical Database High Availability
**Scenario**: Critical application using EC2 for database, database must be highly available and fail over automatically if disruptive event occurs.

**Question**: Which solution will meet these requirements?

**Options**:
1. **Launch two EC2 instances in different AZs in same region, install database on both, configure as cluster with replication** ✅
2. Launch EC2 instance in AZ, use AMI for backup, use CloudFormation for automated provisioning
3. Launch two EC2 instances in different regions, install database on both, set up replication
4. Launch EC2 instance in AZ, use AMI for backup, use EC2 automatic recovery

---

### Question 195: Resilient Order Processing System
**Scenario**: Order system sends requests to EC2 instances that process orders and store in RDS, users report reprocessing orders when system fails, need resilient solution for automatic processing during outages.

**Question**: What should a solutions architect do?

**Options**:
1. Move EC2 instances to Auto Scaling group, create EventBridge rule to target ECS task
2. Move EC2 instances to Auto Scaling group behind ALB, update order system to send to ALB
3. **Move EC2 instances to Auto Scaling group, configure order system to send to SQS queue, configure EC2 to consume from queue** ✅
4. Create SNS topic with Lambda function subscribed, configure order system to send to SNS

---

## Answer Key Summary

| Question | Answer | Key Concept |
|----------|--------|-------------|
| 131 | 4 | Origin Access Identity (OAI) |
| 132 | 1 | CloudFront + S3 |
| 133 | 3 | RDS Custom for Oracle |
| 134 | 3 | S3 + Athena Serverless Analytics |
| 135 | 4 | AWS PrivateLink |
| 136 | 1,3 | DMS Replication |
| 137 | 2 | AWS Organizations Alternate Contacts |
| 138 | 2 | Amazon MQ + RDS Multi-AZ |
| 139 | 3 | S3 Replication + Event Notifications |
| 140 | 1,3 | Spot Instances + Compute Savings Plan |
| 141 | 3 | CloudFront for Static, ALB for Dynamic |
| 142 | 3 | Global Accelerator + NLB |
| 143 | 2 | AWS Amplify + API Gateway |
| 144 | 2 | Aurora Read Replica |
| 145 | 4 | Aurora + Auto Scaling + Spot Fleet |
| 146 | 2 | Reserved + Spot Instances |
| 147 | 2 | S3 Lifecycle Policies |
| 148 | 4 | SQS Dead Letter Queue |
| 149 | 1 | SQS FIFO Queue |
| 150 | 1 | CloudWatch Composite Alarms |
| 151 | 1,3 | Control Tower + Organizations SCPs |
| 152 | 4 | Lambda + EventBridge Scheduling |
| 153 | 4 | S3 Lifecycle to Standard-IA |
| 154 | 2 | S3 Object Lock Compliance Mode |
| 155 | 3 | CloudFront Edge Servers |
| 156 | 1,5 | Athena/QuickSight + Lake Formation |
| 157 | 4,5 | CloudWatch Logs + AWS Backup |
| 158 | 1 | CloudFront for Streaming |
| 159 | 1,3 | API Keys + AWS WAF |
| 160 | 3 | S3 Standard for Quick Access |
| **161** | **2** | **Event-Driven Lambda Processing** |
| **162** | **1** | **FSx for Lustre + S3 Integration** |
| **163** | **1** | **ECS Fargate + Target Tracking** |
| **164** | **3** | **SQS + Dead Letter Queue** |
| **165** | **4** | **CloudFront OAI + WAF** |
| **166** | **4** | **CloudFront Global Distribution** |
| **167** | **3** | **Reserved + Spot Instance Mix** |
| **168** | **4** | **Organizations Service Control Policies** |
| **169** | **3** | **AWS Shield Advanced** |
| **170** | **3** | **AWS WAF Geographic Restrictions** |
| **171** | **2** | **API Gateway + Lambda Serverless** |
| **172** | **3** | **CloudFront Field-Level Encryption** |
| **173** | **2** | **CloudFront Content Distribution** |
| **174** | **2** | **Multi-AZ Auto Scaling** |
| **175** | **2** | **RDS Proxy Connection Pooling** |
| **176** | **1** | **VPC Endpoint for DynamoDB** |
| **177** | **2** | **DynamoDB Accelerator (DAX)** |
| **178** | **1** | **AWS Backup Cross-Region** |
| **179** | **1** | **IAM Role + Parameter Store** |
| **180** | **2,3** | **Shield Advanced + WAF** |
| **181** | **1** | **SQS for Microservices Communication** |
| **182** | **2** | **RDS Multi-AZ** |
| **183** | **1** | **Serverless Architecture Pattern** |
| **184** | **1** | **Lambda VPC Configuration** |
| **185** | **2** | **ECS Task Role** |
| **186** | **2** | **FSx for Windows File Server** |
| **187** | **1,4** | **RDS Multi-AZ + ECS Fargate** |
| **188** | **1** | **AWS Transfer Family** |
| **189** | **2,4** | **S3 Object Lock + KMS** |
| **190** | **2** | **Elastic Beanstalk URL Swapping** |
| **191** | **1** | **RDS Read Replica** |
| **192** | **2,5** | **S3/Athena + Textract/Comprehend** |
| **193** | **2** | **ElastiCache for Redis** |
| **194** | **1** | **Multi-AZ EC2 Database Cluster** |
| **195** | **3** | **SQS Queue + Auto Scaling** |

## Study Tips

1. **Focus on Cost Optimization**: Many questions test your ability to choose the most cost-effective solution
2. **High Availability Patterns**: Understand Multi-AZ deployments, Auto Scaling, and Load Balancers
3. **Security Best Practices**: Know when to use OAI, PrivateLink, WAF, and proper IAM configurations
4. **Storage Classes**: Understand S3 storage classes and lifecycle policies
5. **Serverless vs. Traditional**: Know when to choose serverless solutions for minimal operational overhead
6. **Database Migration**: Understand DMS, RDS Custom, and Aurora features
7. **Networking**: Master VPC concepts, PrivateLink, and Global Accelerator vs CloudFront use cases

## Contributing

Feel free to submit issues or pull requests if you find any errors or want to add more questions to this collection.

## License

This content is for educational purposes only and is based on AWS documentation and best practices.