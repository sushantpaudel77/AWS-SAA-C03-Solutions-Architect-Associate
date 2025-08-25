# AWS Solutions Architect Practice Questions

A comprehensive collection of AWS Solutions Architect Associate practice questions covering various AWS services and architectural patterns.

## Table of Contents

- [Storage Solutions](#storage-solutions)
- [Compute and Auto Scaling](#compute-and-auto-scaling)
- [Database Solutions](#database-solutions)
- [Security and Access Management](#security-and-access-management)
- [Cost Optimization](#cost-optimization)
- [High Availability and Disaster Recovery](#high-availability-and-disaster-recovery)
- [Migration and Data Transfer](#migration-and-data-transfer)
- [Monitoring and Analytics](#monitoring-and-analytics)

---

## Storage Solutions

### Question 651: S3 Lifecycle Management
**Scenario:** A company stores large volume image files in S3 with specific access patterns:
- First 180 days: Readily available
- Next 180 days: Infrequently accessed
- After 360 days: Archived but instantly available
- After 5 years: Auditor access only (12-hour retrieval acceptable)

**Options:**
1. S3 Standard → S3 One Zone-IA (180d) → S3 Glacier Instant Retrieval (360d) → S3 Glacier Deep Archive (5y)
2. S3 Standard → S3 One Zone-IA (180d) → S3 Glacier Flexible Retrieval (360d) → S3 Glacier Deep Archive (5y)
3. S3 Standard → S3 Standard-IA (180d) → S3 Glacier Instant Retrieval (360d) → S3 Glacier Deep Archive (5y) ✅
4. S3 Standard → S3 Standard-IA (180d) → S3 Glacier Flexible Retrieval (360d) → S3 Glacier Deep Archive (5y)

**Key Concepts:** S3 Storage Classes, Lifecycle Policies, Cost Optimization

---

### Question 656: Image Storage for Historical Website
**Scenario:** Website storing historical images with infrequent access (1-2 times per year). Need highly available, cost-effective solution.

**Options:**
1. Amazon EBS with EC2 web server
2. Amazon EFS with EC2 web server
3. Amazon S3 Standard with static website hosting
4. Amazon S3 Standard-IA with static website hosting ✅

**Key Concepts:** S3 Static Website Hosting, Storage Classes, Cost Optimization

---

### Question 673: SMB File Server Migration
**Scenario:** SMB file server with large files accessed frequently for 7 days, then max 24-hour retrieval time acceptable.

**Options:**
1. AWS DataSync for files older than 7 days
2. Amazon S3 File Gateway with S3 Lifecycle to Glacier Deep Archive ✅
3. Amazon FSx File Gateway with S3 Lifecycle
4. Direct S3 access with Glacier Flexible Retrieval

**Key Concepts:** Storage Gateway, File Gateway, S3 Lifecycle Policies

---

### Question 675: EBS Snapshot Protection
**Scenario:** Daily EBS snapshots for compliance. Prevent accidental deletion without changing admin rights.

**Options:**
1. IAM role with delete permissions on separate EC2 instance
2. IAM policy denying snapshot deletion
3. Tags with Recycle Bin retention rules ✅
4. Lock EBS snapshots

**Key Concepts:** EBS Snapshots, Recycle Bin, Data Protection

---

## Compute and Auto Scaling

### Question 652: EMR Cluster Configuration
**Scenario:** 6-hour daily data workload, cannot lose data, need cost-effective EMR cluster.

**Options:**
1. Long-running: Primary/Core On-Demand, Task Spot ✅
2. Transient: Primary/Core On-Demand, Task Spot
3. Transient: Primary On-Demand, Core/Task Spot
4. Long-running: Primary On-Demand, Core/Task Spot

**Key Concepts:** EMR Cluster Types, Spot Instances, Data Persistence

---

### Question 660: Auto Scaling for Peak Hours
**Scenario:** Application performance issues at start of daily peak hours, normalizes after 2-3 hours.

**Options:**
1. Application Load Balancer configuration
2. Dynamic scaling based on memory utilization
3. Dynamic scaling based on CPU utilization
4. Scheduled scaling before peak hours ✅

**Key Concepts:** Auto Scaling Policies, Scheduled Scaling, Predictive Scaling

---

### Question 664: Elastic Beanstalk Scaling
**Scenario:** On-premises app with 10x CPU spikes during monthly latency issues, migrate to Beanstalk.

**Options:**
1. Burstable instances (unlimited mode) with request-based scaling ✅
2. Compute optimized instances with request-based scaling
3. Compute optimized instances with scheduled scaling
4. Burstable instances with predictive scaling

**Key Concepts:** Elastic Beanstalk, Instance Types, Auto Scaling

---

### Question 677: EKS Development Cluster
**Scenario:** Need cost-effective EKS development cluster for infrequent resilience testing.

**Options:**
1. Managed node group with Spot Instances only ✅
2. Two managed node groups (On-Demand + Spot)
3. Auto Scaling group with Spot Instances
4. Managed node group with On-Demand only

**Key Concepts:** Amazon EKS, Managed Node Groups, Spot Instances

---

## Database Solutions

### Question 654: Web Application Redesign
**Scenario:** EC2 with Apache, PHP, and local Redis. Need highly available, managed solution.

**Options:**
1. Elastic Beanstalk in public subnet
2. Lambda + API Gateway + ElastiCache Redis
3. Keep EC2 backend, ElastiCache Multi-AZ, S3 frontend
4. CloudFront + S3, ALB + ECS Fargate, ElastiCache Multi-AZ ✅

**Key Concepts:** High Availability, Managed Services, Container Services

---

### Question 661: Database Connection Scaling
**Scenario:** Applications connecting to RDS, scale on weekends and peak times.

**Options:**
1. DynamoDB with connection pooling
2. Amazon RDS Proxy with target group ✅
3. Custom proxy on EC2
4. Lambda function for connection pooling

**Key Concepts:** RDS Proxy, Connection Pooling, Database Scaling

---

### Question 666: MySQL High Availability
**Scenario:** Stateless Python app with MySQL on single EC2, need HA without code changes.

**Options (Choose 2):**
1. Internet gateway in each AZ
2. Migrate to RDS Multi-AZ ✅
3. Migrate to DynamoDB with auto scaling
4. DataSync for database synchronization
5. ALB with Auto Scaling across AZs ✅

**Key Concepts:** RDS Multi-AZ, Application Load Balancer, High Availability

---

### Question 669: RDS Password Management
**Scenario:** Secure master password rotation every 30 days for RDS PostgreSQL.

**Options:**
1. EventBridge + Lambda scheduled rotation
2. AWS CLI modify-db-instance command
3. AWS Secrets Manager integration ✅
4. Systems Manager Parameter Store integration

**Key Concepts:** AWS Secrets Manager, RDS Integration, Password Rotation

---

### Question 674: RDS Read Performance
**Scenario:** Web app with RDS PostgreSQL, heavy read load during high traffic.

**Options (Choose 2):**
1. Auto scaling for DB instance
2. Read replica with read traffic distribution ✅
3. Multi-AZ with standby read traffic
4. ElastiCache cluster for query caching ✅
5. Same AZ provisioning for EC2 and DB

**Key Concepts:** RDS Read Replicas, ElastiCache, Database Performance

---

## Security and Access Management

### Question 653: Resource Tagging Automation
**Scenario:** Tag all resources with cost center ID of creator using RDS user mapping.

**Options:**
1. SCP requiring cost center tags
2. Lambda + EventBridge + CloudTrail for tagging ✅
3. CloudFormation stack with scheduled Lambda
4. Lambda with default tagging on missing tags

**Key Concepts:** CloudTrail, EventBridge, Lambda Automation, Resource Tagging

---

### Question 655: WAF with Session Affinity
**Scenario:** Auto Scaling web app needing public endpoint, WAF, and sticky sessions.

**Options (Choose 2):**
1. Public Network Load Balancer
2. Gateway Load Balancer
3. Public Application Load Balancer ✅
4. Second target group with Elastic IPs
5. Web ACL associated with endpoint ✅

**Key Concepts:** Application Load Balancer, AWS WAF, Session Affinity

---

### Question 657: Security Group Management
**Scenario:** Centralize security group CIDR range management across organization.

**Options:**
1. VPC security groups in management account
2. Customer managed prefix list shared via AWS RAM ✅
3. AWS managed prefix list with Security Hub
4. Firewall Manager common security group policy

**Key Concepts:** VPC Prefix Lists, AWS RAM, Centralized Management

---

### Question 663: ECS Data Access Control
**Scenario:** Ensure only ECS cluster can access RDS MySQL and S3 bucket with sensitive data.

**Options:**
1. Customer managed KMS key for encryption
2. AWS managed KMS key with S3 bucket policy
3. S3 bucket policy + RDS VPC endpoint + security groups ✅
4. VPC endpoints for both RDS and S3

**Key Concepts:** VPC Endpoints, Security Groups, IAM Roles

---

### Question 668: Development Team Resource Tagging
**Scenario:** Enforce predefined application name tags for development team resources.

**Options:**
1. IAM group with conditional Allow policy
2. Cross-account role with Deny policy
3. Resource Groups for tag validation
4. Organizations tag policy with allowed names ✅

**Key Concepts:** AWS Organizations, Tag Policies, Resource Governance

---

### Question 678: S3 Encryption Key Management
**Scenario:** Full control over encryption key creation, rotation, and disabling for S3.

**Options:**
1. SSE-S3 with Amazon managed keys
2. Customer managed KMS key with SSE-KMS ✅
3. AWS managed KMS key with SSE-KMS
4. Client-side encryption on EC2

**Key Concepts:** AWS KMS, Customer Managed Keys, S3 Encryption

---

### Question 681: EBS Encryption with Key Rotation
**Scenario:** Encrypt all EBS volumes at rest with controllable key rotation.

**Options:**
1. Customer managed key for EBS encryption ✅
2. AWS managed key with automatic rotation
3. External KMS key with imported material
4. AWS owned key for encryption

**Key Concepts:** EBS Encryption, KMS Customer Managed Keys, Key Rotation

---

### Question 682: Automated Encryption Compliance
**Scenario:** Enforce data encryption at rest with automated detection and remediation.

**Options:**
1. IAM policy + AWS Config + Systems Manager ✅
2. AWS KMS + Lambda + EventBridge
3. Amazon Macie + Systems Manager Automation
4. Amazon Inspector + Systems Manager Automation

**Key Concepts:** AWS Config, Systems Manager, Compliance Automation

---

## Cost Optimization

### Question 662: EBS Storage Cost Optimization
**Scenario:** Monthly increases in EBS storage and snapshot costs without additional storage purchases.

**Options:**
1. CloudWatch Logs monitoring + Elastic Volumes
2. Custom script monitoring + Elastic Volumes
3. Delete expired and unused snapshots
4. Delete nonessential snapshots + Data Lifecycle Manager ✅

**Key Concepts:** EBS Snapshots, Data Lifecycle Manager, Cost Optimization

---

### Question 670: DynamoDB Cost Optimization
**Scenario:** 4-hour weekly tests on DynamoDB table with known read/write operations.

**Options:**
1. On-demand mode with appropriate capacity
2. Provisioned mode with appropriate capacity ✅
3. DynamoDB reserved capacity (1-year)
4. DynamoDB reserved capacity (3-year)

**Key Concepts:** DynamoDB Capacity Modes, Cost Optimization

---

### Question 671: Unusual Spending Prevention
**Scenario:** Monitor costs and notify stakeholders of unusual spending patterns.

**Options:**
1. AWS Budgets zero spend budget
2. AWS Cost Anomaly Detection monitor ✅
3. AWS Pricing Calculator estimates
4. CloudWatch cost monitoring

**Key Concepts:** Cost Anomaly Detection, Cost Monitoring, Budgets

---

## High Availability and Disaster Recovery

### Question 658: HPC Storage Migration
**Scenario:** Migrate latency-sensitive HPC workloads with NFS and SMB multi-protocol access.

**Options (Choose 2):**
1. Compute optimized EC2 in cluster placement group ✅
2. Compute optimized EC2 in partition placement group
3. Amazon FSx for Lustre file system
4. Amazon FSx for OpenZFS file system
5. Amazon FSx for NetApp ONTAP file system ✅

**Key Concepts:** HPC, Placement Groups, FSx File Systems, Multi-protocol Access

---

### Question 679: VM Backup Retention
**Scenario:** On-premises VM backups to S3, 30-day retention with automatic deletion.

**Options (Choose 3):**
1. S3 bucket with Object Lock
2. S3 bucket with object versioning ✅
3. Default retention period of 30 days
4. S3 Lifecycle policy for protection
5. S3 Lifecycle policy for expiration ✅
6. Backup solution tagging with retention ✅

**Key Concepts:** S3 Object Versioning, Lifecycle Policies, Backup Retention

---

## Migration and Data Transfer

### Question 659: Large Data Transfer
**Scenario:** Transfer 50 TB securely within 2 weeks, existing Site-to-Site VPN 90% utilized.

**Options:**
1. AWS DataSync with VPC endpoint
2. AWS Direct Connect
3. AWS Snowball Edge Storage Optimized ✅
4. AWS Storage Gateway

**Key Concepts:** Data Transfer Services, Snowball Family, Network Capacity

---

### Question 667: Secure S3 Access
**Scenario:** Secure S3 access from AWS Region and on-premises via Direct Connect, no internet traversal.

**Options:**
1. Gateway endpoints for S3 ✅
2. Transit Gateway for S3 access
3. Interface endpoints for S3
4. AWS KMS for secure access

**Key Concepts:** VPC Endpoints, Gateway Endpoints, Direct Connect

---

### Question 680: Continuous File Synchronization
**Scenario:** Copy files continuously from S3 to EFS and another S3 bucket, overwrite only if changed.

**Options:**
1. DataSync with changed data transfer mode ✅
2. Lambda function with S3 event notifications
3. DataSync with all data transfer mode
4. EC2 instance with synchronization script

**Key Concepts:** AWS DataSync, File Synchronization, Transfer Modes

---

## Monitoring and Analytics

### Question 672: Clickstream Data Analysis
**Scenario:** Analyze large amounts of new clickstream data in S3 quickly with minimal overhead.

**Options:**
1. External tables in Spark catalog + AWS Glue jobs
2. AWS Glue crawler + Amazon Athena ✅
3. External tables in Hive metastore + EMR Spark jobs
4. AWS Glue crawler + Kinesis Data Analytics

**Key Concepts:** AWS Glue, Amazon Athena, Data Cataloging, Serverless Analytics

---

### Question 676: VPC Flow Logs Analysis
**Scenario:** Capture VPC network traffic in near real-time and send to OpenSearch Service.

**Options:**
1. CloudWatch Logs + Kinesis Data Streams
2. CloudWatch Logs + Kinesis Data Firehose ✅
3. CloudTrail + Kinesis Data Streams
4. CloudTrail + Kinesis Data Firehose

**Key Concepts:** VPC Flow Logs, Kinesis Data Firehose, OpenSearch Service

---

## Answer Key Summary

| Question | Answer | Topic |
|----------|---------|-------|
| 651 | 3 | S3 Lifecycle Management |
| 652 | 1 | EMR Cluster Configuration |
| 653 | 2 | Resource Tagging Automation |
| 654 | 4 | Web Application Architecture |
| 655 | 3,5 | Load Balancer + WAF |
| 656 | 4 | S3 Storage Classes |
| 657 | 2 | Security Group Management |
| 658 | 1,5 | HPC Migration |
| 659 | 3 | Data Transfer |
| 660 | 4 | Auto Scaling |
| 661 | 2 | Database Scaling |
| 662 | 4 | Cost Optimization |
| 663 | 3 | Access Control |
| 664 | 1 | Elastic Beanstalk |
| 665 | 2 | Infrastructure as Code |
| 666 | 2,5 | High Availability |
| 667 | 1 | VPC Endpoints |
| 668 | 4 | Tag Policies |
| 669 | 3 | Password Management |
| 670 | 2 | DynamoDB Pricing |
| 671 | 2 | Cost Monitoring |
| 672 | 2 | Data Analytics |
| 673 | 2 | File Storage |
| 674 | 2,4 | Database Performance |
| 675 | 3 | Data Protection |
| 676 | 2 | Network Monitoring |
| 677 | 1 | EKS Cost Optimization |
| 678 | 2 | Encryption Management |
| 679 | 2,5,6 | Backup Retention |
| 680 | 1 | File Synchronization |
| 681 | 1 | EBS Encryption |
| 682 | 1 | Compliance Automation |

---

