# AWS Solutions Architect Associate Practice Questions

This repository contains practice questions for the AWS Solutions Architect Associate certification exam, covering various AWS services and architectural patterns.

## Question Bank (651-685)

### 651. S3 Lifecycle Management
A company stores a large volume of image files in an Amazon S3 bucket. The images need to be readily available for the first 180 days. The images are infrequently accessed for the next 180 days. After 360 days, the images need to be archived but must be available instantly upon request. After 5 years, only auditors can access the images. The auditors must be able to retrieve the images within 12 hours. The images cannot be lost during this process.

A developer will use S3 Standard storage for the first 180 days. The developer needs to configure an S3 Lifecycle rule.

Which solution will meet these requirements MOST cost-effectively?

**Options:**
1. Transition the objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 180 days. S3 Glacier Instant Retrieval after 360 days, and S3 Glacier Deep Archive after 5 years.

2. Transition the objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 180 days. S3 Glacier Flexible Retrieval after 360 days, and S3 Glacier Deep Archive after 5 years.

3. Transition the objects to S3 Standard-Infrequent Access (S3 Standard-IA) after 180 days, S3 Glacier Instant Retrieval after 360 days, and S3 Glacier Deep Archive after 5 years.

4. Transition the objects to S3 Standard-Infrequent Access (S3 Standard-IA) after 180 days, S3 Glacier Flexible Retrieval after 360 days, and S3 Glacier Deep Archive after 5 years.

---

### 652. EMR Cluster Configuration
A company has a large data workload that runs for 6 hours each day. The company cannot lose any data while the process is running. A solutions architect is designing an Amazon EMR cluster configuration to support this critical data workload.

Which solution will meet these requirements MOST cost-effectively?

**Options:**
1. Configure a long-running cluster that runs the primary node and core nodes on On-Demand Instances and the task nodes on Spot Instances.

2. Configure a transient cluster that runs the primary node and core nodes on On-Demand Instances and the task nodes on Spot Instances.

3. Configure a transient cluster that runs the primary node on an On-Demand Instance and the core nodes and task nodes on Spot Instances.

4. Configure a long-running cluster that runs the primary node on an On-Demand Instance, the core nodes on Spot Instances, and the task nodes on Spot Instances.

---

### 653. Resource Tagging with Organizations
A company maintains an Amazon RDS database that maps users to cost centers. The company has accounts in an organization in AWS Organizations. The company needs a solution that will tag all resources that are created in a specific AWS account in the organization. The solution must tag each resource with the cost center ID of the user who created the resource.

Which solution will meet these requirements?

**Options:**
1. Move the specific AWS account to a new organizational unit (OU) in Organizations from the management account. Create a service control policy (SCP) that requires all existing resources to have the correct cost center tag before the resources are created. Apply the SCP to the new OU.

2. Create an AWS Lambda function to tag the resources after the Lambda function looks up the appropriate cost center from the RDS database. Configure an Amazon EventBridge rule that reacts to AWS CloudTrail events to invoke the Lambda function.

3. Create an AWS CloudFormation stack to deploy an AWS Lambda function. Configure the Lambda function to look up the appropriate cost center from the RDS database and to tag resources. Create an Amazon EventBridge scheduled rule to invoke the CloudFormation stack.

4. Create an AWS Lambda function to tag the resources with a default value. Configure an Amazon EventBridge rule that reacts to AWS CloudTrail events to invoke the Lambda function when a resource is missing the cost center tag.

---

### 654. Web Application Modernization
A company recently migrated its web application to the AWS Cloud. The company uses an Amazon EC2 instance to run multiple processes to host the application. The processes include an Apache web server that serves static content. The Apache web server makes requests to a PHP application that uses a local Redis server for user sessions.

The company wants to redesign the architecture to be highly available and to use AWS managed solutions.

Which solution will meet these requirements?

**Options:**
1. Use AWS Elastic Beanstalk to host the static content and the PHP application. Configure Elastic Beanstalk to deploy its EC2 instance into a public subnet. Assign a public IP address.

2. Use AWS Lambda to host the static content and the PHP application. Use an Amazon API Gateway REST API to proxy requests to the Lambda function. Set the API Gateway CORS configuration to respond to the domain name. Configure Amazon ElastiCache for Redis to handle session information.

3. Keep the backend code on the EC2 instance. Create an Amazon ElastiCache for Redis cluster that has Multi-AZ enabled. Configure the ElastiCache for Redis cluster in cluster mode. Copy the frontend resources to Amazon S3. Configure the backend code to reference the EC2 instance.

4. Configure an Amazon CloudFront distribution with an Amazon S3 endpoint to an S3 bucket that is configured to host the static content. Configure an Application Load Balancer that targets an Amazon Elastic Container Service (Amazon ECS) service that runs AWS Fargate tasks for the PHP application. Configure the PHP application to use an Amazon ElastiCache for Redis cluster that runs in multiple Availability Zones.

---

### 655. Load Balancer with WAF and Sticky Sessions
A company runs a web application on Amazon EC2 instances in an Auto Scaling group that has a target group. The company designed the application to work with session affinity (sticky sessions) for a better user experience.

The application must be available publicly over the internet as an endpoint. A WAF must be applied to the endpoint for additional security. Session affinity (sticky sessions) must be configured on the endpoint.

Which combination of steps will meet these requirements? (Choose two.)

**Options:**
1. Create a public Network Load Balancer. Specify the application target group.

2. Create a Gateway Load Balancer. Specify the application target group.

3. Create a public Application Load Balancer. Specify the application target group.

4. Create a second target group. Add Elastic IP addresses to the EC2 instances.

5. Create a web ACL in AWS WAF. Associate the web ACL with the endpoint.

---

### 656. Historical Images Storage
A company runs a website that stores images of historical events. Website users need the ability to search and view images based on the year that the event in the image occurred. On average, users request each image only once or twice a year. The company wants a highly available solution to store and deliver the images to users.

Which solution will meet these requirements MOST cost-effectively?

**Options:**
1. Store images in Amazon Elastic Block Store (Amazon EBS). Use a web server that runs on Amazon EC2.
2. Store images in Amazon Elastic File System (Amazon EFS). Use a web server that runs on Amazon EC2.
3. Store images in Amazon S3 Standard. Use S3 Standard to directly deliver images by using a static website.
4. Store images in Amazon S3 Standard-Infrequent Access (S3 Standard-IA). Use S3 Standard-IA to directly deliver images by using a static website.

---

### 657. Centralized Security Group Management
A company has multiple AWS accounts in an organization in AWS Organizations that different business units use. The company has multiple offices around the world. The company needs to update security group rules to allow new office CIDR ranges or to remove old CIDR ranges across the organization. The company wants to centralize the management of security group rules to minimize the administrative overhead that updating CIDR ranges requires.

Which solution will meet these requirements MOST cost-effectively?

**Options:**
1. Create VPC security groups in the organization's management account. Update the security groups when a CIDR range update is necessary.
2. Create a VPC customer managed prefix list that contains the list of CIDRs. Use AWS Resource Access Manager (AWS RAM) to share the prefix list across the organization. Use the prefix list in the security groups across the organization.
3. Create an AWS managed prefix list. Use an AWS Security Hub policy to enforce the security group update across the organization. Use an AWS Lambda function to update the prefix list automatically when the CIDR ranges change.
4. Create security groups in a central administrative AWS account. Create an AWS Firewall Manager common security group policy for the whole organization. Select the previously created security groups as primary groups in the policy.

---

### 658. HPC Workload Migration
A company uses an on-premises network-attached storage (NAS) system to provide file shares to its high performance computing (HPC) workloads. The company wants to migrate its latency-sensitive HPC workloads and its storage to the AWS Cloud. The company must be able to provide NFS and SMB multi-protocol access from the file system.

Which solution will meet these requirements with the LEAST latency? (Choose two.)

**Options:**
1. Deploy compute optimized EC2 instances into a cluster placement group.
2. Deploy compute optimized EC2 instances into a partition placement group.
3. Attach the EC2 instances to an Amazon FSx for Lustre file system.
4. Attach the EC2 instances to an Amazon FSx for OpenZFS file system.
5. Attach the EC2 instances to an Amazon FSx for NetApp ONTAP file system.

---

### 659. Data Center Migration
A company is relocating its data center and wants to securely transfer 50 TB of data to AWS within 2 weeks. The existing data center has a Site-to-Site VPN connection to AWS that is 90% utilized.

Which AWS service should a solutions architect use to meet these requirements?

**Options:**
1. AWS DataSync with a VPC endpoint

2. AWS Direct Connect

3. AWS Snowball Edge Storage Optimized

4. AWS Storage Gateway

---

### 660. Auto Scaling for Peak Hours
A company hosts an application on Amazon EC2 On-Demand Instances in an Auto Scaling group. Application peak hours occur at the same time each day. Application users report slow application performance at the start of peak hours. The application performs normally 2-3 hours after peak hours begin. The company wants to ensure that the application works properly at the start of peak hours.

Which solution will meet these requirements?

**Options:**
1. Configure an Application Load Balancer to distribute traffic properly to the instances.

2. Configure a dynamic scaling policy for the Auto Scaling group to launch new instances based on memory utilization.

3. Configure a dynamic scaling policy for the Auto Scaling group to launch new instances based on CPU utilization.

4. Configure a scheduled scaling policy for the Auto Scaling group to launch new instances before peak hours.

---

### 661. Database Connection Scaling
A company runs applications on AWS that connect to the company's Amazon RDS database. The applications scale on weekends and at peak times of the year. The company wants to scale the database more effectively for its applications that connect to the database.

Which solution will meet these requirements with the LEAST operational overhead?

**Options:**
1. Use Amazon DynamoDB with connection pooling with a target group configuration for the database. Change the applications to use the DynamoDB endpoint.

2. Use Amazon RDS Proxy with a target group for the database. Change the applications to use the RDS Proxy endpoint.

3. Use a custom proxy that runs on Amazon EC2 as an intermediary to the database. Change the applications to use the custom proxy endpoint.

4. Use an AWS Lambda function to provide connection pooling with a target group configuration for the database. Change the applications to use the Lambda function.

---

### 662. EBS Storage Cost Optimization
A company uses AWS Cost Explorer to monitor its AWS costs. The company notices that Amazon Elastic Block Store (Amazon EBS) storage and snapshot costs increase every month. However, the company does not purchase additional EBS storage every month. The company wants to optimize monthly costs for its current storage usage.

Which solution will meet these requirements with the LEAST operational overhead?

**Options:**
1. Use logs in Amazon CloudWatch Logs to monitor the storage utilization of Amazon EBS. Use Amazon EBS Elastic Volumes to reduce the size of the EBS volumes.
2. Use a custom script to monitor space usage. Use Amazon EBS Elastic Volumes to reduce the size of the EBS volumes.
3. Delete all expired and unused snapshots to reduce snapshot costs.
4. Delete all nonessential snapshots. Use Amazon Data Lifecycle Manager to create and manage the snapshots according to the company's snapshot policy requirements.

---

### 663. ECS Security Configuration
A company is developing a new application on AWS. The application consists of an Amazon Elastic Container Service (Amazon ECS) cluster, an Amazon S3 bucket that contains assets for the application, and an Amazon RDS for MySQL database that contains the dataset for the application. The dataset contains sensitive information. The company wants to ensure that only the ECS cluster can access the data in the RDS for MySQL database and the data in the S3 bucket.

Which solution will meet these requirements?

**Options:**
1. Create a new AWS Key Management Service (AWS KMS) customer managed key to encrypt both the S3 bucket and the RDS for MySQL database. Ensure that the KMS key policy includes encrypt and decrypt permissions for the ECS task execution role.
2. Create an AWS Key Management Service (AWS KMS) AWS managed key to encrypt both the S3 bucket and the RDS for MySQL database. Ensure that the S3 bucket policy specifies the ECS task execution role as a user.
3. Create an S3 bucket policy that restricts bucket access to the ECS task execution role. Create a VPC endpoint for Amazon RDS for MySQL. Update the RDS for MySQL security group to allow access from only the subnets that the ECS cluster will generate tasks in.
4. Create a VPC endpoint for Amazon RDS for MySQL. Update the RDS for MySQL security group to allow access from only the subnets that the ECS cluster will generate tasks in. Create a VPC endpoint for Amazon S3. Update the S3 bucket policy to allow access from only the S3 VPC endpoint.

---

### 664. Elastic Beanstalk Auto Scaling
A company has a web application that runs on premises. The application experiences latency issues during peak hours. The latency issues occur twice each month. At the start of a latency issue, the application's CPU utilization immediately increases to 10 times its normal amount.

The company wants to migrate the application to AWS to improve latency. The company also wants to scale the application automatically when application demand increases. The company will use AWS Elastic Beanstalk for application deployment.

Which solution will meet these requirements?

**Options:**
1. Configure an Elastic Beanstalk environment to use burstable performance instances in unlimited mode. Configure the environment to scale based on requests.
2. Configure an Elastic Beanstalk environment to use compute optimized instances. Configure the environment to scale based on requests.
3. Configure an Elastic Beanstalk environment to use compute optimized instances. Configure the environment to scale on a schedule.
4. Configure an Elastic Beanstalk environment to use burstable performance instances in unlimited mode. Configure the environment to scale on predictive metrics.

---

### 665. Infrastructure Automation and Auditing
A company has customers located across the world. The company wants to use automation to secure its systems and network infrastructure. The company's security team must be able to track and audit all incremental changes to the infrastructure.

Which solution will meet these requirements?

**Options:**
1. Use AWS Organizations to set up the infrastructure. Use AWS Config to track changes.
2. Use AWS CloudFormation to set up the infrastructure. Use AWS Config to track changes.
3. Use AWS Organizations to set up the infrastructure. Use AWS Service Catalog to track changes.
4. Use AWS CloudFormation to set up the infrastructure. Use AWS Service Catalog to track changes.

---

### 666. High Availability Migration
A startup company is hosting a website for its customers on an Amazon EC2 instance. The website consists of a stateless Python application and a MySQL database. The website serves only a small amount of traffic. The company is concerned about the reliability of the instance and needs to migrate to a highly available architecture. The company cannot modify the application code.

Which combination of actions should a solutions architect take to achieve high availability for the website? (Choose two.)

**Options:**
1. Provision an internet gateway in each Availability Zone in use.
2. Migrate the database to an Amazon RDS for MySQL Multi-AZ DB instance.
3. Migrate the database to Amazon DynamoDB, and enable DynamoDB auto scaling.
4. Use AWS DataSync to synchronize the database data across multiple EC2 instances.
5. Create an Application Load Balancer to distribute traffic to an Auto Scaling group of EC2 instances that are distributed across two Availability Zones.

---

### 667. Secure S3 Access
A company is moving its data and applications to AWS during a multiyear migration project. The company wants to securely access data on Amazon S3 from the company's AWS Region and from the company's on-premises location. The data must not traverse the internet. The company has established an AWS Direct Connect connection between its Region and its on-premises location.

Which solution will meet these requirements?

**Options:**
1. Create gateway endpoints for Amazon S3. Use the gateway endpoints to securely access the data from the Region and the on-premises location.
2. Create a gateway in AWS Transit Gateway to access Amazon S3 securely from the Region and the on-premises location.
3. Create interface endpoints for Amazon S3. Use the interface endpoints to securely access the data from the Region and the on-premises location.
4. Use an AWS Key Management Service (AWS KMS) key to access the data securely from the Region and the on-premises location.

---

### 668. Tag Policy Management
A company created a new organization in AWS Organizations. The organization has multiple accounts for the company's development teams. The development team members use AWS IAM Identity Center (AWS Single Sign-On) to access the accounts. For each of the company's applications, the development teams must use a predefined application name to tag resources that are created.

A solutions architect needs to design a solution that gives the development team the ability to create resources only if the application name tag has an approved value.

Which solution will meet these requirements?

**Options:**
1. Create an IAM group that has a conditional Allow policy that requires the application name tag to be specified for resources to be created.
2. Create a cross-account role that has a Deny policy for any resource that has the application name tag.
3. Create a resource group in AWS Resource Groups to validate that the tags are applied to all resources in all accounts.
4. Create a tag policy in Organizations that has a list of allowed application names.

---

### 669. RDS Password Management
A company runs its databases on Amazon RDS for PostgreSQL. The company wants a secure solution to manage the master user password by rotating the password every 30 days.

Which solution will meet these requirements with the LEAST operational overhead?

**Options:**
1. Use Amazon EventBridge to schedule a custom AWS Lambda function to rotate the password every 30 days.
2. Use the modify-db-instance command in the AWS CLI to change the password.
3. Integrate AWS Secrets Manager with Amazon RDS for PostgreSQL to automate password rotation.
4. Integrate AWS Systems Manager Parameter Store with Amazon RDS for PostgreSQL to automate password rotation.

---

### 670. DynamoDB Cost Optimization
A company performs tests on an application that uses an Amazon DynamoDB table. The tests run for 4 hours once a week. The company knows how many read and write operations the application performs to the table each second during the tests. The company does not currently use DynamoDB for any other use case. A solutions architect needs to optimize the costs for the table.

Which solution will meet these requirements?

**Options:**
1. Choose on-demand mode. Update the read and write capacity units appropriately.
2. Choose provisioned mode. Update the read and write capacity units appropriately.
3. Purchase DynamoDB reserved capacity for a 1-year term.
4. Purchase DynamoDB reserved capacity for a 3-year term.

---

### 671. Cost Anomaly Detection
A company runs its applications on Amazon EC2 instances. The company performs periodic financial assessments of its AWS costs. The company recently identified unusual spending.

The company needs a solution to prevent unusual spending. The solution must monitor costs and notify responsible stakeholders in the event of unusual spending.

Which solution will meet these requirements?

**Options:**
1. Use an AWS Budgets template to create a zero spend budget.
2. Create an AWS Cost Anomaly Detection monitor in the AWS Billing and Cost Management console.
3. Create AWS Pricing Calculator estimates for the current running workload pricing details.
4. Use Amazon CloudWatch to monitor costs and to identify unusual spending.

---

### 672. S3 Data Analysis
A marketing company receives a large amount of new clickstream data in Amazon S3 from a marketing campaign. The company needs to analyze the clickstream data in Amazon S3 quickly. Then the company needs to determine whether to process the data further in the data pipeline.

Which solution will meet these requirements with the LEAST operational overhead?

**Options:**
1. Create external tables in a Spark catalog. Configure jobs in AWS Glue to query the data.
2. Configure an AWS Glue crawler to crawl the data. Configure Amazon Athena to query the data.
3. Create external tables in a Hive metastore. Configure Spark jobs in Amazon EMR to query the data.
4. Configure an AWS Glue crawler to crawl the data. Configure Amazon Kinesis Data Analytics to use SQL to query the data.

---

### 673. SMB File Server Migration
A company runs an SMB file server in its data center. The file server stores large files that the company frequently accesses for up to 7 days after the file creation date. After 7 days, the company needs to be able to access the files with a maximum retrieval time of 24 hours.

Which solution will meet these requirements?

**Options:**
1. Use AWS DataSync to copy data that is older than 7 days from the SMB file server to AWS.
2. Create an Amazon S3 File Gateway to increase the company's storage space. Create an S3 Lifecycle policy to transition the data to S3 Glacier Deep Archive after 7 days.
3. Create an Amazon FSx File Gateway to increase the company's storage space. Create an Amazon S3 Lifecycle policy to transition the data after 7 days.
4. Configure access to Amazon S3 for each user. Create an S3 Lifecycle policy to transition the data to S3 Glacier Flexible Retrieval after 7 days.

---

### 674. Database Performance Optimization
A company runs a web application on Amazon EC2 instances in an Auto Scaling group. The application uses a database that runs on an Amazon RDS for PostgreSQL DB instance. The application performs slowly when traffic increases. The database experiences a heavy read load during periods of high traffic.

Which actions should a solutions architect take to resolve these performance issues? (Choose two.)

**Options:**
1. Turn on auto scaling for the DB instance.
2. Create a read replica for the DB instance. Configure the application to send read traffic to the read replica.
3. Convert the DB instance to a Multi-AZ DB instance deployment. Configure the application to send read traffic to the standby DB instance.
4. Create an Amazon ElastiCache cluster. Configure the application to cache query results in the ElastiCache cluster.
5. Configure the Auto Scaling group subnets to ensure that the EC2 instances are provisioned in the same Availability Zone as the DB instance.

---

### 675. EBS Snapshot Protection
A company uses Amazon EC2 instances and Amazon Elastic Block Store (Amazon EBS) volumes to run an application. The company creates one snapshot of each EBS volume every day to meet compliance requirements. The company wants to implement an architecture that prevents the accidental deletion of EBS volume snapshots. The solution must not change the administrative rights of the storage administrator user.

Which solution will meet these requirements with the LEAST administrative effort?

**Options:**
1. Create an IAM role that has permission to delete snapshots. Attach the role to a new EC2 instance. Use the AWS CLI from the new EC2 instance to delete snapshots.
2. Create an IAM policy that denies snapshot deletion. Attach the policy to the storage administrator user.
3. Add tags to the snapshots. Create retention rules in Recycle Bin for EBS snapshots that have the tags.
4. Lock the EBS snapshots to prevent deletion.

---

### 676. VPC Flow Logs to OpenSearch
A company's application uses Network Load Balancers, Auto Scaling groups, Amazon EC2 instances, and databases that are deployed in an Amazon VPC. The company wants to capture information about traffic to and from the network interfaces in near real time in its Amazon VPC. The company wants to send the information to Amazon OpenSearch Service for analysis.

Which solution will meet these requirements?

**Options:**
1. Create a log group in Amazon CloudWatch Logs. Configure VPC Flow Logs to send the log data to the log group. Use Amazon Kinesis Data Streams to stream the logs from the log group to OpenSearch Service.
2. Create a log group in Amazon CloudWatch Logs. Configure VPC Flow Logs to send the log data to the log group. Use Amazon Kinesis Data Firehose to stream the logs from the log group to OpenSearch Service.
3. Create a trail in AWS CloudTrail. Configure VPC Flow Logs to send the log data to the trail. Use Amazon Kinesis Data Streams to stream the logs from the trail to OpenSearch Service.
4. Create a trail in AWS CloudTrail. Configure VPC Flow Logs to send the log data to the trail. Use Amazon Kinesis Data Firehose to stream the logs from the trail to OpenSearch Service.

---

### 677. EKS Development Cluster
A company is developing an application that will run on a production Amazon Elastic Kubernetes Service (Amazon EKS) cluster. The EKS cluster has managed node groups that are provisioned with On-Demand Instances.

The company needs a dedicated EKS cluster for development work. The company will use the development cluster infrequently to test the resiliency of the application. The EKS cluster must manage all the nodes.

Which solution will meet these requirements MOST cost-effectively?

**Options:**
1. Create a managed node group that contains only Spot Instances.
2. Create two managed node groups. Provision one node group with On-Demand Instances. Provision the second node group with Spot Instances.
3. Create an Auto Scaling group that has a launch configuration that uses Spot Instances. Configure the user data to add the nodes to the EKS cluster.
4. Create a managed node group that contains only On-Demand Instances.

---

### 678. S3 Encryption Key Management
A company stores sensitive data in Amazon S3. A solutions architect needs to create an encryption solution. The company needs to fully control the ability of users to create, rotate, and disable encryption keys with minimal effort for any data that must be encrypted.

Which solution will meet these requirements?

**Options:**
1. Use default server-side encryption with Amazon S3 managed encryption keys (SSE-S3) to store the sensitive data.
2. Create a customer managed key by using AWS Key Management Service (AWS KMS). Use the new key to encrypt the S3 objects by using server-side encryption with AWS KMS keys (SSE-KMS).
3. Create an AWS managed key by using AWS Key Management Service (AWS KMS). Use the new key to encrypt the S3 objects by using server-side encryption with AWS KMS keys (SSE-KMS).
4. Download S3 objects to an Amazon EC2 instance. Encrypt the objects by using customer managed keys. Upload the encrypted objects back into Amazon S3.

---

### 679. VM Backup Retention
A company wants to back up its on-premises virtual machines (VMs) to AWS. The company's backup solution exports on-premises backups to an Amazon S3 bucket as objects. The S3 backups must be retained for 30 days and must be automatically deleted after 30 days.

Which combination of steps will meet these requirements? (Choose three.)

**Options:**
1. Create an S3 bucket that has S3 Object Lock enabled.
2. Create an S3 bucket that has object versioning enabled.
3. Configure a default retention period of 30 days for the objects.
4. Configure an S3 Lifecycle policy to protect the objects for 30 days.
5. Configure an S3 Lifecycle policy to expire the objects after 30 days.
6. Configure the backup solution to tag the objects with a 30-day retention period.

---

### 680. File Synchronization
A solutions architect needs to copy files from an Amazon S3 bucket to an Amazon Elastic File System (Amazon EFS) file system and another S3 bucket. The files must be copied continuously. New files are added to the original S3 bucket consistently. The copied files should be overwritten only if the source file changes.

Which solution will meet these requirements with the LEAST operational overhead?

**Options:**
1. Create an AWS DataSync location for both the destination S3 bucket and the EFS file system. Create a task for the destination S3 bucket and the EFS file system. Set the transfer mode to transfer only data that has changed.
2. Create an AWS Lambda function. Mount the file system to the function. Set up an S3 event notification to invoke the function when files are created and changed in Amazon S3. Configure the function to copy files to the file system and the destination S3 bucket.
3. Create an AWS DataSync location for both the destination S3 bucket and the EFS file system. Create a task for the destination S3 bucket and the EFS file system. Set the transfer mode to transfer all data.
4. Launch an Amazon EC2 instance in the same VPC as the file system. Mount the file system. Create a script to routinely synchronize all objects that changed in the origin S3 bucket to the destination S3 bucket and the mounted file system.

---

### 681. EBS Encryption Key Control
A company uses Amazon EC2 instances and stores data on Amazon Elastic Block Store (Amazon EBS) volumes. The company must ensure that all data is encrypted at rest by using AWS Key Management Service (AWS KMS). The company must be able to control rotation of the encryption keys.

Which solution will meet these requirements with the LEAST operational overhead?

**Options:**
1. Create a customer managed key. Use the key to encrypt the EBS volumes.
2. Use an AWS managed key to encrypt the EBS volumes. Use the key to configure automatic key rotation.
3. Create an external KMS key with imported key material. Use the key to encrypt the EBS volumes.
4. Use an AWS owned key to encrypt the EBS volumes.

---

### 682. Compliance Automation
A company needs a solution to enforce data encryption at rest on Amazon EC2 instances. The solution must automatically identify noncompliant resources and enforce compliance policies on findings.

Which solution will meet these requirements with the LEAST administrative overhead?

**Options:**
1. Use an IAM policy that allows users to create only encrypted Amazon Elastic Block Store (Amazon EBS) volumes. Use AWS Config and AWS Systems Manager to automate the detection and remediation of unencrypted EBS volumes.
2. Use AWS Key Management Service (AWS KMS) to manage access to encrypted Amazon Elastic Block Store (Amazon EBS) volumes. Use AWS Lambda and Amazon EventBridge to automate the detection and remediation of unencrypted EBS volumes.
3. Use Amazon Macie to detect unencrypted Amazon Elastic Block Store (Amazon EBS) volumes. Use AWS Systems Manager Automation rules to automatically encrypt existing and new EBS volumes.
4. Use Amazon Inspector to detect unencrypted Amazon Elastic Block Store (Amazon EBS) volumes. Use AWS Systems Manager Automation rules to automatically encrypt existing and new EBS volumes.

---

### 683. Multi-tier Application Migration
A company is migrating its multi-tier on-premises application to AWS. The application consists of a single-node MySQL database and a multi-node web tier. The company must minimize changes to the application during the migration. The company wants to improve application resiliency after the migration.

Which combination of steps will meet these requirements? (Choose two.)

**Options:**
1. Migrate the web tier to Amazon EC2 instances in an Auto Scaling group behind an Application Load Balancer.
2. Migrate the database to Amazon EC2 instances in an Auto Scaling group behind a Network Load Balancer.
3. Migrate the database to an Amazon RDS Multi-AZ deployment.
4. Migrate the web tier to an AWS Lambda function.
5. Migrate the database to an Amazon DynamoDB table.

---

### 684. Low Latency Regional Deployment
A company wants to migrate its web applications from on premises to AWS. The company is located close to the eu-central-1 Region. Because of regulations, the company cannot launch some of its applications in eu-central-1. The company wants to achieve single-digit millisecond latency.

Which solution will meet these requirements?

**Options:**
1. Deploy the applications in eu-central-1. Extend the company's VPC from eu-central-1 to an edge location in Amazon CloudFront.
2. Deploy the applications in AWS Local Zones by extending the company's VPC from eu-central-1 to the chosen Local Zone.
3. Deploy the applications in eu-central-1. Extend the company's VPC from eu-central-1 to the regional edge caches in Amazon CloudFront.
4. Deploy the applications in AWS Wavelength Zones by extending the company's VPC from eu-central-1 to the chosen Wavelength Zone.

---

### 685. Lambda RDS Connection Management
A company's ecommerce website has unpredictable traffic and uses AWS Lambda functions to directly access a private Amazon RDS for PostgreSQL DB instance. The company wants to maintain predictable database performance and ensure that the Lambda invocations do not overload the database with too many connections.

What should a solutions architect do to meet these requirements?

**Options:**
1. Point the client driver at an RDS custom endpoint. Deploy the Lambda functions inside a VPC.
2. Point the client driver at an RDS proxy endpoint. Deploy the Lambda functions inside a VPC.
3. Point the client driver at an RDS custom endpoint. Deploy the Lambda functions outside a VPC.
4. Point the client driver at an RDS proxy endpoint. Deploy the Lambda functions outside a VPC.

---

## Answer Key

| Question | Correct Answer(s) | Topic |
|----------|-------------------|--------|
| 651 | 3 | S3 Lifecycle Management |
| 652 | 2 | EMR Cluster Configuration |
| 653 | 2 | Resource Tagging Automation |
| 654 | 4 | Web Application Modernization |
| 655 | 3,5 | Load Balancer with WAF |
| 656 | 4 | S3 Storage Classes |
| 657 | 2 | Security Group Management |
| 658 | 1,5 | HPC File Systems |
| 659 | 3 | Data Transfer Services |
| 660 | 4 | Auto Scaling Policies |
| 661 | 2 | RDS Connection Pooling |
| 662 | 4 | EBS Cost Optimization |
| 663 | 3 | ECS Security |
| 664 | 1 | Elastic Beanstalk Scaling |
| 665 | 2 | Infrastructure as Code |
| 666 | 2,5 | High Availability Architecture |
| 667 | 1 | VPC Endpoints |
| 668 | 4 | Tag Policies |
| 669 | 3 | Password Management |
| 670 | 2 | DynamoDB Pricing Models |
| 671 | 2 | Cost Monitoring |
| 672 | 2 | S3 Data Analytics |
| 673 | 4 | File Server Migration |
| 674 | 2,4 | Database Performance |
| 675 | 3 | EBS Snapshot Protection |
| 676 | 2 | VPC Flow Logs |
| 677 | 1 | EKS Cost Optimization |
| 678 | 2 | S3 Encryption |
| 679 | 2,5,6 | Backup Retention |
| 680 | 1 | File Synchronization |
| 681 | 1 | EBS Encryption |
| 682 | 1 | Compliance Automation |
| 683 | 1,3 | Application Migration |
| 684 | 2 | Low Latency Deployment |
| 685 | 2 | Lambda Database Connections |

---

## Study Tips

### Key AWS Services Covered
- **Storage**: S3, EBS, EFS, FSx
- **Compute**: EC2, Lambda, ECS, EKS
- **Database**: RDS, DynamoDB
- **Networking**: VPC, Load Balancers, VPC Endpoints
- **Security**: IAM, KMS, WAF, Organizations
- **Monitoring**: CloudWatch, Config, Cost Explorer
- **Data Transfer**: DataSync, Snowball, Direct Connect

### Common Architectural Patterns
1. **High Availability**: Multi-AZ deployments, Auto Scaling, Load Balancing
2. **Cost Optimization**: Right-sizing, Reserved Capacity, Lifecycle Policies
3. **Security**: Encryption at rest/transit, VPC endpoints, IAM policies
4. **Performance**: Caching, Read Replicas, Placement Groups
5. **Operational Excellence**: Infrastructure as Code, Automation, Monitoring

### Important Concepts for Microservices
- **Container Orchestration**: ECS, EKS for microservices deployment
- **Service Discovery**: Application Load Balancers, service mesh patterns
- **Database Per Service**: RDS, DynamoDB for individual microservice data stores
- **API Gateway**: For microservices communication and management
- **Monitoring**: Distributed tracing, centralized logging
- **Security**: Service-to-service authentication, network segmentation

---

## Contributing
Feel free to contribute additional questions or corrections by submitting a pull request.

## License
This repository is for educational purposes only.
