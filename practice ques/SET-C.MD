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

