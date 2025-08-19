## Table of Contents

- [Questions 261-270: Multi-tier Applications & Performance](#questions-261-270-multi-tier-applications--performance)
- [Questions 271-280: Scaling & Disaster Recovery](#questions-271-280-scaling--disaster-recovery)
- [Questions 281-290: Security & Cost Optimization](#questions-281-290-security--cost-optimization)
- [Questions 291-294: Advanced Networking & Data Platform](#questions-291-294-advanced-networking--data-platform)
- [Questions 295-325: Data Processing & Security](#questions-295-325-data-processing--security)# AWS Solutions Architect Associate Practice Questions

A comprehensive collection of practice questions for the AWS Certified Solutions Architect Associate exam, covering various AWS services and architectural scenarios.

**Total Questions: 65 (Questions 261-325)**

## Table of Contents

- [Questions 261-270: Multi-tier Applications & Performance](#questions-261-270-multi-tier-applications--performance)
- [Questions 271-280: Scaling & Disaster Recovery](#questions-271-280-scaling--disaster-recovery)
- [Questions 281-290: Security & Cost Optimization](#questions-281-290-security--cost-optimization)
- [Questions 291-294: Advanced Networking & Data Platform](#questions-291-294-advanced-networking--data-platform)

---

## Questions 261-270: Multi-tier Applications & Performance

### Question 261: Content Delivery Based on Device Type
**Scenario:** A company deployed a retail website globally using EC2 instances behind an Elastic Load Balancer in an Auto Scaling group across multiple AZs. They need to serve different content versions based on customer devices.

**Question:** Which combination of actions should a solutions architect take? (Choose two.)

**Options:**
- A) Configure Amazon CloudFront to cache multiple versions of the content
- B) Configure a host header in a Network Load Balancer to forward traffic to different instances
- C) Configure a Lambda@Edge function to send specific objects to users based on the User-Agent header
- D) Configure AWS Global Accelerator with NLB for host-based routing to different EC2 instances
- E) Configure AWS Global Accelerator with NLB for path-based routing to different EC2 instances

---

### Question 262: VPC Connectivity for ElastiCache
**Scenario:** A multi-tier web application uses ElastiCache cluster in a Cache VPC and EC2 instances in an App VPC (both in us-east-1). Need cost-effective connectivity solution.

**Question:** Which solution will meet these requirements MOST cost-effectively?

**Options:**
- A) Create VPC peering connection, add route table entries, configure ElastiCache security group inbound rule from application security group
- B) Create Transit VPC, update route tables, configure ElastiCache security group inbound rule from application security group
- C) Create VPC peering connection, add route table entries, configure peering connection security group inbound rule from application security group
- D) Create Transit VPC, update route tables, configure Transit VPC security group inbound rule from application security group

---

### Question 263: Container Deployment Strategy
**Scenario:** Company building microservices application using containers on AWS. Need minimal maintenance and scaling effort without managing additional infrastructure.

**Question:** Which combination of actions should a solutions architect take? (Choose two.)

**Options:**
- A) Deploy an Amazon Elastic Container Service (Amazon ECS) cluster
- B) Deploy Kubernetes control plane on Amazon EC2 instances across multiple AZs
- C) Deploy ECS service with EC2 launch type, specify desired task number ≥ 2
- D) Deploy ECS service with Fargate launch type, specify desired task number ≥ 2
- E) Deploy Kubernetes worker nodes on EC2 instances across multiple AZs with 2+ replicas

---

### Question 264: DNS Health Check Issues
**Scenario:** Web application hosted on 10 EC2 instances with Route 53 traffic direction. Experiencing timeout errors when DNS queries return IP addresses of unhealthy instances.

**Question:** What should a solutions architect implement to overcome these timeout errors?

**Options:**
- A) Create Route 53 simple routing policy record for each EC2 instance with health checks
- B) Create Route 53 failover routing policy record for each EC2 instance with health checks
- C) Create CloudFront distribution with EC2 instances as origin and associate health checks
- D) Create Application Load Balancer (ALB) with health check in front of EC2 instances, route to ALB from Route 53

---

### Question 265: Highly Available HTTPS Application
**Scenario:** Need highly available application with web, application, and database tiers. HTTPS content delivery should be as close to edge as possible with least delivery time.

**Question:** Which solution meets these requirements and is MOST secure?

**Options:**
- A) Public ALB with EC2 instances in public subnets, CloudFront with public ALB as origin
- B) Public ALB with EC2 instances in private subnets, CloudFront with EC2 instances as origin
- C) Public ALB with EC2 instances in private subnets, CloudFront with public ALB as origin
- D) Public ALB with EC2 instances in public subnets, CloudFront with EC2 instances as origin

---

### Question 266: Gaming Platform Latency Optimization
**Scenario:** Gaming platform deployed in every AWS Region on EC2 instances in Auto Scaling groups behind ALBs. Application is latency-sensitive. Need health monitoring and traffic redirection to healthy endpoints.

**Question:** Which solution meets these requirements?

**Options:**
- A) Configure AWS Global Accelerator accelerator, add listener for application port, attach to Regional endpoint in each Region with ALB as endpoint
- B) Create CloudFront distribution with ALB as origin server, configure cache behavior to use origin cache headers, use Lambda functions to optimize traffic
- C) Create CloudFront distribution with S3 as origin server, configure cache behavior to use origin cache headers, use Lambda functions to optimize traffic
- D) Configure DynamoDB database as data store, create DynamoDB Accelerator (DAX) cluster as in-memory cache

---

### Question 267: Real-time Data Processing
**Scenario:** Mobile app with 1 million users. Must analyze data usage in near-real time, encrypt data in near-real time, and store in centralized location in Apache Parquet format.

**Question:** Which solution will meet these requirements with the LEAST operational overhead?

**Options:**
- A) Kinesis data stream to store in S3, Kinesis Data Analytics for analysis, Lambda function to send data to analytics
- B) Kinesis data stream to store in S3, EMR cluster for analysis, Lambda function to send data to EMR
- C) Kinesis Data Firehose delivery stream to store in S3, EMR cluster for analysis
- D) Kinesis Data Firehose delivery stream to store in S3, Kinesis Data Analytics for analysis

---

### Question 268: Database Read Performance Issues
**Scenario:** Gaming company's web application on EC2 instances behind ALB stores data in RDS for MySQL. Users experiencing delays due to database read performance issues caused by business analysts' read-only queries.

**Question:** What should a solutions architect do with minimal architecture changes?

**Options:**
- A) Use Amazon ElastiCache in front of the database
- B) Use RDS Proxy between the application and the database
- C) Migrate the application from EC2 instances to AWS Lambda
- D) Migrate the database from Amazon RDS for MySQL to Amazon DynamoDB

---

### Question 269: Read-Only Query Performance
**Scenario:** E-commerce company's RDS-based web application experiencing performance degradation due to increased read-only SQL queries from business analysts.

**Question:** What should the solutions architect recommend with minimal changes?

**Options:**
- A) Export data to Amazon DynamoDB for business analysts' queries
- B) Load data into Amazon ElastiCache for business analysts' queries
- C) Create a read replica of the primary database for business analysts' queries
- D) Copy data into Amazon Redshift cluster for business analysts' queries

---

### Question 270: S3 Data Encryption Requirements
**Scenario:** Centralized AWS account storing log data in various S3 buckets. Need encryption at rest before upload and encryption in transit.

**Question:** Which solution meets these requirements?

**Options:**
- A) Use client-side encryption to encrypt data being uploaded to S3 buckets
- B) Use server-side encryption to encrypt data being uploaded to S3 buckets
- C) Create bucket policies requiring server-side encryption with S3 managed encryption keys (SSE-S3)
- D) Enable security option to encrypt S3 buckets through default AWS KMS key

---

## Questions 271-280: Scaling & Disaster Recovery

### Question 271: Auto Scaling Optimization
**Scenario:** Nightly batch processing job automatically scales up for 1 hour before reaching desired EC2 capacity. Peak capacity is consistent every night starting at 1 AM. Need cost-effective solution for quick capacity achievement and scaling down after completion.

**Question:** What should the solutions architect do?

**Options:**
- A) Increase the minimum capacity for the Auto Scaling group
- B) Increase the maximum capacity for the Auto Scaling group
- C) Configure scheduled scaling to scale up to the desired compute level
- D) Change the scaling policy to add more EC2 instances during each scaling operation

---

### Question 272: Global Website Performance
**Scenario:** Dynamic website served from EC2 fleet behind ALB in us-west-1 Region. Website needs multi-language support with high request latency for users worldwide. Don't want to recreate architecture across multiple Regions.

**Question:** What should a solutions architect do?

**Options:**
- A) Replace with S3-hosted website, configure CloudFront distribution with S3 as origin, cache based on Accept-Language header
- B) Configure CloudFront distribution with ALB as origin, set cache behavior to cache based on Accept-Language header
- C) Create API Gateway API integrated with ALB, configure HTTP integration type, enable API cache based on Accept-Language header
- D) Launch EC2 instances in additional Regions with NGINX cache servers, use Route 53 with geolocation routing policy

---

### Question 273: Disaster Recovery Strategy
**Scenario:** Rapidly growing e-commerce company running workloads in single AWS Region. Need DR strategy in different Region with up-to-date database and least latency. DR infrastructure should run at reduced capacity but scale up if necessary.

**Question:** Which solution meets requirements with LOWEST recovery time objective (RTO)?

**Options:**
- A) Use Amazon Aurora global database with pilot light deployment
- B) Use Amazon Aurora global database with warm standby deployment
- C) Use Amazon RDS Multi-AZ DB instance with pilot light deployment
- D) Use Amazon RDS Multi-AZ DB instance with warm standby deployment

---

### Question 274: Application Disaster Recovery
**Scenario:** Application running on EC2 instances needs DR solution with RTO < 4 hours using fewest possible AWS resources during normal operations.

**Question:** Which solution meets requirements MOST operationally efficiently?

**Options:**
- A) Create AMIs to back up EC2 instances, copy to secondary Region, automate infrastructure deployment using Lambda and custom scripts
- B) Create AMIs to back up EC2 instances, copy to secondary Region, automate infrastructure deployment using CloudFormation
- C) Launch EC2 instances in secondary AWS Region, keep active at all times
- D) Launch EC2 instances in secondary Availability Zone, keep active at all times

---

### Question 275: Morning Performance Issues
**Scenario:** Internal browser-based application on EC2 instances behind ALB in Auto Scaling group across multiple AZs. Scales to 20 instances during work hours, down to 2 overnight. Application very slow at day beginning but runs well by mid-morning.

**Question:** How should scaling be changed to address complaints while minimizing costs?

**Options:**
- A) Implement scheduled action setting desired capacity to 20 before office opens
- B) Implement step scaling action at lower CPU threshold with decreased cooldown period
- C) Implement target tracking action at lower CPU threshold with decreased cooldown period
- D) Implement scheduled action setting minimum and maximum capacity to 20 before office opens

---

### Question 276: Multi-tier Application Scaling
**Scenario:** Multi-tier application on EC2 instances in Auto Scaling group with RDS for Oracle using Oracle-specific PL/SQL functions. Traffic increasing steadily, causing EC2 overload and RDS storage issues. Auto Scaling group only defines minimum healthy instance count.

**Question:** What should a solutions architect do for automatic scaling? (Choose two.)

**Options:**
- A) Configure storage Auto Scaling on RDS for Oracle instance
- B) Migrate database to Amazon Aurora to use Auto Scaling storage
- C) Configure alarm on RDS for Oracle instance for low free storage space
- D) Configure Auto Scaling group to use average CPU as scaling metric
- E) Configure Auto Scaling group to use average free memory as scaling metric

---

### Question 277: Video Processing Cost Optimization
**Scenario:** Online video content posting and transcoding service uses Amazon EFS Standard for video storage accessed by multiple EC2 Linux instances. Storage costs becoming too expensive as service popularity grows.

**Question:** Which storage solution is MOST cost-effective?

**Options:**
- A) Use AWS Storage Gateway for files to store and process video content
- B) Use AWS Storage Gateway for volumes to store and process video content
- C) Use Amazon EFS for storing, transfer to Amazon EBS after processing
- D) Use Amazon S3 for storing, temporarily move to EBS volume for processing

---

### Question 278: Employee Data Storage with Security
**Scenario:** Application to store employee data in hierarchical structured relationship. Need minimum-latency response to high-traffic queries, protect sensitive data, and receive monthly email if financial information present.

**Question:** Which combination of steps should a solutions architect take? (Choose two.)

**Options:**
- A) Use Amazon Redshift to store employee data hierarchies, unload to S3 monthly
- B) Use Amazon DynamoDB to store employee data hierarchies, export to S3 monthly
- C) Configure Amazon Macie, integrate with EventBridge to send monthly events to Lambda
- D) Use Amazon Athena to analyze employee data in S3, integrate with QuickSight for dashboards
- E) Configure Amazon Macie, integrate with EventBridge to send monthly SNS notifications

---

### Question 279: DynamoDB Backup Compliance
**Scenario:** Application backed by DynamoDB table. Compliance requires monthly backups, available for 6 months, retained for 7 years.

**Question:** Which solution will meet these requirements?

**Options:**
- A) Create AWS Backup plan for monthly DynamoDB backup, lifecycle policy to cold storage after 6 months, 7-year retention
- B) Create monthly DynamoDB on-demand backup, transition to S3 Glacier Flexible Retrieval after 6 months, S3 Lifecycle policy to delete after 7 years
- C) Use AWS SDK script for monthly on-demand backup, EventBridge rule for monthly execution, second script for lifecycle management
- D) Use AWS CLI for monthly on-demand backup, EventBridge rule with cron expression, specify transition and deletion in command

---

### Question 280: CloudFront Log Analysis
**Scenario:** Company using CloudFront with website, logging enabled to S3 bucket. Need advanced log analyses and visualizations.

**Question:** What should a solutions architect do?

**Options:**
- A) Use standard SQL queries in Amazon Athena to analyze CloudFront logs, visualize with AWS Glue
- B) Use standard SQL queries in Amazon Athena to analyze CloudFront logs, visualize with Amazon QuickSight
- C) Use standard SQL queries in Amazon DynamoDB to analyze CloudFront logs, visualize with AWS Glue
- D) Use standard SQL queries in Amazon DynamoDB to analyze CloudFront logs, visualize with Amazon QuickSight

---

## Questions 281-290: Security & Cost Optimization

### Question 281: Database Recovery Point Objective
**Scenario:** Fleet of web servers using Amazon RDS for PostgreSQL. Compliance check requires RPO of less than 1 second for all production databases.

**Question:** Which solution meets these requirements?

**Options:**
- A) Enable Multi-AZ deployment for the DB instance
- B) Enable auto scaling for DB instance in one Availability Zone
- C) Configure DB instance in one AZ, create multiple read replicas in separate AZ
- D) Configure DB instance in one AZ, configure AWS DMS change data capture (CDC) tasks

---

### Question 282: ALB to EC2 Security Restrictions
**Scenario:** Web application on EC2 instances in private subnet with ALB in public subnets. Need to restrict inbound traffic from ALB to EC2 instances while preventing access from any other source.

**Question:** Which solution will meet these requirements?

**Options:**
- A) Configure route table to direct internet traffic to private IP addresses of EC2 instances
- B) Configure security group for EC2 instances to only allow traffic from ALB security group
- C) Move EC2 instances to public subnet, assign Elastic IP addresses
- D) Configure ALB security group to allow any TCP traffic on any port

---

### Question 283: File System Migration for Applications
**Scenario:** Research company with simulation application (Linux, NFS output every 5 minutes) and visualization application (Windows desktop, SMB file system required). Currently maintaining two synchronized file systems. Need to migrate to AWS without code changes.

**Question:** Which solution will meet these requirements?

**Options:**
- A) Migrate both applications to AWS Lambda, use S3 bucket for data exchange
- B) Migrate both applications to Amazon ECS, configure Amazon FSx File Gateway for storage
- C) Migrate simulation to Linux EC2, visualization to Windows EC2, configure Amazon SQS for data exchange
- D) Migrate simulation to Linux EC2, visualization to Windows EC2, configure Amazon FSx for NetApp ONTAP for storage

---

### Question 284: AWS Billing Report by User
**Scenario:** Management wants AWS billed items report listed by user for department budget creation. Need most efficient way to obtain report information.

**Question:** Which solution meets these requirements?

**Options:**
- A) Run a query with Amazon Athena to generate the report
- B) Create a report in Cost Explorer and download the report
- C) Access bill details from billing dashboard and download the bill
- D) Modify cost budget in AWS Budgets to alert with Amazon SES

---

### Question 285: Static Website Contact Form
**Scenario:** Company hosts static website using S3, wants to add contact form with dynamic server-side components (name, email, phone, message). Expecting fewer than 100 site visits monthly.

**Question:** Which solution will meet requirements MOST cost-effectively?

**Options:**
- A) Host dynamic contact form in Amazon ECS, set up Amazon SES with third-party email provider
- B) Create API Gateway endpoint with Lambda backend calling Amazon SES
- C) Convert static webpage to dynamic using Lightsail, use client-side scripting for contact form, integrate with WorkMail
- D) Create t2.micro EC2 instance, deploy LAMP stack, use client-side scripting for contact form, integrate with WorkMail

---

### Question 286: CloudFront Cache Update Issues
**Scenario:** Static website hosted on CloudFront in front of S3 with database backend. Website doesn't reflect Git repository updates despite properly configured CI/CD pipeline with successful deployment messages.

**Question:** Which solution will meet these requirements?

**Options:**
- A) Add an Application Load Balancer
- B) Add Amazon ElastiCache for Redis or Memcached to database layer
- C) Invalidate the CloudFront cache
- D) Use AWS Certificate Manager (ACM) to validate website's SSL certificate

---

### Question 287: Windows Application Migration
**Scenario:** Migrate Windows-based three-tier application (application, business, database tiers with Microsoft SQL Server) from on-premises to AWS. Need specific SQL Server features (native backups, Data Quality Services) and file sharing between tiers.

**Question:** How should a solutions architect design the architecture?

**Options:**
- A) Host all three tiers on EC2 instances, use Amazon FSx File Gateway for file sharing
- B) Host all three tiers on EC2 instances, use Amazon FSx for Windows File Server for file sharing
- C) Host application and business tiers on EC2, database tier on RDS, use Amazon EFS for file sharing
- D) Host application and business tiers on EC2, database tier on RDS, use Provisioned IOPS SSD (io2) EBS volume for file sharing

---

### Question 288: Linux Web Server File Sharing
**Scenario:** Migrating Linux-based web server group to AWS. Web servers must access files in shared file store for content. Cannot make application changes.

**Question:** What should a solutions architect do?

**Options:**
- A) Create Amazon S3 Standard bucket with access to web servers
- B) Configure CloudFront distribution with S3 bucket as origin
- C) Create Amazon Elastic File System (EFS), mount EFS on all web servers
- D) Configure General Purpose SSD (gp3) EBS volume, mount to all web servers

---

### Question 289: Lambda S3 Access Security
**Scenario:** AWS Lambda function needs read access to S3 bucket in same AWS account.

**Question:** Which solution meets requirements in MOST secure manner?

**Options:**
- A) Apply S3 bucket policy that grants read access to the S3 bucket
- B) Apply IAM role to Lambda function with IAM policy granting read access to the S3 bucket
- C) Embed access key and secret key in Lambda function's code for required IAM permissions
- D) Apply IAM role to Lambda function with IAM policy granting read access to all S3 buckets in account

---

### Question 290: EC2 Cost Optimization
**Scenario:** Web application hosted on multiple EC2 instances in Auto Scaling group that scales with user demand. Want to optimize cost savings without long-term commitment.

**Question:** Which EC2 instance purchasing option should be recommended?

**Options:**
- A) Dedicated Instances only
- B) On-Demand Instances only
- C) Mix of On-Demand Instances and Spot Instances
- D) Mix of On-Demand Instances and Reserved Instances

---

## Questions 291-294: Advanced Networking & Data Platform

### Question 291: Secure Video Content Access
**Scenario:** Media company uses CloudFront for publicly available streaming video content hosted in S3. Want to control access to secure video content. Some users use custom HTTP client without cookie support, others cannot change hardcoded URLs.

**Question:** Which services/methods meet requirements with LEAST user impact? (Choose two.)

**Options:**
- A) Signed cookies
- B) Signed URLs
- C) AWS AppSync
- D) JSON Web Token (JWT)
- E) AWS Secrets Manager

---

### Question 292: Real-time Data Platform
**Scenario:** Preparing new data platform to ingest real-time streaming data from multiple sources. Need to transform data before writing to S3 and ability to use SQL to query transformed data.

**Question:** Which solutions meet these requirements? (Choose two.)

**Options:**
- A) Use Kinesis Data Streams for streaming, Kinesis Data Analytics for transformation, Kinesis Data Firehose to write to S3, Amazon Athena to query transformed data
- B) Use Amazon MSK for streaming, AWS Glue for transformation and writing to S3, Amazon Athena to query transformed data
- C) Use AWS DMS to ingest data, Amazon EMR for transformation and writing to S3, Amazon Athena to query transformed data
- D) Use Amazon MSK for streaming, Kinesis Data Analytics for transformation and writing to S3, RDS query editor to query transformed data
- E) Use Kinesis Data Streams for streaming, AWS Glue for transformation, Kinesis Data Firehose to write to S3, RDS query editor to query transformed data

---

### Question 293: Hybrid Backup Solution
**Scenario:** On-premises volume backup solution reached end of life. Want to use AWS as part of new backup solution while maintaining local access to all data backed up on AWS. Need automatic and secure data transfer.

**Question:** Which solution meets these requirements?

**Options:**
- A) Use AWS Snowball to migrate data to S3, configure on-premises systems to mount Snowball S3 endpoint for local access
- B) Use AWS Snowball Edge to migrate data to S3, use Snowball Edge file interface for on-premises local access
- C) Use AWS Storage Gateway with cached volume gateway, run appliance on-premises, configure percentage of data to cache locally, mount gateway storage volumes for local access
- D) Use AWS Storage Gateway with stored volume gateway, run appliance on-premises, map gateway storage volumes to on-premises storage, mount for local access

---

### Question 294: Private S3 Access from EC2
**Scenario:** Application hosted on Amazon EC2 instances needs to access Amazon S3 bucket. Traffic must not traverse the internet.

**Question:** How should a solutions architect configure access?

**Options:**
- A) Create private hosted zone using Amazon Route 53
- B) Set up gateway VPC endpoint for Amazon S3 in the VPC
- C) Configure EC2 instances to use NAT gateway to access S3 bucket
- D) Establish AWS Site-to-Site VPN connection between VPC and S3 bucket

---

## Questions 295-325: Data Processing & Security

### Question 295: PII Data Processing
**Scenario:** E-commerce company stores terabytes of customer data with PII in AWS Cloud. Data used by three applications - only one needs to process PII. PII must be removed before other two applications process the data.

**Question:** Which solution meets requirements with LEAST operational overhead?

**Options:**
- A) Store data in DynamoDB table, create proxy application layer to intercept and process data for each application
- B) Store data in S3 bucket, process and transform data using S3 Object Lambda before returning to requesting application
- C) Process data and store transformed data in three separate S3 buckets for each application's custom dataset
- D) Process data and store transformed data in three separate DynamoDB tables for each application's custom dataset

---

### Question 296: VPC CIDR Block Planning
**Scenario:** Development team launched application in development VPC with CIDR 192.168.0.0/24. Solutions architect needs to create new VPC in same account to be peered with development VPC.

**Question:** What is the SMALLEST CIDR block that meets these requirements?

**Options:**
- A) 10.0.1.0/32
- B) 192.168.0.0/24
- C) 192.168.1.0/32
- D) 10.0.1.0/24

---

### Question 297: Auto Scaling for Cost Optimization
**Scenario:** Application on five EC2 instances behind ALB with target group. Average CPU usage below 10% most of the time with occasional surges to 65%. Need automated scalability while optimizing costs and ensuring sufficient CPU during surges.

**Question:** Which solution meets these requirements?

**Options:**
- A) Create CloudWatch alarm for CPUUtilization < 20%, Lambda function to terminate EC2 instance when alarm triggers
- B) Create Auto Scaling group with existing ALB and target group, target tracking scaling policy based on ASGAverageCPUUtilization, min 2/desired 3/max 6 instances, target value 50%
- C) Create Auto Scaling group with existing ALB and target group, min 2/desired 3/max 6 instances
- D) Create two CloudWatch alarms (< 20% and > 50% CPU), publish to SNS topic to send email for manual scaling

---

### Question 298: Multi-AZ High Availability
**Scenario:** Critical business application on EC2 instances behind ALB in Auto Scaling group accessing RDS DB instance. All resources in single AZ failed operational review. Need to update design to use second AZ.

**Question:** Which solution makes the application highly available?

**Options:**
- A) Provision subnet in each AZ, configure Auto Scaling group across both AZs, configure DB instance with connections to each network
- B) Provision two subnets extending across both AZs, configure Auto Scaling group across both AZs, configure DB instance with connections to each network
- C) Provision subnet in each AZ, configure Auto Scaling group across both AZs, configure DB instance for Multi-AZ deployment
- D) Provision subnet extending across both AZs, configure Auto Scaling group across both AZs, configure DB instance for Multi-AZ deployment

---

### Question 299: High-Performance Storage Requirements
**Scenario:** Research laboratory processing 8 TB of data requiring sub-millisecond latencies and minimum 6 GBps throughput for storage subsystem. Hundreds of EC2 instances running Amazon Linux will distribute and process data.

**Question:** Which solution meets performance requirements?

**Options:**
- A) Create Amazon FSx for NetApp ONTAP file system, set each volume's tiering policy to ALL, import raw data, mount on EC2 instances
- B) Create S3 bucket for raw data, create Amazon FSx for Lustre file system with persistent SSD storage, select import/export to S3 option, mount on EC2 instances
- C) Create S3 bucket for raw data, create Amazon FSx for Lustre file system with persistent HDD storage, select import/export to S3 option, mount on EC2 instances
- D) Create Amazon FSx for NetApp ONTAP file system, set each volume's tiering policy to NONE, import raw data, mount on EC2 instances

---

### Question 300: Legacy Application Migration
**Scenario:** Legacy application migration from on-premises to AWS due to hardware capacity constraints. Application runs 24/7, database storage continues to grow over time.

**Question:** What should solutions architect do MOST cost-effectively?

**Options:**
- A) Migrate application layer to EC2 Spot Instances, data storage layer to S3
- B) Migrate application layer to EC2 Reserved Instances, data storage layer to RDS On-Demand Instances
- C) Migrate application layer to EC2 Reserved Instances, data storage layer to Aurora Reserved Instances
- D) Migrate application layer to EC2 On-Demand Instances, data storage layer to RDS Reserved Instances

---

### Question 301: Data Migration with Bandwidth Control
**Scenario:** University research laboratory needs to migrate 30 TB from on-premises Windows file server to Amazon FSx for Windows File Server. 1 Gbps network link shared with other departments. Need maximum performance while controlling bandwidth to minimize impact. Migration must complete within 5 days.

**Question:** Which AWS solution meets these requirements?

**Options:**
- A) AWS Snowcone
- B) Amazon FSx File Gateway
- C) AWS DataSync
- D) AWS Transfer Family

---

### Question 302: Mobile Video App Performance
**Scenario:** Mobile app for streaming slow-motion video clips. App captures and uploads raw format videos to S3 bucket, retrieves directly from S3. Videos large in raw format causing buffering and playback issues. Need maximum performance and scalability with minimal operational overhead.

**Question:** Which combination of solutions meets requirements? (Choose two.)

**Options:**
- A) Deploy Amazon CloudFront for content delivery and caching
- B) Use AWS DataSync to replicate video files across AWS Regions in other S3 buckets
- C) Use Amazon Elastic Transcoder to convert video files to more appropriate formats
- D) Deploy Auto Scaling group of EC2 instances in Local Zones for content delivery and caching
- E) Deploy Auto Scaling group of EC2 instances to convert video files to more appropriate formats

---

### Question 303: ECS Fargate Cost Optimization
**Scenario:** New application deployed on ECS cluster using Fargate launch type. Monitoring CPU and memory usage expecting high traffic at launch. Want to reduce costs when utilization decreases.

**Question:** What should solutions architect recommend?

**Options:**
- A) Use Amazon EC2 Auto Scaling to scale at certain periods based on previous traffic patterns
- B) Use AWS Lambda function to scale ECS based on metric breaches triggering CloudWatch alarm
- C) Use Amazon EC2 Auto Scaling with simple scaling policies when ECS metrics breach CloudWatch alarms
- D) Use AWS Application Auto Scaling with target tracking policies when ECS metrics breach CloudWatch alarms

---

### Question 304: Cross-Region NFS Data Transfer
**Scenario:** Company created disaster recovery site in different AWS Region. Need to transfer large amounts of data between NFS file systems in two Regions on periodic basis.

**Question:** Which solution meets requirements with LEAST operational overhead?

**Options:**
- A) Use AWS DataSync
- B) Use AWS Snowball devices
- C) Set up SFTP server on Amazon EC2
- D) Use AWS Database Migration Service (AWS DMS)

---

### Question 305: SMB Shared Storage Solution
**Scenario:** Designing shared storage solution for gaming application hosted in AWS Cloud. Need ability to use SMB clients to access data. Solution must be fully managed.

**Question:** Which AWS solution meets these requirements?

**Options:**
- A) Create AWS DataSync task sharing data as mountable file system, mount to application server
- B) Create Amazon EC2 Windows instance, install and configure Windows file share role, connect application server
- C) Create Amazon FSx for Windows File Server file system, attach to origin server, connect application server
- D) Create Amazon S3 bucket, assign IAM role to application for S3 access, mount S3 bucket to application server

---

### Question 306: In-Memory Database Network Design
**Scenario:** In-memory database for latency-sensitive application on EC2 instances. Application processes 100,000+ transactions per minute requiring high network throughput. Need cost-effective network design minimizing data transfer charges.

**Question:** Which solution meets these requirements?

**Options:**
- A) Launch all EC2 instances in same AZ within same Region, specify placement group with cluster strategy
- B) Launch all EC2 instances in different AZs within same Region, specify placement group with partition strategy
- C) Deploy Auto Scaling group launching EC2 instances in different AZs based on network utilization target
- D) Deploy Auto Scaling group with step scaling policy launching EC2 instances in different AZs

---

### Question 307: Hybrid Storage with Local Access
**Scenario:** Company primarily running application servers on-premises wants to migrate to AWS. Minimize need to scale iSCSI storage on-premises. Want only recently accessed data stored locally.

**Question:** Which AWS solution meets these requirements?

**Options:**
- A) Amazon S3 File Gateway
- B) AWS Storage Gateway Tape Gateway
- C) AWS Storage Gateway Volume Gateway stored volumes
- D) AWS Storage Gateway Volume Gateway cached volumes

---

### Question 308: RDS Cost Optimization with Trusted Advisor
**Scenario:** Company with multiple AWS accounts using consolidated billing. Running several active high performance RDS for Oracle On-Demand DB instances for 90 days. Finance team has Trusted Advisor access in consolidated billing and all other accounts. Need to review appropriate Trusted Advisor check to reduce RDS costs.

**Question:** Which combination of steps should finance team take? (Choose two.)

**Options:**
- A) Use Trusted Advisor recommendations from account where RDS instances are running
- B) Use Trusted Advisor recommendations from consolidated billing account to see all RDS instance checks
- C) Review Trusted Advisor check for Amazon RDS Reserved Instance Optimization
- D) Review Trusted Advisor check for Amazon RDS Idle DB Instances
- E) Review Trusted Advisor check for Amazon Redshift Reserved Node Optimization

---

### Question 309: S3 Storage Cost Optimization
**Scenario:** Solutions architect needs to optimize storage costs by identifying S3 buckets no longer being accessed or rarely accessed.

**Question:** Which solution accomplishes this goal with LEAST operational overhead?

**Options:**
- A) Analyze bucket access patterns using S3 Storage Lens dashboard for advanced activity metrics
- B) Analyze bucket access patterns using S3 dashboard in AWS Management Console
- C) Turn on CloudWatch BucketSizeBytes metric, analyze with Amazon Athena
- D) Turn on AWS CloudTrail for S3 object monitoring, analyze with CloudWatch Logs

---

### Question 310: Global Dataset Distribution
**Scenario:** Company sells datasets to AI/ML research customers. Large formatted files stored in S3 bucket in us-east-1. Web application on multiple EC2 instances behind ALB for purchases. Customers receive S3 signed URLs after purchase. Customers distributed across North America and Europe. Want to reduce data transfer costs while maintaining/improving performance.

**Question:** What should solutions architect do?

**Options:**
- A) Configure S3 Transfer Acceleration on existing bucket, direct requests to Transfer Acceleration endpoint, continue using S3 signed URLs
- B) Deploy CloudFront distribution with existing S3 bucket as origin, direct requests to CloudFront URL, switch to CloudFront signed URLs
- C) Set up second S3 bucket in eu-central-1 with Cross-Region Replication, direct requests to closest Region, continue using S3 signed URLs
- D) Modify web application for streaming datasets to end users, configure to read from existing S3 bucket, implement access control in application

---

### Question 311: Insurance Quote Processing System
**Scenario:** Web application processing insurance quotes. Users request quotes separated by quote type, must be responded to within 24 hours, must not get lost. Solution must maximize operational efficiency and minimize maintenance.

**Question:** Which solution meets these requirements?

**Options:**
- A) Create multiple Kinesis data streams by quote type, configure web application to send to proper stream, configure backend servers to use KCL to pool messages
- B) Create Lambda function and SNS topic for each quote type, subscribe Lambda to associated SNS topic, configure application to publish to appropriate SNS topic
- C) Create single SNS topic, subscribe SQS queues to SNS topic, configure SNS message filtering to publish to proper SQS queue by quote type, configure backend servers to use own SQS queue
- D) Create multiple Kinesis Data Firehose delivery streams by quote type to deliver to OpenSearch Service cluster, configure application to send to proper stream, configure backend servers to search and process from OpenSearch

---

### Question 312: Application Backup and Recovery
**Scenario:** Application runs on several EC2 instances, each with multiple EBS data volumes attached. Application's EC2 configuration and data need nightly backup. Application must be recoverable in different AWS Region.

**Question:** Which solution meets requirements MOST operationally efficiently?

**Options:**
- A) Write Lambda function scheduling nightly EBS snapshots and copying to different Region
- B) Create AWS Backup plan for nightly backups, copy to another Region, add EC2 instances as resources
- C) Create AWS Backup plan for nightly backups, copy to another Region, add EBS volumes as resources
- D) Write Lambda function scheduling nightly EBS snapshots and copying to different AZ

---

### Question 313: Mobile Content Streaming Platform
**Scenario:** Building mobile app on AWS to expand reach to millions of users. Need platform for authorized users to watch company content on mobile devices.

**Question:** What should solutions architect recommend?

**Options:**
- A) Publish content to public S3 bucket, use AWS KMS keys to stream content
- B) Set up IPsec VPN between mobile app and AWS environment to stream content
- C) Use Amazon CloudFront, provide signed URLs to stream content
- D) Set up AWS Client VPN between mobile app and AWS environment to stream content

---

### Question 314: Global Database Migration
**Scenario:** On-premises MySQL database used by global sales team with infrequent access patterns. Sales team requires minimal downtime. Database administrator wants to migrate without selecting particular instance type anticipating more users in future.

**Question:** Which service should solutions architect recommend?

**Options:**
- A) Amazon Aurora MySQL
- B) Amazon Aurora Serverless for MySQL
- C) Amazon Redshift Spectrum
- D) Amazon RDS for MySQL

---

### Question 315: EC2 Vulnerability Scanning
**Scenario:** Company experienced breach affecting on-premises applications due to custom application vulnerabilities. Migrating applications to EC2 instances. Want solution actively scanning for vulnerabilities on EC2 instances with detailed findings report.

**Question:** Which solution meets these requirements?

**Options:**
- A) Deploy AWS Shield to scan EC2 instances, create Lambda function to log findings to CloudTrail
- B) Deploy Amazon Macie and Lambda functions to scan EC2 instances, log findings to CloudTrail
- C) Turn on Amazon GuardDuty, deploy GuardDuty agents to EC2 instances, configure Lambda function to automate report generation and distribution
- D) Turn on Amazon Inspector, deploy Inspector agent to EC2 instances, configure Lambda function to automate report generation and distribution

---

### Question 316: SQS Processing Cost Optimization
**Scenario:** Company uses EC2 instance to run script polling and processing SQS queue messages. Want to reduce operational costs while maintaining ability to process growing number of messages.

**Question:** What should solutions architect recommend?

**Options:**
- A) Increase EC2 instance size to process messages faster
- B) Use Amazon EventBridge to turn off EC2 instance when underutilized
- C) Migrate script on EC2 instance to AWS Lambda function with appropriate runtime
- D) Use AWS Systems Manager Run Command to run script on demand

---

### Question 317: Legacy CSV to SQL Data Processing
**Scenario:** Legacy application produces CSV data stored in S3. New COTS application can perform complex SQL queries on data in Redshift and S3 only, but cannot process CSV files. Cannot update legacy application to produce different format.

**Question:** Which solution meets requirements with LEAST operational overhead?

**Options:**
- A) Create AWS Glue ETL job running on schedule to process CSV files and store in Redshift
- B) Develop Python script on EC2 instances to convert CSV to SQL files, invoke on cron schedule to store in S3
- C) Create Lambda function and DynamoDB table, use S3 event to invoke Lambda, configure ETL job to process CSV and store in DynamoDB
- D) Use EventBridge to launch EMR cluster weekly, configure ETL job to process CSV files and store in Redshift table

---

### Question 318: IT Environment Audit and Compliance
**Scenario:** Company migrated entire IT environment to AWS Cloud. Users provisioning oversized EC2 instances and modifying security group rules without proper change control process. Need strategy to track and audit inventory and configuration changes.

**Question:** Which actions should solutions architect take? (Choose two.)

**Options:**
- A) Enable AWS CloudTrail and use it for auditing
- B) Use data lifecycle policies for Amazon EC2 instances
- C) Enable AWS Trusted Advisor and reference security dashboard
- D) Enable AWS Config and create rules for auditing and compliance purposes
- E) Restore previous resource configurations with CloudFormation template

---

### Question 319: Secure EC2 Access Without Shared Keys
**Scenario:** Company has hundreds of EC2 Linux-based instances managed with shared SSH keys. After audit, security team mandating removal of all shared keys. Need secure access solution with least administrative overhead.

**Question:** Which solution meets this requirement?

**Options:**
- A) Use AWS Systems Manager Session Manager to connect to EC2 instances
- B) Use AWS STS to generate one-time SSH keys on demand
- C) Allow shared SSH access to bastion instances, configure other instances to allow SSH only from bastion instances
- D) Use Amazon Cognito custom authorizer to authenticate users, invoke Lambda function to generate temporary SSH key

---

### Question 320: Real-time Data Ingestion and Querying
**Scenario:** Fleet of EC2 instances ingesting JSON data from on-premises sources at up to 1 MB/s. When EC2 instance reboots, in-flight data is lost. Data science team wants to query ingested data in near-real time.

**Question:** Which solution provides near-real-time querying that is scalable with minimal data loss?

**Options:**
- A) Publish data to Kinesis Data Streams, use Kinesis Data Analytics to query data
- B) Publish data to Kinesis Data Firehose with Redshift as destination, use Redshift to query data
- C) Store ingested data in EC2 instance store, publish to Kinesis Data Firehose with S3 as destination, use Athena to query data
- D) Store ingested data in EBS volume, publish to ElastiCache for Redis, subscribe to Redis channel to query data

---

### Question 321: S3 Encryption Enforcement
**Scenario:** Ensure all objects uploaded to Amazon S3 bucket are encrypted.

**Question:** What should solutions architect do?

**Options:**
- A) Update bucket policy to deny if PutObject does not have s3:x-amz-acl header set
- B) Update bucket policy to deny if PutObject does not have s3:x-amz-acl header set to private
- C) Update bucket policy to deny if PutObject does not have aws:SecureTransport header set to true
- D) Update bucket policy to deny if PutObject does not have x-amz-server-side-encryption header set

---

### Question 322: Asynchronous Image Processing
**Scenario:** Multi-tier application where users upload images from mobile device. Application generates thumbnail (can take up to 60 seconds) and returns confirmation message. Company wants faster response time confirming original image receipt while thumbnail generation happens asynchronously.

**Question:** What should solutions architect do?

**Options:**
- A) Write custom Lambda function to generate thumbnail and alert user, use image upload process as event source to invoke Lambda
- B) Create AWS Step Functions workflow to handle orchestration between application tiers and alert user when thumbnail generation complete
- C) Create Amazon SQS message queue, place message on queue for thumbnail generation as images uploaded, alert user through application message that image was received
- D) Create Amazon SNS notification topics and subscriptions - one for thumbnail generation after upload, second to message user's mobile app after thumbnail generation complete

---

### Question 323: Badge Reader Message Processing
**Scenario:** Company facility has badge readers at every entrance sending messages over HTTPS when badges scanned. Need system to process messages from sensors with high availability, results available for security team analysis.

**Question:** Which system architecture should solutions architect recommend?

**Options:**
- A) Launch EC2 instance as HTTPS endpoint to process messages, configure to save results to S3 bucket
- B) Create HTTPS endpoint in API Gateway, configure to invoke Lambda function to process messages and save results to DynamoDB table
- C) Use Route 53 to direct incoming sensor messages to Lambda function, configure to process messages and save results to DynamoDB table
- D) Create gateway VPC endpoint for S3, configure Site-to-Site VPN from facility network to VPC for direct sensor data writing to S3 bucket

---

### Question 324: Disaster Recovery for File Storage
**Scenario:** Company wants disaster recovery plan for primary on-premises file storage volume mounted from iSCSI device. Volume holds hundreds of TB of data. End users need immediate access to all file types from on-premises systems without latency.

**Question:** Which solution meets requirements with LEAST change to existing infrastructure?

**Options:**
- A) Provision Amazon S3 File Gateway as on-premises VM with 10 TB local cache, modify applications to access files through NFS protocol, recover by provisioning EC2 instance and mounting S3 bucket
- B) Provision AWS Storage Gateway tape gateway, use data backup solution to back up to virtual tape library with nightly runs, recover by provisioning EC2 instance and restoring data to EBS volume
- C) Provision AWS Storage Gateway Volume Gateway cached volume with 10 TB local cache, mount to existing file server using iSCSI and copy files, configure scheduled snapshots, recover by restoring snapshot to EBS volume on EC2 instance
- D) Provision AWS Storage Gateway Volume Gateway stored volume with same disk space as existing storage, mount to existing file server using iSCSI and copy files, configure scheduled snapshots, recover by restoring snapshot to EBS volume on EC2 instance

---

### Question 325: Cognito Authentication Access Issues
**Scenario:** Web application hosted from S3 bucket uses Amazon Cognito as identity provider to authenticate users and return JWT providing access to protected resources in another S3 bucket. Upon deployment, users report errors and cannot access protected content.

**Question:** Which solution meets these requirements?

**Options:**
- A) Update Amazon Cognito identity pool to assume proper IAM role for access to protected content
- B) Update S3 ACL to allow application to access protected content
- C) Redeploy application to Amazon S3 to prevent eventually consistent reads affecting user access to protected content
- D) Update Amazon Cognito pool to use custom attribute mappings within identity pool and grant users proper permissions to access protected content

---

## Answer Key

```
## Answer Key

| Question | Answer | Key Concepts |
|----------|--------|--------------|
| 261 | A, C | CloudFront caching, Lambda@Edge, User-Agent header |
| 262 | A | VPC peering, Cost optimization, Security groups |
| 263 | A, D | ECS cluster, Fargate launch type, Managed services |
| 264 | D | Application Load Balancer, Health checks, Route 53 |
| 265 | C | Private subnets, ALB origin, CloudFront security |
| 266 | A | AWS Global Accelerator, Regional endpoints, Gaming latency |
| 267 | D | Kinesis Data Firehose, Kinesis Data Analytics, Minimal overhead |
| 268 | A | ElastiCache, Database read performance, Caching layer |
| 269 | C | RDS read replica, Read-only queries, Minimal changes |
| 270 | A | Client-side encryption, Data encryption in transit |
| 271 | C | Scheduled scaling, Auto Scaling groups, Cost optimization |
| 272 | B | CloudFront distribution, Accept-Language header, Global performance |
| 273 | B | Aurora global database, Warm standby, Low RTO |
| 274 | B | AMI backups, CloudFormation automation, Operational efficiency |
| 275 | A | Scheduled scaling actions, Morning performance, Cost minimization |
| 276 | A, D | RDS storage Auto Scaling, CPU-based scaling metrics |
| 277 | D | Amazon S3 storage, EBS processing, Cost-effective solution |
| 278 | B, E | DynamoDB hierarchical data, Macie PII detection, SNS notifications |
| 279 | A | AWS Backup plans, Lifecycle policies, Compliance requirements |
| 280 | B | Amazon Athena SQL queries, QuickSight visualizations |
| 281 | A | Multi-AZ deployment, RPO requirements, Database availability |
| 282 | B | Security group references, ALB to EC2 security |
| 283 | D | FSx for NetApp ONTAP, NFS and SMB support |
| 284 | B | Cost Explorer reports, Billing by user |
| 285 | B | API Gateway, Lambda backend, SES integration |
| 286 | C | CloudFront cache invalidation, Static website updates |
| 287 | B | FSx for Windows File Server, SQL Server features |
| 288 | C | Amazon EFS, Shared file system, Linux web servers |
| 289 | B | IAM roles, Lambda security, Least privilege |
| 290 | C | On-Demand and Spot instances, Cost optimization, Auto Scaling |
| 291 | A, B | CloudFront signed cookies and URLs, Access control |
| 292 | A, B | Kinesis streaming, AWS Glue transformation, Athena queries |
| 293 | D | Storage Gateway stored volumes, Hybrid backup |
| 294 | B | VPC endpoints, Private S3 access, No internet traffic |
| 295 | B | S3 Object Lambda, PII processing, Minimal overhead |
| 296 | D | VPC CIDR blocks, Peering requirements, Non-overlapping ranges |
| 297 | B | Auto Scaling groups, Target tracking, CPU optimization |
| 298 | C | Multi-AZ subnets, RDS Multi-AZ deployment, High availability |
| 299 | B | FSx for Lustre, Persistent SSD, High-performance computing |
| 300 | C | Reserved Instances, Aurora Reserved, 24/7 workloads |
| 301 | C | AWS DataSync, Bandwidth control, Data migration |
| 302 | A, C | CloudFront CDN, Elastic Transcoder, Video optimization |
| 303 | D | Application Auto Scaling, ECS Fargate, Target tracking |
| 304 | A | AWS DataSync, Cross-region transfers, Minimal overhead |
| 305 | C | FSx for Windows File Server, SMB protocol, Fully managed |
| 306 | A | Placement groups cluster strategy, Same AZ, Network performance |
| 307 | D | Storage Gateway cached volumes, Local access, Hybrid storage |
| 308 | A, C | Account-specific Trusted Advisor, RDS Reserved Instance optimization |
| 309 | A | S3 Storage Lens, Access pattern analysis, Cost optimization |
| 310 | B | CloudFront distribution, Signed URLs, Global content delivery |
| 311 | C | SNS with SQS, Message filtering, Quote processing |
| 312 | B | AWS Backup, EC2 instances as resources, Cross-region recovery |
| 313 | C | CloudFront signed URLs, Mobile content streaming, Authorized access |
| 314 | B | Aurora Serverless, Auto scaling, Infrequent access patterns |
| 315 | D | Amazon Inspector, Vulnerability scanning, Agent deployment |
| 316 | C | Lambda functions, SQS processing, Cost optimization |
| 317 | A | AWS Glue ETL, CSV to Redshift, Scheduled processing |
| 318 | A, D | CloudTrail auditing, AWS Config compliance, Change tracking |
| 319 | A | Systems Manager Session Manager, SSH key elimination |
| 320 | A | Kinesis Data Streams, Real-time analytics, Data loss prevention |
| 321 | D | S3 bucket policy, Server-side encryption enforcement |
| 322 | C | SQS message queues, Asynchronous processing, Fast response |
| 323 | B | API Gateway HTTPS endpoint, Lambda processing, DynamoDB storage |
| 324 | C | Storage Gateway cached volumes, iSCSI protocol, Disaster recovery |
| 325 | A | Cognito identity pool, IAM roles, Protected content access |


```

---

## Study Tips

1. **Focus on Cost Optimization:** Many questions test your ability to choose the most cost-effective solution
2. **Security Best Practices:** Always choose solutions that follow the principle of least privilege
3. **Operational Efficiency:** Prefer managed services over self-managed infrastructure when possible
4. **Performance:** Consider latency, throughput, and caching strategies
5. **Disaster Recovery:** Understand RTO/RPO requirements and appropriate DR strategies

## Contributing

Feel free to contribute additional questions, corrections, or improvements to this repository. Please ensure all questions follow the AWS SAA exam format and include proper explanations for answers.

## License

This content is provided for educational purposes. Please refer to AWS documentation for the most current information on services and best practices.