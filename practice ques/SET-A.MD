# AWS Solutions Architect Associate (SAA) Practice Questions
---

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

## Contributing

Feel free to contribute additional questions or improvements to existing ones. Please ensure all questions follow AWS best practices and real-world scenarios.

## License

This content is provided for educational purposes. AWS and related service names are trademarks of Amazon Web Services, Inc.