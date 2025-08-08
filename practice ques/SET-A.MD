# AWS Solutions Architect Associate (SAA) Practice Questions

This repository contains 25 comprehensive practice questions for the AWS Solutions Architect Associate certification exam. Each question focuses on real-world scenarios and AWS best practices.

---

## Questions 1-5: Storage & Data Transfer

### Question 1: Global Data Aggregation
**Scenario:** A company collects temperature, humidity, and atmospheric pressure data from global sites. Each site generates 500 GB daily and has high-speed internet. They need to aggregate data quickly in a single S3 bucket with minimal operational complexity.

**Which solution meets these requirements?**

A) Turn on S3 Transfer Acceleration on the destination S3 bucket. Use multipart uploads to directly upload site data to the destination S3 bucket.

B) Upload the data from each site to an S3 bucket in the closest Region. Use S3 Cross-Region Replication to copy objects to the destination S3 bucket. Then remove the data from the origin S3 bucket.

C) Schedule AWS Snowball Edge Storage Optimized device jobs daily to transfer data from each site to the closest Region. Use S3 Cross-Region Replication to copy objects to the destination S3 bucket.

D) Upload the data from each site to an Amazon EC2 instance in the closest Region. Store the data in an Amazon Elastic Block Store (Amazon EBS) volume. At regular intervals, take an EBS snapshot and copy it to the Region that contains the destination S3 bucket. Restore the EBS volume in that Region.

**Answer:** A

---

### Question 2: Log Analysis with Minimal Changes
**Scenario:** A company needs to analyze JSON log files stored in S3. Queries will be simple and run on-demand. The solution needs minimal changes to existing architecture.

**What should the solutions architect do with the LEAST operational overhead?**

A) Use Amazon Redshift to load all the content into one place and run the SQL queries as needed.

B) Use Amazon CloudWatch Logs to store the logs. Run SQL queries as needed from the Amazon CloudWatch console.

C) Use Amazon Athena directly with Amazon S3 to run the queries as needed.

D) Use AWS Glue to catalog the logs. Use a transient Apache Spark cluster on Amazon EMR to run the SQL queries as needed.

**Answer:** C

---

### Question 3: Organizational S3 Access Control
**Scenario:** A company uses AWS Organizations to manage multiple accounts. The management account has an S3 bucket with project reports that should only be accessible to users within the organization.

**Which solution meets these requirements with the LEAST operational overhead?**

A) Add the aws:PrincipalOrgID global condition key with a reference to the organization ID to the S3 bucket policy.

B) Create an organizational unit (OU) for each department. Add the aws:PrincipalOrgPaths global condition key to the S3 bucket policy.

C) Use AWS CloudTrail to monitor the CreateAccount, InviteAccountToOrganization, LeaveOrganization, and RemoveAccountFromOrganization events. Update the S3 bucket policy accordingly.

D) Tag each user that needs access to the S3 bucket. Add the aws:PrincipalTag global condition key to the S3 bucket policy.

**Answer:** A

---

### Question 4: Private S3 Access from VPC
**Scenario:** An application runs on EC2 in a VPC and processes logs stored in S3. The EC2 instance needs S3 access without internet connectivity.

**Which solution provides private network connectivity to S3?**

A) Create a gateway VPC endpoint to the S3 bucket.

B) Stream the logs to Amazon CloudWatch Logs. Export the logs to the S3 bucket.

C) Create an instance profile on Amazon EC2 to allow S3 access.

D) Create an Amazon API Gateway API with a private link to access the S3 endpoint.

**Answer:** A

---

### Question 5: Shared Document Storage Issue
**Scenario:** A company has two EC2 instances with separate EBS volumes behind an ALB. Users report seeing different subsets of documents when refreshing the website.

**What should the solutions architect propose?**

A) Copy the data so both EBS volumes contain all the documents

B) Configure the Application Load Balancer to direct a user to the server with the documents

C) Copy the data from both EBS volumes to Amazon EFS. Modify the application to save new documents to Amazon EFS

D) Configure the Application Load Balancer to send the request to both servers. Return each document from the correct server

**Answer:** C

---

## Questions 6-10: Application Architecture

### Question 6: Large File Migration Strategy
**Scenario:** A company needs to migrate 70 TB of video files (1 MB to 500 GB each) from on-premises NFS to S3 as quickly as possible with minimal network bandwidth usage.

**Which solution meets these requirements?**

A) Create an S3 bucket. Create an IAM role that has permissions to write to the S3 bucket. Use the AWS CLI to copy all files locally to the S3 bucket.

B) Create an AWS Snowball Edge job. Receive a Snowball Edge device on premises. Use the Snowball Edge client to transfer data to the device. Return the device so that AWS can import the data into Amazon S3.

C) Deploy an S3 File Gateway on premises. Create a public service endpoint to connect to the S3 File Gateway. Create an S3 bucket. Create a new NFS file share on the S3 File Gateway. Point the new file share to the S3 bucket. Transfer the data from the existing NFS file share to the S3 File Gateway.

D) Set up an AWS Direct Connect connection between the on-premises network and AWS. Deploy an S3 File Gateway on premises. Create a public virtual interface (VIF) to connect to the S3 File Gateway. Create an S3 bucket. Create a new NFS file share on the S3 File Gateway. Point the new file share to the S3 bucket. Transfer the data from the existing NFS file share to the S3 File Gateway.

**Answer:** B

---

### Question 7: High-Volume Message Processing
**Scenario:** An application ingests messages that are consumed by dozens of other applications. Message volume varies drastically, sometimes reaching 100,000 per second. The solution needs decoupling and scalability.

**Which solution meets these requirements?**

A) Persist the messages to Amazon Kinesis Data Analytics. Configure the consumer applications to read and process the messages.

B) Deploy the ingestion application on Amazon EC2 instances in an Auto Scaling group to scale the number of EC2 instances based on CPU metrics.

C) Write the messages to Amazon Kinesis Data Streams with a single shard. Use an AWS Lambda function to preprocess messages and store them in Amazon DynamoDB. Configure the consumer applications to read from DynamoDB to process the messages.

D) Publish the messages to an Amazon Simple Notification Service (Amazon SNS) topic with multiple Amazon Simple Queue Service (Amazon SQS) subscriptions. Configure the consumer applications to process the messages from the queues.

**Answer:** D

---

### Question 8: Distributed Application Modernization
**Scenario:** A company is migrating a distributed application with a primary server coordinating jobs across compute nodes. They want to maximize resiliency and scalability for variable workloads.

**How should the architecture be designed?**

A) Configure an Amazon Simple Queue Service (Amazon SQS) queue as a destination for the jobs. Implement the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure EC2 Auto Scaling to use scheduled scaling.

B) Configure an Amazon Simple Queue Service (Amazon SQS) queue as a destination for the jobs. Implement the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure EC2 Auto Scaling based on the size of the queue.

C) Implement the primary server and the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure AWS CloudTrail as a destination for the jobs. Configure EC2 Auto Scaling based on the load on the primary server.

D) Implement the primary server and the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure Amazon EventBridge (Amazon CloudWatch Events) as a destination for the jobs. Configure EC2 Auto Scaling based on the load on the compute nodes.

**Answer:** B

---

### Question 9: SMB File Server Storage Extension
**Scenario:** A company's SMB file server is near storage capacity. Files are accessed frequently for 7 days, then rarely accessed. They need to extend storage while maintaining low-latency access to recent files and implementing lifecycle management.

**Which solution meets these requirements?**

A) Use AWS DataSync to copy data that is older than 7 days from the SMB file server to AWS.

B) Create an Amazon S3 File Gateway to extend the company's storage space. Create an S3 Lifecycle policy to transition the data to S3 Glacier Deep Archive after 7 days.

C) Create an Amazon FSx for Windows File Server file system to extend the company's storage space.

D) Install a utility on each user's computer to access Amazon S3. Create an S3 Lifecycle policy to transition the data to S3 Glacier Flexible Retrieval after 7 days.

**Answer:** B

---

### Question 10: E-commerce Order Processing
**Scenario:** An e-commerce application sends new orders to an API Gateway REST API. Orders must be processed in the order they are received.

**Which solution meets these requirements?**

A) Use an API Gateway integration to publish a message to an Amazon Simple Notification Service (Amazon SNS) topic when the application receives an order. Subscribe an AWS Lambda function to the topic to perform processing.

B) Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) FIFO queue when the application receives an order. Configure the SQS FIFO queue to invoke an AWS Lambda function for processing.

C) Use an API Gateway authorizer to block any requests while the application processes an order.

D) Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) standard queue when the application receives an order. Configure the SQS standard queue to invoke an AWS Lambda function for processing.

**Answer:** B

---

## Questions 11-15: Security & Networking

### Question 11: Credential Management for Aurora
**Scenario:** EC2 instances connect to Aurora database using usernames and passwords stored locally in files. The company wants to minimize credential management overhead.

**What should the solutions architect do?**

A) Use AWS Secrets Manager. Turn on automatic rotation.

B) Use AWS Systems Manager Parameter Store. Turn on automatic rotation.

C) Create an Amazon S3 bucket to store objects that are encrypted with an AWS Key Management Service (AWS KMS) encryption key. Migrate the credential file to the S3 bucket. Point the application to the S3 bucket.

D) Create an encrypted Amazon Elastic Block Store (Amazon EBS) volume for each EC2 instance. Attach the new EBS volume to each EC2 instance. Migrate the credential file to the new EBS volume. Point the application to the new EBS volume.

**Answer:** A

---

### Question 12: Global Performance Optimization
**Scenario:** A global company hosts its web application on EC2 behind an ALB. The application has static and dynamic data, with static data stored in S3. They want to improve performance and reduce latency using their own Route 53 domain.

**What should the solutions architect do?**

A) Create an Amazon CloudFront distribution that has the S3 bucket and the ALB as origins. Configure Route 53 to route traffic to the CloudFront distribution.

B) Create an Amazon CloudFront distribution that has the ALB as an origin. Create an AWS Global Accelerator standard accelerator that has the S3 bucket as an endpoint. Configure Route 53 to route traffic to the CloudFront distribution.

C) Create an Amazon CloudFront distribution that has the S3 bucket as an origin. Create an AWS Global Accelerator standard accelerator that has the ALB and the CloudFront distribution as endpoints. Create a custom domain name that points to the accelerator DNS name. Use the custom domain name as an endpoint for the web application.

D) Create an Amazon CloudFront distribution that has the ALB as an origin. Create an AWS Global Accelerator standard accelerator that has the S3 bucket as an endpoint. Create two domain names. Point one domain name to the CloudFront DNS name for dynamic content. Point the other domain name to the accelerator DNS name for static content. Use the domain names as endpoints for the web application.

**Answer:** A

---

### Question 13: Multi-Region Database Credential Rotation
**Scenario:** A company performs monthly maintenance requiring RDS MySQL credential rotation across multiple AWS Regions with minimal operational overhead.

**Which solution meets these requirements?**

A) Store the credentials as secrets in AWS Secrets Manager. Use multi-Region secret replication for the required Regions. Configure Secrets Manager to rotate the secrets on a schedule.

B) Store the credentials as secrets in AWS Systems Manager by creating a secure string parameter. Use multi-Region secret replication for the required Regions. Configure Systems Manager to rotate the secrets on a schedule.

C) Store the credentials in an Amazon S3 bucket that has server-side encryption (SSE) enabled. Use Amazon EventBridge (Amazon CloudWatch Events) to invoke an AWS Lambda function to rotate the credentials.

D) Encrypt the credentials as secrets by using AWS Key Management Service (AWS KMS) multi-Region customer managed keys. Store the secrets in an Amazon DynamoDB global table. Use an AWS Lambda function to retrieve the secrets from DynamoDB. Use the RDS API to rotate the secrets.

**Answer:** A

---

### Question 14: Auto-Scaling Database Solution
**Scenario:** An e-commerce application runs on EC2 with Auto Scaling behind an ALB. The MySQL database on a large EC2 instance degrades as load increases. The application handles more reads than writes and needs automatic scaling with high availability.

**Which solution meets these requirements?**

A) Use Amazon Redshift with a single node for leader and compute functionality.

B) Use Amazon RDS with a Single-AZ deployment. Configure Amazon RDS to add reader instances in a different Availability Zone.

C) Use Amazon Aurora with a Multi-AZ deployment. Configure Aurora Auto Scaling with Aurora Replicas.

D) Use Amazon ElastiCache for Memcached with EC2 Spot Instances.

**Answer:** C

---

### Question 15: VPC Traffic Inspection
**Scenario:** A company migrated to AWS and wants to implement traffic inspection and filtering similar to their on-premises inspection server for their production VPC.

**Which solution meets these requirements?**

A) Use Amazon GuardDuty for traffic inspection and traffic filtering in the production VPC.

B) Use Traffic Mirroring to mirror traffic from the production VPC for traffic inspection and filtering.

C) Use AWS Network Firewall to create the required rules for traffic inspection and traffic filtering for the production VPC.

D) Use AWS Firewall Manager to create the required rules for traffic inspection and traffic filtering for the production VPC.

**Answer:** C

---

## Questions 16-20: Data Analytics & Performance

### Question 16: Data Lake Reporting Solution
**Scenario:** A company has a data lake with S3 and RDS PostgreSQL data. They need a reporting solution with data visualization where management has full access and others have limited access.

**Which solution meets these requirements?**

A) Create an analysis in Amazon QuickSight. Connect all the data sources and create new datasets. Publish dashboards to visualize the data. Share the dashboards with the appropriate IAM roles.

B) Create an analysis in Amazon QuickSight. Connect all the data sources and create new datasets. Publish dashboards to visualize the data. Share the dashboards with the appropriate users and groups.

C) Create an AWS Glue table and crawler for the data in Amazon S3. Create an AWS Glue extract, transform, and load (ETL) job to produce reports. Publish the reports to Amazon S3. Use S3 bucket policies to limit access to the reports.

D) Create an AWS Glue table and crawler for the data in Amazon S3. Use Amazon Athena Federated Query to access data within Amazon RDS for PostgreSQL. Generate reports by using Amazon Athena. Publish the reports to Amazon S3. Use S3 bucket policies to limit access to the reports.

**Answer:** B

---

### Question 17: EC2 S3 Access Configuration
**Scenario:** A business application runs on two EC2 instances and uses an S3 bucket for document storage. The EC2 instances need access to the S3 bucket.

**What should the solutions architect do?**

A) Create an IAM role that grants access to the S3 bucket. Attach the role to the EC2 instances.

B) Create an IAM policy that grants access to the S3 bucket. Attach the policy to the EC2 instances.

C) Create an IAM group that grants access to the S3 bucket. Attach the group to the EC2 instances.

D) Create an IAM user that grants access to the S3 bucket. Attach the user account to the EC2 instances.

**Answer:** A

---

### Question 18: Image Processing Microservice
**Scenario:** A microservice needs to convert large images to compressed versions. When users upload images via web interface, the service should store original images in S3, process them with Lambda, and store compressed versions in another S3 bucket using durable, stateless components.

**Which combination of actions meets these requirements? (Choose two)**

A) Create an Amazon Simple Queue Service (Amazon SQS) queue. Configure the S3 bucket to send a notification to the SQS queue when an image is uploaded to the S3 bucket.

B) Configure the Lambda function to use the Amazon Simple Queue Service (Amazon SQS) queue as the invocation source. When the SQS message is successfully processed, delete the message in the queue.

C) Configure the Lambda function to monitor the S3 bucket for new uploads. When an uploaded image is detected, write the file name to a text file in memory and use the text file to keep track of the images that were processed.

D) Launch an Amazon EC2 instance to monitor an Amazon Simple Queue Service (Amazon SQS) queue. When items are added to the queue, log the file name in a text file on the EC2 instance and invoke the Lambda function.

E) Configure an Amazon EventBridge (Amazon CloudWatch Events) event to monitor the S3 bucket. When an image is uploaded, send an alert to an Amazon Simple Notification Service (Amazon SNS) topic with the application owner's email address for further processing.

**Answer:** A, B

---

### Question 19: Web Application Traffic Inspection
**Scenario:** A three-tier web application is deployed on AWS with web servers in public subnets and application/database servers in private subnets. A third-party firewall appliance in an inspection VPC needs to inspect all traffic before it reaches the web server.

**Which solution meets requirements with LEAST operational overhead?**

A) Create a Network Load Balancer in the public subnet of the application's VPC to route the traffic to the appliance for packet inspection.

B) Create an Application Load Balancer in the public subnet of the application's VPC to route the traffic to the appliance for packet inspection.

C) Deploy a transit gateway in the inspection VPC. Configure route tables to route the incoming packets through the transit gateway.

D) Deploy a Gateway Load Balancer in the inspection VPC. Create a Gateway Load Balancer endpoint to receive the incoming packets and forward the packets to the appliance.

**Answer:** D

---

### Question 20: Production Data Cloning
**Scenario:** A company wants to clone large amounts of production data on EBS volumes into a test environment in the same Region. Cloned data modifications must not affect production, software requires high I/O performance, and cloning time should be minimized.

**Which solution meets these requirements?**

A) Take EBS snapshots of the production EBS volumes. Restore the snapshots onto EC2 instance store volumes in the test environment.

B) Configure the production EBS volumes to use the EBS Multi-Attach feature. Take EBS snapshots of the production EBS volumes. Attach the production EBS volumes to the EC2 instances in the test environment.

C) Take EBS snapshots of the production EBS volumes. Create and initialize new EBS volumes. Attach the new EBS volumes to EC2 instances in the test environment before restoring the volumes from the production EBS snapshots.

D) Take EBS snapshots of the production EBS volumes. Turn on the EBS fast snapshot restore feature on the EBS snapshots. Restore the snapshots into new EBS volumes. Attach the new EBS volumes to EC2 instances in the test environment.

**Answer:** D

---

## Questions 21-25: Cost Optimization & Monitoring

### Question 21: One-Deal-A-Day Website
**Scenario:** An e-commerce company wants to launch a one-deal-a-day website that can handle millions of requests per hour with millisecond latency during peak hours.

**Which solution meets requirements with LEAST operational overhead?**

A) Use Amazon S3 to host the full website in different S3 buckets. Add Amazon CloudFront distributions. Set the S3 buckets as origins for the distributions. Store the order data in Amazon S3.

B) Deploy the full website on Amazon EC2 instances that run in Auto Scaling groups across multiple Availability Zones. Add an Application Load Balancer (ALB) to distribute the website traffic. Add another ALB for the backend APIs. Store the data in Amazon RDS for MySQL.

C) Migrate the full application to run in containers. Host the containers on Amazon Elastic Kubernetes Service (Amazon EKS). Use the Kubernetes Cluster Autoscaler to increase and decrease the number of pods to process bursts in traffic. Store the data in Amazon RDS for MySQL.

D) Use an Amazon S3 bucket to host the website's static content. Deploy an Amazon CloudFront distribution. Set the S3 bucket as the origin. Use Amazon API Gateway and AWS Lambda functions for the backend APIs. Store the data in Amazon DynamoDB.

**Answer:** D

---

### Question 22: Digital Media Storage Optimization
**Scenario:** A solutions architect is designing storage for a digital media application. Media files must be resilient to AZ loss. Some files are accessed frequently while others are rarely accessed in unpredictable patterns. Storage and retrieval costs must be minimized.

**Which storage option meets these requirements?**

A) S3 Standard

B) S3 Intelligent-Tiering

C) S3 Standard-Infrequent Access (S3 Standard-IA)

D) S3 One Zone-Infrequent Access (S3 One Zone-IA)

**Answer:** B

---

### Question 23: Backup File Lifecycle Management
**Scenario:** A company stores backup files using S3 Standard. Files are accessed frequently for 1 month but not accessed afterward. Files must be kept indefinitely in the most cost-effective way.

**Which storage solution meets these requirements?**

A) Configure S3 Intelligent-Tiering to automatically migrate objects.

B) Create an S3 Lifecycle configuration to transition objects from S3 Standard to S3 Glacier Deep Archive after 1 month.

C) Create an S3 Lifecycle configuration to transition objects from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) after 1 month.

D) Create an S3 Lifecycle configuration to transition objects from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 1 month.

**Answer:** B

---

### Question 24: EC2 Cost Analysis
**Scenario:** A company observes increased EC2 costs due to unwanted vertical scaling. The billing team needs to create a graph comparing the last 2 months of EC2 costs and perform in-depth analysis to identify the root cause.

**How should this be done with LEAST operational overhead?**

A) Use AWS Budgets to create a budget report and compare EC2 costs based on instance types.

B) Use Cost Explorer's granular filtering feature to perform an in-depth analysis of EC2 costs based on instance types.

C) Use graphs from the AWS Billing and Cost Management dashboard to compare EC2 costs based on instance types for the last 2 months.

D) Use AWS Cost and Usage Reports to create a report and send it to an Amazon S3 bucket. Use Amazon QuickSight with Amazon S3 as a source to generate an interactive graph based on instance types.

**Answer:** B

---

### Question 25: Lambda Function Optimization
**Scenario:** An application uses Lambda through API Gateway to store information in Aurora PostgreSQL. During proof-of-concept, Lambda quotas had to be increased significantly for high data volumes. A new design is needed for better scalability with minimal configuration effort.

**Which solution meets these requirements?**

A) Refactor the Lambda function code to Apache Tomcat code that runs on Amazon EC2 instances. Connect the database by using native Java Database Connectivity (JDBC) drivers.

B) Change the platform from Aurora to Amazon DynamoDB. Provision a DynamoDB Accelerator (DAX) cluster. Use the DAX client SDK to point the existing DynamoDB API calls at the DAX cluster.

C) Set up two Lambda functions. Configure one function to receive the information. Configure the other function to load the information into the database. Integrate the Lambda functions by using Amazon Simple Notification Service (Amazon SNS).

D) Set up two Lambda functions. Configure one function to receive the information. Configure the other function to load the information into the database. Integrate the Lambda functions by using an Amazon Simple Queue Service (Amazon SQS) queue.

**Answer:** D

---

## Answer Key Summary

| Question | Answer | Key Concept |
|----------|--------|-------------|
| 1 | A | S3 Transfer Acceleration |
| 2 | C | Amazon Athena for S3 queries |
| 3 | A | AWS Organizations S3 bucket policy |
| 4 | A | VPC Gateway Endpoint |
| 5 | C | Amazon EFS for shared storage |
| 6 | B | AWS Snowball for large data migration |
| 7 | D | SNS with SQS for fan-out messaging |
| 8 | B | SQS-based Auto Scaling |
| 9 | B | S3 File Gateway with lifecycle policies |
| 10 | B | SQS FIFO for ordered processing |
| 11 | A | AWS Secrets Manager |
| 12 | A | CloudFront with multiple origins |
| 13 | A | Multi-Region Secrets Manager |
| 14 | C | Aurora Auto Scaling |
| 15 | C | AWS Network Firewall |
| 16 | B | Amazon QuickSight user/group sharing |
| 17 | A | IAM roles for EC2 |
| 18 | A, B | S3 notifications with SQS and Lambda |
| 19 | D | Gateway Load Balancer |
| 20 | D | EBS Fast Snapshot Restore |
| 21 | D | Serverless architecture (S3, CloudFront, API Gateway, Lambda, DynamoDB) |
| 22 | B | S3 Intelligent-Tiering |
| 23 | B | S3 Glacier Deep Archive |
| 24 | B | AWS Cost Explorer |
| 25 | D | Lambda decoupling with SQS |

---

## Study Tips

1. **Focus on AWS Well-Architected Framework pillars:**
   - Operational Excellence
   - Security
   - Reliability
   - Performance Efficiency
   - Cost Optimization

2. **Key service patterns to remember:**
   - Use S3 for static content, Aurora/RDS for relational data
   - SQS for decoupling, SNS for notifications
   - CloudFront for global content delivery
   - Auto Scaling for handling variable loads
   - Secrets Manager for credential management

3. **Cost optimization strategies:**
   - Use appropriate storage classes (S3 Intelligent-Tiering, lifecycle policies)
   - Implement Auto Scaling to match capacity with demand
   - Use serverless services where appropriate

4. **Security best practices:**
   - Use IAM roles instead of access keys
   - Implement least privilege access
   - Use AWS Organizations for multi-account management

---

## Questions 26-30: Monitoring & Compliance

### Question 26: S3 Configuration Change Monitoring
**Scenario:** A company needs to review its AWS deployment to ensure S3 buckets don't have unauthorized configuration changes.

**What should a solutions architect do?**

A) Turn on AWS Config with the appropriate rules.

B) Turn on AWS Trusted Advisor with the appropriate checks.

C) Turn on Amazon Inspector with the appropriate assessment template.

D) Turn on Amazon S3 server access logging. Configure Amazon EventBridge (Amazon CloudWatch Events).

**Answer:** A

---

### Question 27: CloudWatch Dashboard Access for External User
**Scenario:** A company's product manager (without AWS account) needs periodic access to a CloudWatch dashboard following least privilege principle.

**Which solution meets these requirements?**

A) Share the dashboard from the CloudWatch console. Enter the product manager's email address, and complete the sharing steps. Provide a shareable link for the dashboard to the product manager.

B) Create an IAM user specifically for the product manager. Attach the CloudWatchReadOnlyAccess AWS managed policy to the user. Share the new login credentials with the product manager. Share the browser URL of the correct dashboard with the product manager.

C) Create an IAM user for the company's employees. Attach the ViewOnlyAccess AWS managed policy to the IAM user. Share the new login credentials with the product manager. Ask the product manager to navigate to the CloudWatch console and locate the dashboard by name in the Dashboards section.

D) Deploy a bastion server in a public subnet. When the product manager requires access to the dashboard, start the server and share the RDP credentials. On the bastion server, ensure that the browser is configured to open the dashboard URL with cached AWS credentials that have appropriate permissions to view the dashboard.

**Answer:** A

---

### Question 28: SSO with On-Premises Active Directory
**Scenario:** A company manages accounts with AWS Organizations and needs SSO across all accounts while continuing to manage users in on-premises Microsoft Active Directory.

**Which solution meets these requirements?**

A) Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console. Create a one-way forest trust or a one-way domain trust to connect the company's self-managed Microsoft Active Directory with AWS SSO by using AWS Directory Service for Microsoft Active Directory.

B) Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console. Create a two-way forest trust to connect the company's self-managed Microsoft Active Directory with AWS SSO by using AWS Directory Service for Microsoft Active Directory.

C) Use AWS Directory Service. Create a two-way trust relationship with the company's self-managed Microsoft Active Directory.

D) Deploy an identity provider (IdP) on premises. Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console.

**Answer:** B

---

### Question 29: VoIP Service Global Routing
**Scenario:** A VoIP service using UDP connections runs on EC2 Auto Scaling groups across multiple regions. Users need routing to the lowest latency region with automated failover.

**Which solution meets these requirements?**

A) Deploy a Network Load Balancer (NLB) and an associated target group. Associate the target group with the Auto Scaling group. Use the NLB as an AWS Global Accelerator endpoint in each Region.

B) Deploy an Application Load Balancer (ALB) and an associated target group. Associate the target group with the Auto Scaling group. Use the ALB as an AWS Global Accelerator endpoint in each Region.

C) Deploy a Network Load Balancer (NLB) and an associated target group. Associate the target group with the Auto Scaling group. Create an Amazon Route 53 latency record that points to aliases for each NLB. Create an Amazon CloudFront distribution that uses the latency record as an origin.

D) Deploy an Application Load Balancer (ALB) and an associated target group. Associate the target group with the Auto Scaling group. Create an Amazon Route 53 weighted record that points to aliases for each ALB. Deploy an Amazon CloudFront distribution that uses the weighted record as an origin.

**Answer:** A

---

### Question 30: Cost-Effective RDS Testing Strategy
**Scenario:** A development team runs monthly 48-hour resource-intensive tests on a general purpose RDS MySQL instance. They want to reduce costs without reducing compute/memory attributes.

**Which solution is MOST cost-effective?**

A) Stop the DB instance when tests are completed. Restart the DB instance when required.

B) Use an Auto Scaling policy with the DB instance to automatically scale when tests are completed.

C) Create a snapshot when tests are completed. Terminate the DB instance and restore the snapshot when required.

D) Modify the DB instance to a low-capacity instance when tests are completed. Modify the DB instance again when required.

**Answer:** C

---

## Questions 31-35: Resource Management & Security

### Question 31: Resource Tagging Compliance
**Scenario:** A company wants to ensure all EC2, RDS, and Redshift resources are configured with tags with minimal effort for configuration and operation.

**What should a solutions architect do?**

A) Use AWS Config rules to define and detect resources that are not properly tagged.

B) Use Cost Explorer to display resources that are not properly tagged. Tag those resources manually.

C) Write API calls to check all resources for proper tag allocation. Periodically run the code on an EC2 instance.

D) Write API calls to check all resources for proper tag allocation. Schedule an AWS Lambda function through Amazon CloudWatch to periodically run the code.

**Answer:** A

---

### Question 32: Cost-Effective Static Website Hosting
**Scenario:** A development team needs to host a website with HTML, CSS, client-side JavaScript, and images for access by other teams.

**Which method is MOST cost-effective?**

A) Containerize the website and host it in AWS Fargate.

B) Create an Amazon S3 bucket and host the website there.

C) Deploy a web server on an Amazon EC2 instance to host the website.

D) Configure an Application Load Balancer with an AWS Lambda target that uses the Express.js framework.

**Answer:** B

---

### Question 33: Real-Time Transaction Processing
**Scenario:** An online marketplace needs a scalable, near-real-time solution to share millions of financial transactions with internal applications. Sensitive data must be removed before storage in a document database.

**What should a solutions architect recommend?**

A) Store the transactions data into Amazon DynamoDB. Set up a rule in DynamoDB to remove sensitive data from every transaction upon write. Use DynamoDB Streams to share the transactions data with other applications.

B) Stream the transactions data into Amazon Kinesis Data Firehose to store data in Amazon DynamoDB and Amazon S3. Use AWS Lambda integration with Kinesis Data Firehose to remove sensitive data. Other applications can consume the data stored in Amazon S3.

C) Stream the transactions data into Amazon Kinesis Data Streams. Use AWS Lambda integration to remove sensitive data from every transaction and then store the transactions data in Amazon DynamoDB. Other applications can consume the transactions data off the Kinesis data stream.

D) Store the batched transactions data in Amazon S3 as files. Use AWS Lambda to process every file and remove sensitive data before updating the files in Amazon S3. The Lambda function then stores the data in Amazon DynamoDB. Other applications can consume transaction files stored in Amazon S3.

**Answer:** C

---

### Question 34: Compliance and Auditing Requirements
**Scenario:** A company must track configuration changes on AWS resources and record API call history for compliance, governance, auditing, and security.

**What should a solutions architect do?**

A) Use AWS CloudTrail to track configuration changes and AWS Config to record API calls.

B) Use AWS Config to track configuration changes and AWS CloudTrail to record API calls.

C) Use AWS Config to track configuration changes and Amazon CloudWatch to record API calls.

D) Use AWS CloudTrail to track configuration changes and Amazon CloudWatch to record API calls.

**Answer:** B

---

### Question 35: DDoS Protection for Public Web Application
**Scenario:** A company is launching a public-facing web application with EC2 instances in a VPC behind an ELB, using third-party DNS. They need protection against large-scale DDoS attacks.

**Which solution meets these requirements?**

A) Enable Amazon GuardDuty on the account.

B) Enable Amazon Inspector on the EC2 instances.

C) Enable AWS Shield and assign Amazon Route 53 to it.

D) Enable AWS Shield Advanced and assign the ELB to it.

**Answer:** D

---

## Questions 36-40: Encryption & Performance

### Question 36: Multi-Region KMS Encryption
**Scenario:** An application stores data in S3 buckets in two regions. All data must be encrypted/decrypted with the same KMS customer managed key, with data and key stored in both regions.

**Which solution meets requirements with LEAST operational overhead?**

A) Create an S3 bucket in each Region. Configure the S3 buckets to use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Configure replication between the S3 buckets.

B) Create a customer managed multi-Region KMS key. Create an S3 bucket in each Region. Configure replication between the S3 buckets. Configure the application to use the KMS key with client-side encryption.

C) Create a customer managed KMS key and an S3 bucket in each Region. Configure the S3 buckets to use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Configure replication between the S3 buckets.

D) Create a customer managed KMS key and an S3 bucket in each Region. Configure the S3 buckets to use server-side encryption with AWS KMS keys (SSE-KMS). Configure replication between the S3 buckets.

**Answer:** B

---

### Question 37: Secure Remote EC2 Access
**Scenario:** A company needs to create a repeatable strategy to access and administer EC2 instances remotely and securely using native AWS services following Well-Architected Framework.

**Which solution has LEAST operational overhead?**

A) Use the EC2 serial console to directly access the terminal interface of each instance for administration.

B) Attach the appropriate IAM role to each existing instance and new instance. Use AWS Systems Manager Session Manager to establish a remote SSH session.

C) Create an administrative SSH key pair. Load the public key into each EC2 instance. Deploy a bastion host in a public subnet to provide a tunnel for administration of each instance.

D) Establish an AWS Site-to-Site VPN connection. Instruct administrators to use their local on-premises machines to connect directly to the instances by using SSH keys across the VPN tunnel.

**Answer:** B

---

### Question 38: Global Static Website Performance
**Scenario:** A company hosts a static website on S3 with Route 53 DNS. The website is experiencing increased global demand and needs decreased latency.

**Which solution is MOST cost-effective?**

A) Replicate the S3 bucket that contains the website to all AWS Regions. Add Route 53 geolocation routing entries.

B) Provision accelerators in AWS Global Accelerator. Associate the supplied IP addresses with the S3 bucket. Edit the Route 53 entries to point to the IP addresses of the accelerators.

C) Add an Amazon CloudFront distribution in front of the S3 bucket. Edit the Route 53 entries to point to the CloudFront distribution.

D) Enable S3 Transfer Acceleration on the bucket. Edit the Route 53 entries to point to the new endpoint.

**Answer:** C

---

### Question 39: RDS Performance Optimization
**Scenario:** An RDS MySQL database with 10+ million rows and 2TB General Purpose SSD storage experiences slow insert operations (10+ seconds) due to storage performance issues.

**Which solution addresses this performance issue?**

A) Change the storage type to Provisioned IOPS SSD.

B) Change the DB instance to a memory optimized instance class.

C) Change the DB instance to a burstable performance instance class.

D) Enable Multi-AZ RDS read replicas with MySQL native asynchronous replication.

**Answer:** A

---

### Question 40: Edge Device Data Ingestion
**Scenario:** Thousands of edge devices generate 1TB of 2KB status alerts daily. Need a highly available, cost-effective solution with 14-day immediate access and archiving of older data.

**What is the MOST operationally efficient solution?**

A) Create an Amazon Kinesis Data Firehose delivery stream to ingest the alerts. Configure the Kinesis Data Firehose stream to deliver the alerts to an Amazon S3 bucket. Set up an S3 Lifecycle configuration to transition data to Amazon S3 Glacier after 14 days.

B) Launch Amazon EC2 instances across two Availability Zones and place them behind an Elastic Load Balancer to ingest the alerts. Create a script on the EC2 instances that will store the alerts in an Amazon S3 bucket. Set up an S3 Lifecycle configuration to transition data to Amazon S3 Glacier after 14 days.

C) Create an Amazon Kinesis Data Firehose delivery stream to ingest the alerts. Configure the Kinesis Data Firehose stream to deliver the alerts to an Amazon OpenSearch Service (Amazon Elasticsearch Service) cluster. Set up the Amazon OpenSearch Service (Amazon Elasticsearch Service) cluster to take manual snapshots every day and delete data from the cluster that is older than 14 days.

D) Create an Amazon Simple Queue Service (Amazon SQS) standard queue to ingest the alerts, and set the message retention period to 14 days. Configure consumers to poll the SQS queue, check the age of the message, and analyze the message data as needed. If the message is 14 days old, the consumer should copy the message to an Amazon S3 bucket and delete the message from the SQS queue.

**Answer:** A

---

## Questions 41-45: Application Optimization & Reliability

### Question 41: SaaS Integration Performance Improvement
**Scenario:** An application integrates with multiple SaaS sources, with EC2 instances receiving, uploading to S3, and sending notifications. Performance is slow and needs improvement.

**Which solution has LEAST operational overhead?**

A) Create an Auto Scaling group so that EC2 instances can scale out. Configure an S3 event notification to send events to an Amazon Simple Notification Service (Amazon SNS) topic when the upload to the S3 bucket is complete.

B) Create an Amazon AppFlow flow to transfer data between each SaaS source and the S3 bucket. Configure an S3 event notification to send events to an Amazon Simple Notification Service (Amazon SNS) topic when the upload to the S3 bucket is complete.

C) Create an Amazon EventBridge (Amazon CloudWatch Events) rule for each SaaS source to send output data. Configure the S3 bucket as the rule's target. Create a second EventBridge (CloudWatch Events) rule to send events when the upload to the S3 bucket is complete. Configure an Amazon Simple Notification Service (Amazon SNS) topic as the second rule's target.

D) Create a Docker container to use instead of an EC2 instance. Host the containerized application on Amazon Elastic Container Service (Amazon ECS). Configure Amazon CloudWatch Container Insights to send events to an Amazon Simple Notification Service (Amazon SNS) topic when the upload to the S3 bucket is complete.

**Answer:** B

---

### Question 42: Cost-Effective S3 Access
**Scenario:** EC2 instances in multiple AZs download/upload images to S3 through a single NAT gateway. The company is concerned about data transfer charges.

**What is the MOST cost-effective way to avoid Regional data transfer charges?**

A) Launch the NAT gateway in each Availability Zone.

B) Replace the NAT gateway with a NAT instance.

C) Deploy a gateway VPC endpoint for Amazon S3.

D) Provision an EC2 Dedicated Host to run the EC2 instances.

**Answer:** C

---

### Question 43: On-Premises Backup Bandwidth Solution
**Scenario:** An on-premises application generates large amounts of time-sensitive data backed up to S3, but users complain about internet bandwidth limitations.

**Which long-term solution meets these requirements?**

A) Establish AWS VPN connections and proxy all traffic through a VPC gateway endpoint.

B) Establish a new AWS Direct Connect connection and direct backup traffic through this new connection.

C) Order daily AWS Snowball devices. Load the data onto the Snowball devices and return the devices to AWS each day.

D) Submit a support ticket through the AWS Management Console. Request the removal of S3 service limits from the account.

**Answer:** B

---

### Question 44: S3 Data Protection from Accidental Deletion
**Scenario:** A company has an S3 bucket with critical data that must be protected from accidental deletion.

**Which combination of steps should be taken? (Choose two)**

A) Enable versioning on the S3 bucket.

B) Enable MFA Delete on the S3 bucket.

C) Create a bucket policy on the S3 bucket.

D) Enable default encryption on the S3 bucket.

E) Create a lifecycle policy for the objects in the S3 bucket.

**Answer:** A, B

---

### Question 45: Lambda Function Reliability Improvement
**Scenario:** A data ingestion workflow with SNS and Lambda occasionally fails due to network connectivity issues. When failures occur, Lambda doesn't process the corresponding data unless manually rerun.

**Which combination ensures Lambda ingests all data? (Choose two)**

A) Deploy the Lambda function in multiple Availability Zones.

B) Create an Amazon Simple Queue Service (Amazon SQS) queue, and subscribe it to the SNS topic.

C) Increase the CPU and memory that are allocated to the Lambda function.

D) Increase provisioned throughput for the Lambda function.

E) Modify the Lambda function to read from an Amazon Simple Queue Service (Amazon SQS) queue.

**Answer:** B, E

---

## Questions 46-50: Advanced Security & Management

### Question 46: PII Detection and Remediation
**Scenario:** A company receives transaction files via SFTP (some >200GB) and discovered some contain PII that shouldn't be included. They want automated PII detection alerts and remediation.

**What should a solutions architect do with LEAST development effort?**

A) Use an Amazon S3 bucket as a secure transfer point. Use Amazon Inspector to scan the objects in the bucket. If objects contain PII, trigger an S3 Lifecycle policy to remove the objects that contain PII.

B) Use an Amazon S3 bucket as a secure transfer point. Use Amazon Macie to scan the objects in the bucket. If objects contain PII, use Amazon Simple Notification Service (Amazon SNS) to trigger a notification to the administrators to remove the objects that contain PII.

C) Implement custom scanning algorithms in an AWS Lambda function. Trigger the function when objects are loaded into the bucket. If objects contain PII, use Amazon Simple Notification Service (Amazon SNS) to trigger a notification to the administrators to remove the objects that contain PII.

D) Implement custom scanning algorithms in an AWS Lambda function. Trigger the function when objects are loaded into the bucket. If objects contain PII, use Amazon Simple Email Service (Amazon SES) to trigger a notification to the administrators and trigger an S3 Lifecycle policy to remove the objects that contain PII.

**Answer:** B

---

### Question 47: Guaranteed EC2 Capacity
**Scenario:** A company needs guaranteed EC2 capacity in three specific Availability Zones in a specific region for a 1-week upcoming event.

**What should the company do?**

A) Purchase Reserved Instances that specify the Region needed.

B) Create an On-Demand Capacity Reservation that specifies the Region needed.

C) Purchase Reserved Instances that specify the Region and three Availability Zones needed.

D) Create an On-Demand Capacity Reservation that specifies the Region and three Availability Zones needed.

**Answer:** D

---

### Question 48: Durable Catalog Storage
**Scenario:** A company's website uses EC2 instance store for its catalog. They want to ensure the catalog is highly available and stored in a durable location.

**What should a solutions architect do?**

A) Move the catalog to Amazon ElastiCache for Redis.

B) Deploy a larger EC2 instance with a larger instance store.

C) Move the catalog from the instance store to Amazon S3 Glacier Deep Archive.

D) Move the catalog to an Amazon Elastic File System (Amazon EFS) file system.

**Answer:** D

---

### Question 49: Call Transcript File Storage Optimization
**Scenario:** A company stores call transcript files monthly. Users access files randomly within 1 year but infrequently after 1 year. Quick access needed for <1 year files, acceptable delay for older files.

**Which solution is MOST cost-effective?**

A) Store individual files with tags in Amazon S3 Glacier Instant Retrieval. Query the tags to retrieve the files from S3 Glacier Instant Retrieval.

B) Store individual files in Amazon S3 Intelligent-Tiering. Use S3 Lifecycle policies to move the files to S3 Glacier Flexible Retrieval after 1 year. Query and retrieve the files that are in Amazon S3 by using Amazon Athena. Query and retrieve the files that are in S3 Glacier by using S3 Glacier Select.

C) Store individual files with tags in Amazon S3 Standard storage. Store search metadata for each archive in Amazon S3 Standard storage. Use S3 Lifecycle policies to move the files to S3 Glacier Instant Retrieval after 1 year. Query and retrieve the files by searching for metadata from Amazon S3.

D) Store individual files in Amazon S3 Standard storage. Use S3 Lifecycle policies to move the files to S3 Glacier Deep Archive after 1 year. Store search metadata in Amazon RDS. Query the files from Amazon RDS. Retrieve the files from S3 Glacier Deep Archive.

**Answer:** B

---

### Question 50: Large-Scale EC2 Patching
**Scenario:** A company has 1,000 EC2 Linux instances running third-party software that needs patching as quickly as possible to remediate a critical security vulnerability.

**What should a solutions architect do?**

A) Create an AWS Lambda function to apply the patch to all EC2 instances.

B) Configure AWS Systems Manager Patch Manager to apply the patch to all EC2 instances.

C) Schedule an AWS Systems Manager maintenance window to apply the patch to all EC2 instances.

D) Use AWS Systems Manager Run Command to run a custom command that applies the patch to all EC2 instances.

**Answer:** D

---

## Questions 51-55: Advanced Application Development

### Question 51: Automated Email Reporting System
**Scenario:** A company developing an application with a REST API for order shipping statistics wants to extract data, format it into HTML, and email reports to multiple addresses every morning.

**Which combination of steps should be taken? (Choose two)**

A) Configure the application to send the data to Amazon Kinesis Data Firehose.

B) Use Amazon Simple Email Service (Amazon SES) to format the data and to send the report by email.

C) Create an Amazon EventBridge (Amazon CloudWatch Events) scheduled event that invokes an AWS Glue job to query the application's API for the data.

D) Create an Amazon EventBridge (Amazon CloudWatch Events) scheduled event that invokes an AWS Lambda function to query the application's API for the data.

E) Store the application data in Amazon S3. Create an Amazon Simple Notification Service (Amazon SNS) topic as an S3 event destination to send the report by email.

**Answer:** D, B

---

### Question 52: Large File Processing Migration
**Scenario:** A company wants to migrate an on-premises application to AWS. The application produces files ranging from tens of GB to hundreds of TB and needs standard file system structure with automatic scaling, high availability, and minimal operational overhead.

**Which solution meets these requirements?**

A) Migrate the application to run as containers on Amazon Elastic Container Service (Amazon ECS). Use Amazon S3 for storage.

B) Migrate the application to run as containers on Amazon Elastic Kubernetes Service (Amazon EKS). Use Amazon Elastic Block Store (Amazon EBS) for storage.

C) Migrate the application to Amazon EC2 instances in a Multi-AZ Auto Scaling group. Use Amazon Elastic File System (Amazon EFS) for storage.

D) Migrate the application to Amazon EC2 instances in a Multi-AZ Auto Scaling group. Use Amazon Elastic Block Store (Amazon EBS) for storage.

**Answer:** C

---

### Question 53: Long-Term Compliance Storage
**Scenario:** A company needs to store accounting records in S3 with immediate access for 1 year, then archived for 9 more years. No one, including admin and root users, can delete records during the entire 10-year period. Maximum resiliency required.

**Which solution meets these requirements?**

A) Store the records in S3 Glacier for the entire 10-year period. Use an access control policy to deny deletion of the records for a period of 10 years.

B) Store the records by using S3 Intelligent-Tiering. Use an IAM policy to deny deletion of the records. After 10 years, change the IAM policy to allow deletion.

C) Use an S3 Lifecycle policy to transition the records from S3 Standard to S3 Glacier Deep Archive after 1 year. Use S3 Object Lock in compliance mode for a period of 10 years.

D) Use an S3 Lifecycle policy to transition the records from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 1 year. Use S3 Object Lock in governance mode for a period of 10 years.

**Answer:** C

---

### Question 54: Windows File Shares Modernization
**Scenario:** A company runs Windows workloads with file shares on two EC2 instances that synchronize data. They want a highly available, durable storage solution preserving current user access patterns.

**What should a solutions architect do?**

A) Migrate all the data to Amazon S3. Set up IAM authentication for users to access files.

B) Set up an Amazon S3 File Gateway. Mount the S3 File Gateway on the existing EC2 instances.

C) Extend the file share environment to Amazon FSx for Windows File Server with a Multi-AZ configuration. Migrate all the data to FSx for Windows File Server.

D) Extend the file share environment to Amazon Elastic File System (Amazon EFS) with a Multi-AZ configuration. Migrate all the data to Amazon EFS.

**Answer:** C

---

### Question 55: VPC Database Access Control
**Scenario:** A VPC architecture has six subnets in two AZs (public, private, and database subnets per AZ). Only EC2 instances in private subnets should access RDS databases.

**Which solution meets these requirements?**

A) Create a new route table that excludes the route to the public subnets' CIDR blocks. Associate the route table with the database subnets.

B) Create a security group that denies inbound traffic from the security group that is assigned to instances in the public subnets. Attach the security group to the DB instances.

C) Create a security group that allows inbound traffic from the security group that is assigned to instances in the private subnets. Attach the security group to the DB instances.

D) Create a new peering connection between the public subnets and the private subnets. Create a different peering connection between the private subnets and the database subnets.

**Answer:** C

---

## Questions 56-60: API Gateway & Web Applications

### Question 56: Custom Domain API Gateway with HTTPS
**Scenario:** A company uses API Gateway in ca-central-1 as public interface for backend APIs. Third-party services need HTTPS access using the company's domain name and certificate.

**Which solution meets these requirements?**

A) Create stage variables in API Gateway with Name="Endpoint-URL" and Value="Company Domain Name" to overwrite the default URL. Import the public certificate associated with the company's domain name into AWS Certificate Manager (ACM).

B) Create Route 53 DNS records with the company's domain name. Point the alias record to the Regional API Gateway stage endpoint. Import the public certificate associated with the company's domain name into AWS Certificate Manager (ACM) in the us-east-1 Region.

C) Create a Regional API Gateway endpoint. Associate the API Gateway endpoint with the company's domain name. Import the public certificate associated with the company's domain name into AWS Certificate Manager (ACM) in the same Region. Attach the certificate to the API Gateway endpoint. Configure Route 53 to route traffic to the API Gateway endpoint.

D) Create a Regional API Gateway endpoint. Associate the API Gateway endpoint with the company's domain name. Import the public certificate associated with the company's domain name into AWS Certificate Manager (ACM) in the us-east-1 Region. Attach the certificate to the API Gateway APIs. Create Route 53 DNS records with the company's domain name. Point an A record to the company's domain name.

**Answer:** C

---

### Question 57: Image Content Moderation
**Scenario:** A social media website allows users to upload images. The company wants to ensure images don't contain inappropriate content with minimal development effort.

**What should a solutions architect do?**

A) Use Amazon Comprehend to detect inappropriate content. Use human review for low-confidence predictions.

B) Use Amazon Rekognition to detect inappropriate content. Use human review for low-confidence predictions.

C) Use Amazon SageMaker to detect inappropriate content. Use ground truth to label low-confidence predictions.

D) Use AWS Fargate to deploy a custom machine learning model to detect inappropriate content. Use ground truth to label low-confidence predictions.

**Answer:** B

---

### Question 58: Serverless Container Management
**Scenario:** A company wants to run critical applications in containers for scalability and availability. They want to focus on application maintenance without managing underlying infrastructure.

**What should a solutions architect do?**

A) Use Amazon EC2 instances, and install Docker on the instances.

B) Use Amazon Elastic Container Service (Amazon ECS) on Amazon EC2 worker nodes.

C) Use Amazon Elastic Container Service (Amazon ECS) on AWS Fargate.

D) Use Amazon EC2 instances from an Amazon Elastic Container Service (Amazon ECS)-optimized Amazon Machine Image (AMI).

**Answer:** C

---

### Question 59: Large-Scale Clickstream Analytics
**Scenario:** A company hosts 300+ global websites and needs to analyze 30+ TB of clickstream data daily.

**What should a solutions architect do to transmit and process the data?**

A) Design an AWS Data Pipeline to archive the data to an Amazon S3 bucket and run an Amazon EMR cluster with the data to generate analytics.

B) Create an Auto Scaling group of Amazon EC2 instances to process the data and send it to an Amazon S3 data lake for Amazon Redshift to use for analysis.

C) Cache the data to Amazon CloudFront. Store the data in an Amazon S3 bucket. When an object is added to the S3 bucket, run an AWS Lambda function to process the data for analysis.

D) Collect the data from Amazon Kinesis Data Streams. Use Amazon Kinesis Data Firehose to transmit the data to an Amazon S3 data lake. Load the data in Amazon Redshift for analysis.

**Answer:** D

---

### Question 60: HTTP to HTTPS Redirection
**Scenario:** A company has a website behind an ALB configured to handle HTTP and HTTPS separately. They want to forward all requests to use HTTPS.

**What should a solutions architect do?**

A) Update the ALB's network ACL to accept only HTTPS traffic.

B) Create a rule that replaces the HTTP in the URL with HTTPS.

C) Create a listener rule on the ALB to redirect HTTP traffic to HTTPS.

D) Replace the ALB with a Network Load Balancer configured to use Server Name Indication (SNI).

**Answer:** C

---

## Questions 61-65: Security & Healthcare Applications

### Question 61: Database Credential Management
**Scenario:** A two-tier web application on EC2 connects to RDS. The company must not hardcode database credentials and needs automatic credential rotation.

**Which solution has LEAST operational overhead?**

A) Store the database credentials in the instance metadata. Use Amazon EventBridge (Amazon CloudWatch Events) rules to run a scheduled AWS Lambda function that updates the RDS credentials and instance metadata at the same time.

B) Store the database credentials in a configuration file in an encrypted Amazon S3 bucket. Use Amazon EventBridge (Amazon CloudWatch Events) rules to run a scheduled AWS Lambda function that updates the RDS credentials and the credentials in the configuration file at the same time. Use S3 Versioning to ensure the ability to fall back to previous values.

C) Store the database credentials as a secret in AWS Secrets Manager. Turn on automatic rotation for the secret. Attach the required permission to the EC2 role to grant access to the secret.

D) Store the database credentials as encrypted parameters in AWS Systems Manager Parameter Store. Turn on automatic rotation for the encrypted parameters. Attach the required permission to the EC2 role to grant access to the encrypted parameters.

**Answer:** C

---

### Question 62: External Certificate Management
**Scenario:** A public web application behind an ALB needs encryption with an SSL/TLS certificate from an external CA. The certificate must be rotated yearly before expiration.

**What should a solutions architect do?**

A) Use AWS Certificate Manager (ACM) to issue an SSL/TLS certificate. Apply the certificate to the ALB. Use the managed renewal feature to automatically rotate the certificate.

B) Use AWS Certificate Manager (ACM) to issue an SSL/TLS certificate. Import the key material from the certificate. Apply the certificate to the ALB. Use the managed renewal feature to automatically rotate the certificate.

C) Use AWS Certificate Manager (ACM) Private Certificate Authority to issue an SSL/TLS certificate from the root CA. Apply the certificate to the ALB. Use the managed renewal feature to automatically rotate the certificate.

D) Use AWS Certificate Manager (ACM) to import an SSL/TLS certificate. Apply the certificate to the ALB. Use Amazon EventBridge (Amazon CloudWatch Events) to send a notification when the certificate is nearing expiration. Rotate the certificate manually.

**Answer:** D

---

### Question 63: PDF to JPG Conversion at Scale
**Scenario:** A company with 700,000 users needs to convert large PDF files (5MB average) to JPG format. They need to store both original and converted files with a scalable solution for rapid growth.

**Which solution is MOST cost-effective?**

A) Save the .pdf files to Amazon S3. Configure an S3 PUT event to invoke an AWS Lambda function to convert the files to .jpg format and store them back in Amazon S3.

B) Save the .pdf files to Amazon DynamoDB. Use the DynamoDB Streams feature to invoke an AWS Lambda function to convert the files to .jpg format and store them back in DynamoDB.

C) Upload the .pdf files to an AWS Elastic Beanstalk application that includes Amazon EC2 instances, Amazon Elastic Block Store (Amazon EBS) storage, and an Auto Scaling group. Use a program in the EC2 instances to convert the files to .jpg format. Save the .pdf files and the .jpg files in the EBS store.

D) Upload the .pdf files to an AWS Elastic Beanstalk application that includes Amazon EC2 instances, Amazon Elastic File System (Amazon EFS) storage, and an Auto Scaling group. Use a program in the EC2 instances to convert the file to .jpg format. Save the .pdf files and the .jpg files in the EBS store.

**Answer:** A

---

### Question 64: Hybrid File Storage Solution
**Scenario:** A company has 5+ TB of Windows file data on-premises. During AWS migration, they need access to both AWS and on-premises storage with minimum latency, minimal operational overhead, and no changes to file access patterns. They use Site-to-Site VPN.

**What should a solutions architect do?**

A) Deploy and configure Amazon FSx for Windows File Server on AWS. Move the on-premises file data to FSx for Windows File Server. Reconfigure the workloads to use FSx for Windows File Server on AWS.

B) Deploy and configure an Amazon S3 File Gateway on premises. Move the on-premises file data to the S3 File Gateway. Reconfigure the on-premises workloads and the cloud workloads to use the S3 File Gateway.

C) Deploy and configure an Amazon S3 File Gateway on premises. Move the on-premises file data to Amazon S3. Reconfigure the workloads to use either Amazon S3 directly or the S3 File Gateway, depending on each workload's location.

D) Deploy and configure Amazon FSx for Windows File Server on AWS. Deploy and configure an Amazon FSx File Gateway on premises. Move the on-premises file data to the FSx File Gateway. Configure the cloud workloads to use FSx for Windows File Server on AWS. Configure the on-premises workloads to use the FSx File Gateway.

**Answer:** D

---

### Question 65: Healthcare PHI Detection
**Scenario:** A hospital uses API Gateway and Lambda to upload PDF and JPEG reports. They need to modify Lambda code to identify protected health information (PHI) in the reports.

**Which solution has LEAST operational overhead?**

A) Use existing Python libraries to extract the text from the reports and to identify the PHI from the extracted text.

B) Use Amazon Textract to extract the text from the reports. Use Amazon SageMaker to identify the PHI from the extracted text.

C) Use Amazon Textract to extract the text from the reports. Use Amazon Comprehend Medical to identify the PHI from the extracted text.

D) Use Amazon Rekognition to extract the text from the reports. Use Amazon Comprehend Medical to identify the PHI from the extracted text.

**Answer:** C

---

## Complete Answer Key Summary

| Question | Answer | Key Concept |
|----------|--------|-------------|
| 1 | A | S3 Transfer Acceleration |
| 2 | C | Amazon Athena for S3 queries |
| 3 | A | AWS Organizations S3 bucket policy |
| 4 | A | VPC Gateway Endpoint |
| 5 | C | Amazon EFS for shared storage |
| 6 | B | AWS Snowball for large data migration |
| 7 | D | SNS with SQS for fan-out messaging |
| 8 | B | SQS-based Auto Scaling |
| 9 | B | S3 File Gateway with lifecycle policies |
| 10 | B | SQS FIFO for ordered processing |
| 11 | A | AWS Secrets Manager |
| 12 | A | CloudFront with multiple origins |
| 13 | A | Multi-Region Secrets Manager |
| 14 | C | Aurora Auto Scaling |
| 15 | C | AWS Network Firewall |
| 16 | B | Amazon QuickSight user/group sharing |
| 17 | A | IAM roles for EC2 |
| 18 | A, B | S3 notifications with SQS and Lambda |
| 19 | D | Gateway Load Balancer |
| 20 | D | EBS Fast Snapshot Restore |
| 21 | D | Serverless architecture |
| 22 | B | S3 Intelligent-Tiering |
| 23 | B | S3 Glacier Deep Archive |
| 24 | B | AWS Cost Explorer |
| 25 | D | Lambda decoupling with SQS |
| 26 | A | AWS Config for configuration monitoring |
| 27 | A | CloudWatch dashboard sharing |
| 28 | B | AWS SSO with two-way forest trust |
| 29 | A | Global Accelerator with NLB for UDP |
| 30 | C | RDS snapshot and terminate strategy |
| 31 | A | AWS Config rules for tagging compliance |
| 32 | B | S3 static website hosting |
| 33 | C | Kinesis Data Streams with Lambda processing |
| 34 | B | Config for configuration, CloudTrail for API calls |
| 35 | D | AWS Shield Advanced for DDoS protection |
| 36 | B | Multi-Region KMS key |
| 37 | B | Systems Manager Session Manager |
| 38 | C | CloudFront for global content delivery |
| 39 | A | Provisioned IOPS SSD for database performance |
| 40 | A | Kinesis Data Firehose with S3 lifecycle |
| 41 | B | Amazon AppFlow for SaaS integration |
| 42 | C | VPC Gateway Endpoint for S3 |
| 43 | B | AWS Direct Connect for dedicated bandwidth |
| 44 | A, B | S3 versioning and MFA Delete |
| 45 | B, E | SQS queue for Lambda reliability |
| 46 | B | Amazon Macie for PII detection |
| 47 | D | On-Demand Capacity Reservation for specific AZs |
| 48 | D | Amazon EFS for durable file storage |
| 49 | B | S3 Intelligent-Tiering with lifecycle policies |
| 50 | D | Systems Manager Run Command for immediate patching |
| 51 | D, B | EventBridge scheduling with SES for email reports |
| 52 | C | EFS for scalable file system storage |
| 53 | C | S3 Object Lock compliance mode for retention |
| 54 | C | FSx for Windows File Server |
| 55 | C | Security groups for database access control |
| 56 | C | Regional API Gateway with ACM certificate |
| 57 | B | Amazon Rekognition for image content moderation |
| 58 | C | ECS on Fargate for serverless containers |
| 59 | D | Kinesis Data Streams and Firehose for analytics |
| 60 | C | ALB listener rule for HTTP to HTTPS redirect |
| 61 | C | Secrets Manager for credential management |
| 62 | D | Manual certificate rotation for external CA |
| 63 | A | S3 event-driven Lambda processing |
| 64 | D | FSx File Gateway for hybrid storage |
| 65 | C | Textract and Comprehend Medical for PHI detection |

---

## Extended Study Tips

### Advanced Concepts to Master:

1. **Multi-Region Architecture:**
   - Global Accelerator vs CloudFront
   - Multi-Region KMS keys
   - Cross-Region replication strategies

2. **Security Best Practices:**
   - AWS Config for compliance monitoring
   - Secrets Manager for credential rotation
   - Macie for data classification and PII detection

3. **Performance Optimization:**
   - Storage types: GP2 vs GP3 vs Provisioned IOPS
   - Database scaling patterns
   - Content delivery strategies

4. **Cost Optimization Advanced:**
   - Reserved Instances vs Savings Plans vs Spot Instances
   - S3 storage class optimization
   - Data transfer cost reduction

6. **Healthcare & Compliance:**
   - Amazon Textract for document text extraction
   - Amazon Comprehend Medical for PHI detection
   - S3 Object Lock for compliance requirements
   - HIPAA-compliant architectures

7. **Operational Excellence:**
   - Systems Manager for patch management
   - CloudWatch for monitoring and alerting
   - AWS Config for configuration drift detection

### Service-Specific Best Practices:

**API Gateway:**
- Use Regional endpoints for better performance
- Custom domain names require ACM certificates in same region
- Implement proper HTTPS redirection patterns

**Container Services:**
- ECS on Fargate for serverless container management
- Use appropriate storage solutions (EFS for shared, EBS for instance-specific)
- Consider operational overhead when choosing between ECS and EKS

**File Storage Solutions:**
- S3 for object storage and static websites
- EFS for scalable, shared file systems
- FSx for Windows-specific file sharing needs
- Storage Gateways for hybrid scenarios

**Machine Learning Services:**
- Rekognition for image analysis and content moderation
- Textract for document text extraction
- Comprehend Medical for healthcare text analysis
- Choose managed services over custom solutions for faster implementation

- **Data Pipeline Design:** Kinesis → Lambda → DynamoDB patterns
- **Hybrid Cloud Integration:** Direct Connect, VPN, and gateway patterns  
- **Disaster Recovery:** RTO/RPO considerations with backup and restore strategies
- **Compliance Automation:** Config rules, CloudTrail, and automated remediation

## Contributing

Feel free to contribute additional questions or improvements to existing ones. Please ensure all questions follow AWS best practices and real-world scenarios.

## License

This content is provided for educational purposes. AWS and related service names are trademarks of Amazon Web Services, Inc.