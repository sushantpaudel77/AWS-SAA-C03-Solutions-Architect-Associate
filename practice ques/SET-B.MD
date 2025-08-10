# AWS Solutions Architect Associate Practice Questions

This repository contains practice questions for the AWS Solutions Architect Associate certification exam. These questions cover various AWS services and architectural best practices.

## Questions 66-115

### Question 66
A company has an application that generates a large number of files, each approximately 5 MB in size. The files are stored in Amazon S3. Company policy requires the files to be stored for 4 years before they can be deleted. Immediate accessibility is always required as the files contain critical business data that is not easy to reproduce. The files are frequently accessed in the first 30 days of object creation but are rarely accessed after the first 30 days.

**Which storage solution is MOST cost-effective?**

A) Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Glacier 30 days from object creation. Delete the files 4 years after object creation.

B) Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) 30 days from object creation. Delete the files 4 years after object creation.

C) Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Delete the files 4 years after object creation.

D) Create an S3 bucket lifecycle policy to move files from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) 30 days from object creation. Move the files to S3 Glacier 4 years after object creation.

---

### Question 67
A company hosts an application on multiple Amazon EC2 instances. The application processes messages from an Amazon SQS queue, writes to an Amazon RDS table, and deletes the message from the queue. Occasional duplicate records are found in the RDS table. The SQS queue does not contain any duplicate messages.

**What should a solutions architect do to ensure messages are being processed once only?**

A) Use the CreateQueue API call to create a new queue.

B) Use the AddPermission API call to add appropriate permissions.

C) Use the ReceiveMessage API call to set an appropriate wait time.

D) Use the ChangeMessageVisibility API call to increase the visibility timeout.

---

### Question 68
A solutions architect is designing a new hybrid architecture to extend a company's on-premises infrastructure to AWS. The company requires a highly available connection with consistent low latency to an AWS Region. The company needs to minimize costs and is willing to accept slower traffic if the primary connection fails.

**What should the solutions architect do to meet these requirements?**

A) Provision an AWS Direct Connect connection to a Region. Provision a VPN connection as a backup if the primary Direct Connect connection fails.

B) Provision a VPN tunnel connection to a Region for private connectivity. Provision a second VPN tunnel for private connectivity and as a backup if the primary VPN connection fails.

C) Provision an AWS Direct Connect connection to a Region. Provision a second Direct Connect connection to the same Region as a backup if the primary Direct Connect connection fails.

D) Provision an AWS Direct Connect connection to a Region. Use the Direct Connect failover attribute from the AWS CLI to automatically create a backup connection if the primary Direct Connect connection fails.

---

### Question 69
A company is running a business-critical web application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances are in an Auto Scaling group. The application uses an Amazon Aurora PostgreSQL database that is deployed in a single Availability Zone. The company wants the application to be highly available with minimum downtime and minimum loss of data.

**Which solution will meet these requirements with the LEAST operational effort?**

A) Place the EC2 instances in different AWS Regions. Use Amazon Route 53 health checks to redirect traffic. Use Aurora PostgreSQL Cross-Region Replication.

B) Configure the Auto Scaling group to use multiple Availability Zones. Configure the database as Multi-AZ. Configure an Amazon RDS Proxy instance for the database.

C) Configure the Auto Scaling group to use one Availability Zone. Generate hourly snapshots of the database. Recover the database from the snapshots in the event of a failure.

D) Configure the Auto Scaling group to use multiple AWS Regions. Write the data from the application to Amazon S3. Use S3 Event Notifications to launch an AWS Lambda function to write the data to the database.

---

### Question 70
A company's HTTP application is behind a Network Load Balancer (NLB). The NLB's target group is configured to use an Amazon EC2 Auto Scaling group with multiple EC2 instances that run the web service. The company notices that the NLB is not detecting HTTP errors for the application. These errors require a manual restart of the EC2 instances that run the web service. The company needs to improve the application's availability without writing custom scripts or code.

**What should a solutions architect do to meet these requirements?**

A) Enable HTTP health checks on the NLB, supplying the URL of the company's application.

B) Add a cron job to the EC2 instances to check the local application's logs once each minute. If HTTP errors are detected, the application will restart.

C) Replace the NLB with an Application Load Balancer. Enable HTTP health checks by supplying the URL of the company's application. Configure an Auto Scaling action to replace unhealthy instances.

D) Create an Amazon CloudWatch alarm that monitors the UnhealthyHostCount metric for the NLB. Configure an Auto Scaling action to replace unhealthy instances when the alarm is in the ALARM state.

---

### Question 71
A company runs a shopping application that uses Amazon DynamoDB to store customer information. In case of data corruption, a solutions architect needs to design a solution that meets a recovery point objective (RPO) of 15 minutes and a recovery time objective (RTO) of 1 hour.

**What should the solutions architect recommend to meet these requirements?**

A) Configure DynamoDB global tables. For RPO recovery, point the application to a different AWS Region.

B) Configure DynamoDB point-in-time recovery. For RPO recovery, restore to the desired point in time.

C) Export the DynamoDB data to Amazon S3 Glacier on a daily basis. For RPO recovery, import the data from S3 Glacier to DynamoDB.

D) Schedule Amazon Elastic Block Store (Amazon EBS) snapshots for the DynamoDB table every 15 minutes. For RPO recovery, restore the DynamoDB table by using the EBS snapshot.

---

### Question 72
A company runs a photo processing application that needs to frequently upload and download pictures from Amazon S3 buckets that are located in the same AWS Region. A solutions architect has noticed an increased cost in data transfer fees and needs to implement a solution to reduce these costs.

**How can the solutions architect meet this requirement?**

A) Deploy Amazon API Gateway into a public subnet and adjust the route table to route S3 calls through it.

B) Deploy a NAT gateway into a public subnet and attach an endpoint policy that allows access to the S3 buckets.

C) Deploy the application into a public subnet and allow it to route through an internet gateway to access the S3 buckets.

D) Deploy an S3 VPC gateway endpoint into the VPC and attach an endpoint policy that allows access to the S3 buckets.

---

### Question 73
A company recently launched Linux-based application instances on Amazon EC2 in a private subnet and launched a Linux-based bastion host on an Amazon EC2 instance in a public subnet of a VPC. A solutions architect needs to connect from the on-premises network, through the company's internet connection, to the bastion host, and to the application servers. The solutions architect must make sure that the security groups of all the EC2 instances will allow that access.

**Which combination of steps should the solutions architect take to meet these requirements? (Choose two.)**

A) Replace the current security group of the bastion host with one that only allows inbound access from the application instances.

B) Replace the current security group of the bastion host with one that only allows inbound access from the internal IP range for the company.

C) Replace the current security group of the bastion host with one that only allows inbound access from the external IP range for the company.

D) Replace the current security group of the application instances with one that allows inbound SSH access from only the private IP address of the bastion host.

E) Replace the current security group of the application instances with one that allows inbound SSH access from only the public IP address of the bastion host.

---

### Question 74
A solutions architect is designing a two-tier web application. The application consists of a public-facing web tier hosted on Amazon EC2 in public subnets. The database tier consists of Microsoft SQL Server running on Amazon EC2 in a private subnet. Security is a high priority for the company.

**How should security groups be configured in this situation? (Choose two.)**

A) Configure the security group for the web tier to allow inbound traffic on port 443 from 0.0.0.0/0.

B) Configure the security group for the web tier to allow outbound traffic on port 443 from 0.0.0.0/0.

C) Configure the security group for the database tier to allow inbound traffic on port 1433 from the security group for the web tier.

D) Configure the security group for the database tier to allow outbound traffic on ports 443 and 1433 to the security group for the web tier.

E) Configure the security group for the database tier to allow inbound traffic on ports 443 and 1433 from the security group for the web tier.

---

### Question 75
A company wants to move a multi-tiered application from on premises to the AWS Cloud to improve the application's performance. The application consists of application tiers that communicate with each other by way of RESTful services. Transactions are dropped when one tier becomes overloaded. A solutions architect must design a solution that resolves these issues and modernizes the application.

**Which solution meets these requirements and is the MOST operationally efficient?**

A) Use Amazon API Gateway and direct transactions to the AWS Lambda functions as the application layer. Use Amazon Simple Queue Service (Amazon SQS) as the communication layer between application services.

B) Use Amazon CloudWatch metrics to analyze the application performance history to determine the servers' peak utilization during the performance failures. Increase the size of the application server's Amazon EC2 instances to meet the peak requirements.

C) Use Amazon Simple Notification Service (Amazon SNS) to handle the messaging between application servers running on Amazon EC2 in an Auto Scaling group. Use Amazon CloudWatch to monitor the SNS queue length and scale up and down as required.

D) Use Amazon Simple Queue Service (Amazon SQS) to handle the messaging between application servers running on Amazon EC2 in an Auto Scaling group. Use Amazon CloudWatch to monitor the SQS queue length and scale up when communication failures are detected.

---

### Question 76
A company receives 10 TB of instrumentation data each day from several machines located at a single factory. The data consists of JSON files stored on a storage area network (SAN) in an on-premises data center located within the factory. The company wants to send this data to Amazon S3 where it can be accessed by several additional systems that provide critical near-real-time analytics. A secure transfer is important because the data is considered sensitive.

**Which solution offers the MOST reliable data transfer?**

A) AWS DataSync over public internet

B) AWS DataSync over AWS Direct Connect

C) AWS Database Migration Service (AWS DMS) over public internet

D) AWS Database Migration Service (AWS DMS) over AWS Direct Connect

---

### Question 77
A company needs to configure a real-time data ingestion architecture for its application. The company needs an API, a process that transforms data as the data is streamed, and a storage solution for the data.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Deploy an Amazon EC2 instance to host an API that sends data to an Amazon Kinesis data stream. Create an Amazon Kinesis Data Firehose delivery stream that uses the Kinesis data stream as a data source. Use AWS Lambda functions to transform the data. Use the Kinesis Data Firehose delivery stream to send the data to Amazon S3.

B) Deploy an Amazon EC2 instance to host an API that sends data to AWS Glue. Stop source/destination checking on the EC2 instance. Use AWS Glue to transform the data and to send the data to Amazon S3.

C) Configure an Amazon API Gateway API to send data to an Amazon Kinesis data stream. Create an Amazon Kinesis Data Firehose delivery stream that uses the Kinesis data stream as a data source. Use AWS Lambda functions to transform the data. Use the Kinesis Data Firehose delivery stream to send the data to Amazon S3.

D) Configure an Amazon API Gateway API to send data to AWS Glue. Use AWS Lambda functions to transform the data. Use AWS Glue to send the data to Amazon S3.

---

### Question 78
A company needs to keep user transaction data in an Amazon DynamoDB table. The company must retain the data for 7 years.

**What is the MOST operationally efficient solution that meets these requirements?**

A) Use DynamoDB point-in-time recovery to back up the table continuously.

B) Use AWS Backup to create backup schedules and retention policies for the table.

C) Create an on-demand backup of the table by using the DynamoDB console. Store the backup in an Amazon S3 bucket. Set an S3 Lifecycle configuration for the S3 bucket.

D) Create an Amazon EventBridge (Amazon CloudWatch Events) rule to invoke an AWS Lambda function. Configure the Lambda function to back up the table and to store the backup in an Amazon S3 bucket. Set an S3 Lifecycle configuration for the S3 bucket.

---

### Question 79
A company is planning to use an Amazon DynamoDB table for data storage. The company is concerned about cost optimization. The table will not be used on most mornings. In the evenings, the read and write traffic will often be unpredictable. When traffic spikes occur, they will happen very quickly.

**What should a solutions architect recommend?**

A) Create a DynamoDB table in on-demand capacity mode.

B) Create a DynamoDB table with a global secondary index.

C) Create a DynamoDB table with provisioned capacity and auto scaling.

D) Create a DynamoDB table in provisioned capacity mode, and configure it as a global table.

---

### Question 80
A company recently signed a contract with an AWS Managed Service Provider (MSP) Partner for help with an application migration initiative. A solutions architect needs to share an Amazon Machine Image (AMI) from an existing AWS account with the MSP Partner's AWS account. The AMI is backed by Amazon Elastic Block Store (Amazon EBS) and uses an AWS Key Management Service (AWS KMS) customer managed key to encrypt EBS volume snapshots.

**What is the MOST secure way for the solutions architect to share the AMI with the MSP Partner's AWS account?**

A) Make the encrypted AMI and snapshots publicly available. Modify the key policy to allow the MSP Partner's AWS account to use the key.

B) Modify the launchPermission property of the AMI. Share the AMI with the MSP Partner's AWS account only. Modify the key policy to allow the MSP Partner's AWS account to use the key.

C) Modify the launchPermission property of the AMI. Share the AMI with the MSP Partner's AWS account only. Modify the key policy to trust a new KMS key that is owned by the MSP Partner for encryption.

D) Export the AMI from the source account to an Amazon S3 bucket in the MSP Partner's AWS account. Encrypt the S3 bucket with a new KMS key that is owned by the MSP Partner. Copy and launch the AMI in the MSP Partner's AWS account.

---

### Question 81
A solutions architect is designing the cloud architecture for a new application being deployed on AWS. The process should run in parallel while adding and removing application nodes as needed based on the number of jobs to be processed. The processor application is stateless. The solutions architect must ensure that the application is loosely coupled and the job items are durably stored.

**Which design should the solutions architect use?**

A) Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch configuration that uses the AMI. Create an Auto Scaling group using the launch configuration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on CPU usage.

B) Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch configuration that uses the AMI. Create an Auto Scaling group using the launch configuration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on network usage.

C) Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of items in the SQS queue.

D) Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of messages published to the SNS topic.

---

### Question 82
A company hosts its web applications in the AWS Cloud. The company configures Elastic Load Balancers to use certificates that are imported into AWS Certificate Manager (ACM). The company's security team must be notified 30 days before the expiration of each certificate.

**What should a solutions architect recommend to meet this requirement?**

A) Add a rule in ACM to publish a custom message to an Amazon Simple Notification Service (Amazon SNS) topic every day, beginning 30 days before any certificate will expire.

B) Create an AWS Config rule that checks for certificates that will expire within 30 days. Configure Amazon EventBridge (Amazon CloudWatch Events) to invoke a custom alert by way of Amazon Simple Notification Service (Amazon SNS) when AWS Config reports a noncompliant resource.

C) Use AWS Trusted Advisor to check for certificates that will expire within 30 days. Create an Amazon CloudWatch alarm that is based on Trusted Advisor metrics for check status changes. Configure the alarm to send a custom alert by way of Amazon Simple Notification Service (Amazon SNS).

D) Create an Amazon EventBridge (Amazon CloudWatch Events) rule to detect any certificates that will expire within 30 days. Configure the rule to invoke an AWS Lambda function. Configure the Lambda function to send a custom alert by way of Amazon Simple Notification Service (Amazon SNS).

---

### Question 83
A company's dynamic website is hosted using on-premises servers in the United States. The company is launching its product in Europe, and it wants to optimize site loading times for new European users. The site's backend must remain in the United States. The product is being launched in a few days, and an immediate solution is needed.

**What should the solutions architect recommend?**

A) Launch an Amazon EC2 instance in us-east-1 and migrate the site to it.

B) Move the website to Amazon S3. Use Cross-Region Replication between Regions.

C) Use Amazon CloudFront with a custom origin pointing to the on-premises servers.

D) Use an Amazon Route 53 geoproximity routing policy pointing to on-premises servers.

---

### Question 84
A company wants to reduce the cost of its existing three-tier web architecture. The web, application, and database servers are running on Amazon EC2 instances for the development, test, and production environments. The EC2 instances average 30% CPU utilization during peak hours and 10% CPU utilization during non-peak hours. The production EC2 instances run 24 hours a day. The development and test EC2 instances run for at least 8 hours each day. The company plans to implement automation to stop the development and test EC2 instances when they are not in use.

**Which EC2 instance purchasing solution will meet the company's requirements MOST cost-effectively?**

A) Use Spot Instances for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.

B) Use Reserved Instances for the production EC2 instances. Use On-Demand Instances for the development and test EC2 instances.

C) Use Spot blocks for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.

D) Use On-Demand Instances for the production EC2 instances. Use Spot blocks for the development and test EC2 instances.

---

### Question 85
A company has a production web application in which users upload documents through a web interface or a mobile app. According to a new regulatory requirement, new documents cannot be modified or deleted after they are stored.

**What should a solutions architect do to meet this requirement?**

A) Store the uploaded documents in an Amazon S3 bucket with S3 Versioning and S3 Object Lock enabled.

B) Store the uploaded documents in an Amazon S3 bucket. Configure an S3 Lifecycle policy to archive the documents periodically.

C) Store the uploaded documents in an Amazon S3 bucket with S3 Versioning enabled. Configure an ACL to restrict all access to read-only.

D) Store the uploaded documents on an Amazon Elastic File System (Amazon EFS) volume. Access the data by mounting the volume in read-only mode.

---

### Question 86
A company has several web servers that need to frequently access a common Amazon RDS MySQL Multi-AZ DB instance. The company wants a secure method for the web servers to connect to the database while meeting a security requirement to rotate user credentials frequently.

**Which solution meets these requirements?**

A) Store the database user credentials in AWS Secrets Manager. Grant the necessary IAM permissions to allow the web servers to access AWS Secrets Manager.

B) Store the database user credentials in AWS Systems Manager OpsCenter. Grant the necessary IAM permissions to allow the web servers to access OpsCenter.

C) Store the database user credentials in a secure Amazon S3 bucket. Grant the necessary IAM permissions to allow the web servers to retrieve credentials and access the database.

D) Store the database user credentials in files encrypted with AWS Key Management Service (AWS KMS) on the web server file system. The web server should be able to decrypt the files and access the database.

---

### Question 87
A company hosts an application on AWS Lambda functions that are invoked by an Amazon API Gateway API. The Lambda functions save customer data to an Amazon Aurora MySQL database. Whenever the company upgrades the database, the Lambda functions fail to establish database connections until the upgrade is complete. The result is that customer data is not recorded for some of the events. A solutions architect needs to design a solution that stores customer data that is created during database upgrades.

**Which solution will meet these requirements?**

A) Provision an Amazon RDS proxy to sit between the Lambda functions and the database. Configure the Lambda functions to connect to the RDS proxy.

B) Increase the run time of the Lambda functions to the maximum. Create a retry mechanism in the code that stores the customer data in the database.

C) Persist the customer data to Lambda local storage. Configure new Lambda functions to scan the local storage to save the customer data to the database.

D) Store the customer data in an Amazon Simple Queue Service (Amazon SQS) FIFO queue. Create a new Lambda function that polls the queue and stores the customer data in the database.

---

### Question 88
A survey company has gathered data for several years from areas in the United States. The company hosts the data in an Amazon S3 bucket that is 3 TB in size and growing. The company has started to share the data with a European marketing firm that has S3 buckets. The company wants to ensure that its data transfer costs remain as low as possible.

**Which solution will meet these requirements?**

A) Configure the Requester Pays feature on the company's S3 bucket.

B) Configure S3 Cross-Region Replication from the company's S3 bucket to one of the marketing firm's S3 buckets.

C) Configure cross-account access for the marketing firm so that the marketing firm has access to the company's S3 bucket.

D) Configure the company's S3 bucket to use S3 Intelligent-Tiering. Sync the S3 bucket to one of the marketing firm's S3 buckets.

---

### Question 89
A company uses Amazon S3 to store its confidential audit documents. The S3 bucket uses bucket policies to restrict access to audit team IAM user credentials according to the principle of least privilege. Company managers are worried about accidental deletion of documents in the S3 bucket and want a more secure solution.

**What should a solutions architect do to secure the audit documents?**

A) Enable the versioning and MFA Delete features on the S3 bucket.

B) Enable multi-factor authentication (MFA) on the IAM user credentials for each audit team IAM user account.

C) Add an S3 Lifecycle policy to the audit team's IAM user accounts to deny the s3:DeleteObject action during audit dates.

D) Use AWS Key Management Service (AWS KMS) to encrypt the S3 bucket and restrict audit team IAM user accounts from accessing the KMS key.

---

### Question 90
A company is using a SQL database to store movie data that is publicly accessible. The database runs on an Amazon RDS Single-AZ DB instance. A script runs queries at random intervals each day to record the number of new movies that have been added to the database. The script must report a final total during business hours. The company's development team notices that the database performance is inadequate for development tasks when the script is running. A solutions architect must recommend a solution to resolve this issue.

**Which solution will meet this requirement with the LEAST operational overhead?**

A) Modify the DB instance to be a Multi-AZ deployment.

B) Create a read replica of the database. Configure the script to query only the read replica.

C) Instruct the development team to manually export the entries in the database at the end of each day.

D) Use Amazon ElastiCache to cache the common queries that the script runs against the database.

---

### Question 91
A company has applications that run on Amazon EC2 instances in a VPC. One of the applications needs to call the Amazon S3 API to store and read objects. According to the company's security regulations, no traffic from the applications is allowed to travel across the internet.

**Which solution will meet these requirements?**

A) Configure an S3 gateway endpoint.

B) Create an S3 bucket in a private subnet.

C) Create an S3 bucket in the same AWS Region as the EC2 instances.

D) Configure a NAT gateway in the same subnet as the EC2 instances.

---

### Question 92
A company is storing sensitive user information in an Amazon S3 bucket. The company wants to provide secure access to this bucket from the application tier running on Amazon EC2 instances inside a VPC.

**Which combination of steps should a solutions architect take to accomplish this? (Choose two.)**

A) Configure a VPC gateway endpoint for Amazon S3 within the VPC.

B) Create a bucket policy to make the objects in the S3 bucket public.

C) Create a bucket policy that limits access to only the application tier running in the VPC.

D) Create an IAM user with an S3 access policy and copy the IAM credentials to the EC2 instance.

E) Create a NAT instance and have the EC2 instances use the NAT instance to access the S3 bucket.

---

### Question 93
A company runs an on-premises application that is powered by a MySQL database. The company is migrating the application to AWS to increase the application's elasticity and availability. The current architecture shows heavy read activity on the database during times of normal operation. Every 4 hours, the company's development team pulls a full export of the production database to populate a database in the staging environment. During this period, users experience unacceptable application latency. The development team is unable to use the staging environment until the procedure completes. A solutions architect must recommend replacement architecture that alleviates the application latency issue. The replacement architecture also must give the development team the ability to continue using the staging environment without delay.

**Which solution meets these requirements?**

A) Use Amazon Aurora MySQL with Multi-AZ Aurora Replicas for production. Populate the staging database by implementing a backup and restore process that uses the mysqldump utility.

B) Use Amazon Aurora MySQL with Multi-AZ Aurora Replicas for production. Use database cloning to create the staging database on-demand.

C) Use Amazon RDS for MySQL with a Multi-AZ deployment and read replicas for production. Use the standby instance for the staging database.

D) Use Amazon RDS for MySQL with a Multi-AZ deployment and read replicas for production. Populate the staging database by implementing a backup and restore process that uses the mysqldump utility.

---

### Question 94
A company is designing an application where users upload small files into Amazon S3. After a user uploads a file, the file requires one-time simple processing to transform the data and save the data in JSON format for later analysis. Each file must be processed as quickly as possible after it is uploaded. Demand will vary. On some days, users will upload a high number of files. On other days, users will upload a few files or no files.

**Which solution meets these requirements with the LEAST operational overhead?**

A) Configure Amazon EMR to read text files from Amazon S3. Run processing scripts to transform the data. Store the resulting JSON file in an Amazon Aurora DB cluster.

B) Configure Amazon S3 to send an event notification to an Amazon Simple Queue Service (Amazon SQS) queue. Use Amazon EC2 instances to read from the queue and process the data. Store the resulting JSON file in Amazon DynamoDB.

C) Configure Amazon S3 to send an event notification to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function to read from the queue and process the data. Store the resulting JSON file in Amazon DynamoDB.

D) Configure Amazon EventBridge (Amazon CloudWatch Events) to send an event to Amazon Kinesis Data Streams when a new file is uploaded. Use an AWS Lambda function to consume the event from the stream and process the data. Store the resulting JSON file in an Amazon Aurora DB cluster.

---

### Question 95
An application allows users at a company's headquarters to access product data. The product data is stored in an Amazon RDS MySQL DB instance. The operations team has isolated an application performance slowdown and wants to separate read traffic from write traffic. A solutions architect needs to optimize the application's performance quickly.

**What should the solutions architect recommend?**

A) Change the existing database to a Multi-AZ deployment. Serve the read requests from the primary Availability Zone.

B) Change the existing database to a Multi-AZ deployment. Serve the read requests from the secondary Availability Zone.

C) Create read replicas for the database. Configure the read replicas with half of the compute and storage resources as the source database.

D) Create read replicas for the database. Configure the read replicas with the same compute and storage resources as the source database.

---

### Question 96
An Amazon EC2 administrator created the following policy associated with an IAM group containing several users:

**What is the effect of this policy?**

A) Users can terminate an EC2 instance in any AWS Region except us-east-1.

B) Users can terminate an EC2 instance with the IP address 10.100.100.1 in the us-east-1 Region.

C) Users can terminate an EC2 instance in the us-east-1 Region when the user's source IP is 10.100.100.254.

D) Users cannot terminate an EC2 instance in the us-east-1 Region when the user's source IP is 10.100.100.254.

---

### Question 97
A company has a large Microsoft SharePoint deployment running on-premises that requires Microsoft Windows shared file storage. The company wants to migrate this workload to the AWS Cloud and is considering various storage options. The storage solution must be highly available and integrated with Active Directory for access control.

**Which solution will satisfy these requirements?**

A) Configure Amazon EFS storage and set the Active Directory domain for authentication.

B) Create an SMB file share on an AWS Storage Gateway file gateway in two Availability Zones.

C) Create an Amazon S3 bucket and configure Microsoft Windows Server to mount it as a volume.

D) Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

---

### Question 100
A company's containerized application runs on an Amazon EC2 instance. The application needs to download security certificates before it can communicate with other business applications. The company wants a highly secure solution to encrypt and decrypt the certificates in near real time. The solution also needs to store data in highly available storage after the data is encrypted.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Create AWS Secrets Manager secrets for encrypted certificates. Manually update the certificates as needed. Control access to the data by using fine-grained IAM access.

B) Create an AWS Lambda function that uses the Python cryptography library to receive and perform encryption operations. Store the function in an Amazon S3 bucket.

C) Create an AWS Key Management Service (AWS KMS) customer managed key. Allow the EC2 role to use the KMS key for encryption operations. Store the encrypted data on Amazon S3.

D) Create an AWS Key Management Service (AWS KMS) customer managed key. Allow the EC2 role to use the KMS key for encryption operations. Store the encrypted data on Amazon Elastic Block Store (Amazon EBS) volumes.

---

### Question 101
A solutions architect is designing a VPC with public and private subnets. The VPC and subnets use IPv4 CIDR blocks. There is one public subnet and one private subnet in each of three Availability Zones (AZs) for high availability. An internet gateway is used to provide internet access for the public subnets. The private subnets require access to the internet to allow Amazon EC2 instances to download software updates.

**What should the solutions architect do to enable Internet access for the private subnets?**

A) Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT gateway in its AZ.

B) Create three NAT instances, one for each private subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT instance in its AZ.

C) Create a second internet gateway on one of the private subnets. Update the route table for the private subnets that forward non-VPC traffic to the private internet gateway.

D) Create an egress-only internet gateway on one of the public subnets. Update the route table for the private subnets that forward non-VPC traffic to the egress-only Internet gateway.

---

### Question 102
A company wants to migrate an on-premises data center to AWS. The data center hosts an SFTP server that stores its data on an NFS-based file system. The server holds 200 GB of data that needs to be transferred. The server must be hosted on an Amazon EC2 instance that uses an Amazon Elastic File System (Amazon EFS) file system.

**Which combination of steps should a solutions architect take to automate this task? (Choose two.)**

A) Launch the EC2 instance into the same Availability Zone as the EFS file system.

B) Install an AWS DataSync agent in the on-premises data center.

C) Create a secondary Amazon Elastic Block Store (Amazon EBS) volume on the EC2 instance for the data.

D) Manually use an operating system copy command to push the data to the EC2 instance.

E) Use AWS DataSync to create a suitable location configuration for the on-premises SFTP server.

---

### Question 103
A company has an AWS Glue extract, transform, and load (ETL) job that runs every day at the same time. The job processes XML data that is in an Amazon S3 bucket. New data is added to the S3 bucket every day. A solutions architect notices that AWS Glue is processing all the data during each run.

**What should the solutions architect do to prevent AWS Glue from reprocessing old data?**

A) Edit the job to use job bookmarks.

B) Edit the job to delete data after the data is processed.

C) Edit the job by setting the NumberOfWorkers field to 1.

D) Use a FindMatches machine learning (ML) transform.

---

### Question 104
A solutions architect must design a highly available infrastructure for a website. The website is powered by Windows web servers that run on Amazon EC2 instances. The solutions architect must implement a solution that can mitigate a large-scale DDoS attack that originates from thousands of IP addresses. Downtime is not acceptable for the website.

**Which actions should the solutions architect take to protect the website from such an attack? (Choose two.)**

A) Use AWS Shield Advanced to stop the DDoS attack.

B) Configure Amazon GuardDuty to automatically block the attackers.

C) Configure the website to use Amazon CloudFront for both static and dynamic content.

D) Use an AWS Lambda function to automatically add attacker IP addresses to VPC network ACLs.

E) Use EC2 Spot Instances in an Auto Scaling group with a target tracking scaling policy that is set to 80% CPU utilization.

---

### Question 105
A company is preparing to deploy a new serverless workload. A solutions architect must use the principle of least privilege to configure permissions that will be used to run an AWS Lambda function. An Amazon EventBridge (Amazon CloudWatch Events) rule will invoke the function.

**Which solution meets these requirements?**

A) Add an execution role to the function with lambda:InvokeFunction as the action and * as the principal.

B) Add an execution role to the function with lambda:InvokeFunction as the action and Service: lambda.amazonaws.com as the principal.

C) Add a resource-based policy to the function with lambda:* as the action and Service: events.amazonaws.com as the principal.

D) Add a resource-based policy to the function with lambda:InvokeFunction as the action and Service: events.amazonaws.com as the principal.

---

### Question 106
A company is preparing to store confidential data in Amazon S3. For compliance reasons, the data must be encrypted at rest. Encryption key usage must be logged for auditing purposes. Keys must be rotated every year.

**Which solution meets these requirements and is the MOST operationally efficient?**

A) Server-side encryption with customer-provided keys (SSE-C)

B) Server-side encryption with Amazon S3 managed keys (SSE-S3)

C) Server-side encryption with AWS KMS keys (SSE-KMS) with manual rotation

D) Server-side encryption with AWS KMS keys (SSE-KMS) with automatic rotation

---

### Question 107
A bicycle sharing company is developing a multi-tier architecture to track the location of its bicycles during peak operating hours. The company wants to use these data points in its existing analytics platform. A solutions architect must determine the most viable multi-tier option to support this architecture. The data points must be accessible from the REST API.

**Which action meets these requirements for storing and retrieving location data?**

A) Use Amazon Athena with Amazon S3.

B) Use Amazon API Gateway with AWS Lambda.

C) Use Amazon QuickSight with Amazon Redshift.

D) Use Amazon API Gateway with Amazon Kinesis Data Analytics.

---

### Question 108
A company has an automobile sales website that stores its listings in a database on Amazon RDS. When an automobile is sold, the listing needs to be removed from the website and the data must be sent to multiple target systems.

**Which design should a solutions architect recommend?**

A) Create an AWS Lambda function triggered when the database on Amazon RDS is updated to send the information to an Amazon Simple Queue Service (Amazon SQS) queue for the targets to consume.

B) Create an AWS Lambda function triggered when the database on Amazon RDS is updated to send the information to an Amazon Simple Queue Service (Amazon SQS) FIFO queue for the targets to consume.

C) Subscribe to an RDS event notification and send an Amazon Simple Queue Service (Amazon SQS) queue fanned out to multiple Amazon Simple Notification Service (Amazon SNS) topics. Use AWS Lambda functions to update the targets.

D) Subscribe to an RDS event notification and send an Amazon Simple Notification Service (Amazon SNS) topic fanned out to multiple Amazon Simple Queue Service (Amazon SQS) queues. Use AWS Lambda functions to update the targets.

---

### Question 109
A company needs to store data in Amazon S3 and must prevent the data from being changed. The company wants new objects that are uploaded to Amazon S3 to remain unchangeable for a nonspecific amount of time until the company decides to modify the objects. Only specific users in the company's AWS account can have the ability to delete the objects.

**What should a solutions architect do to meet these requirements?**

A) Create an S3 Glacier vault. Apply a write-once, read-many (WORM) vault lock policy to the objects.

B) Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Set a retention period of 100 years. Use governance mode as the S3 bucket's default retention mode for new objects.

C) Create an S3 bucket. Use AWS CloudTrail to track any S3 API events that modify the objects. Upon notification, restore the modified objects from any backup versions that the company has.

D) Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Add a legal hold to the objects. Add the s3:PutObjectLegalHold permission to the IAM policies of users who need to delete the objects.

---

### Question 110
A social media company allows users to upload images to its website. The website runs on Amazon EC2 instances. During upload requests, the website resizes the images to a standard size and stores the resized images in Amazon S3. Users are experiencing slow upload requests to the website. The company needs to reduce coupling within the application and improve website performance. A solutions architect must design the most operationally efficient process for image uploads.

**Which combination of actions should the solutions architect take to meet these requirements? (Choose two.)**

A) Configure the application to upload images to S3 Glacier.

B) Configure the web server to upload the original images to Amazon S3.

C) Configure the application to upload images directly from each user's browser to Amazon S3 through the use of a presigned URL.

D) Configure S3 Event Notifications to invoke an AWS Lambda function when an image is uploaded. Use the function to resize the image.

E) Create an Amazon EventBridge (Amazon CloudWatch Events) rule that invokes an AWS Lambda function on a schedule to resize uploaded images.

---

### Question 111
A company recently migrated a message processing system to AWS. The system receives messages into an ActiveMQ queue running on an Amazon EC2 instance. Messages are processed by a consumer application running on Amazon EC2. The consumer application processes the messages and writes results to a MySQL database running on Amazon EC2. The company wants this application to be highly available with low operational complexity.

**Which architecture offers the HIGHEST availability?**

A) Add a second ActiveMQ server to another Availability Zone. Add an additional consumer EC2 instance in another Availability Zone. Replicate the MySQL database to another Availability Zone.

B) Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an additional consumer EC2 instance in another Availability Zone. Replicate the MySQL database to another Availability Zone.

C) Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an additional consumer EC2 instance in another Availability Zone. Use Amazon RDS for MySQL with Multi-AZ enabled.

D) Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an Auto Scaling group for the consumer EC2 instances across two Availability Zones. Use Amazon RDS for MySQL with Multi-AZ enabled.

---

### Question 112
A company hosts a containerized web application on a fleet of on-premises servers that process incoming requests. The number of requests is growing quickly. The on-premises servers cannot handle the increased number of requests. The company wants to move the application to AWS with minimum code changes and minimum development effort.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Use AWS Fargate on Amazon Elastic Container Service (Amazon ECS) to run the containerized web application with Service Auto Scaling. Use an Application Load Balancer to distribute the incoming requests.

B) Use two Amazon EC2 instances to host the containerized web application. Use an Application Load Balancer to distribute the incoming requests.

C) Use AWS Lambda with a new code that uses one of the supported languages. Create multiple Lambda functions to support the load. Use Amazon API Gateway as an entry point to the Lambda functions.

D) Use a high performance computing (HPC) solution such as AWS ParallelCluster to establish an HPC cluster that can process the incoming requests at the appropriate scale.

---

### Question 113
A company uses 50 TB of data for reporting. The company wants to move this data from on premises to AWS. A custom application in the company's data center runs a weekly data transformation job. The company plans to pause the application until the data transfer is complete and needs to begin the transfer process as soon as possible. The data center does not have any available network bandwidth for additional workloads. A solutions architect must transfer the data and must configure the transformation job to continue to run in the AWS Cloud.

**Which solution will meet these requirements with the LEAST operational overhead?**

A) Use AWS DataSync to move the data. Create a custom transformation job by using AWS Glue.

B) Order an AWS Snowcone device to move the data. Deploy the transformation application to the device.

C) Order an AWS Snowball Edge Storage Optimized device. Copy the data to the device. Create a custom transformation job by using AWS Glue.

D) Order an AWS Snowball Edge Storage Optimized device that includes Amazon EC2 compute. Copy the data to the device. Create a new EC2 instance on AWS to run the transformation application.

---

### Question 114
A company has created an image analysis application in which users can upload photos and add photo frames to their images. The users upload images and metadata to indicate which photo frames they want to add to their images. The application uses a single Amazon EC2 instance and Amazon DynamoDB to store the metadata. The application is becoming more popular, and the number of users is increasing. The company expects the number of concurrent users to vary significantly depending on the time of day and day of week. The company must ensure that the application can scale to meet the needs of the growing user base.

**Which solution meets these requirements?**

A) Use AWS Lambda to process the photos. Store the photos and metadata in DynamoDB.

B) Use Amazon Kinesis Data Firehose to process the photos and to store the photos and metadata.

C) Use AWS Lambda to process the photos. Store the photos in Amazon S3. Retain DynamoDB to store the metadata.

D) Increase the number of EC2 instances to three. Use Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volumes to store the photos and metadata.

---

### Question 115
A medical records company is hosting an application on Amazon EC2 instances. The application processes customer data files that are stored on Amazon S3. The EC2 instances are hosted in public subnets. The EC2 instances access Amazon S3 over the internet, but they do not require any other network access. A new requirement mandates that the network traffic for file transfers take a private route and not be sent over the internet.

**Which change to the network architecture should a solutions architect recommend to meet this requirement?**

A) Create a NAT gateway. Configure the route table for the public subnets to send traffic to Amazon S3 through the NAT gateway.

B) Configure the security group for the EC2 instances to restrict outbound traffic so that only traffic to the S3 prefix list is permitted.

C) Move the EC2 instances to private subnets. Create a VPC endpoint for Amazon S3, and link the endpoint to the route table for the private subnets.

D) Remove the internet gateway from the VPC. Set up an AWS Direct Connect connection, and route traffic to Amazon S3 over the Direct Connect connection.

---

## Answer Key

| Question | Answer | Key Concepts |
|----------|--------|-------------|
| 66 | C | S3 storage classes, lifecycle policies, immediate access requirement |
| 67 | D | SQS visibility timeout, message processing duplication |
| 68 | A | Direct Connect with VPN backup, cost optimization |
| 69 | B | Aurora Multi-AZ, Auto Scaling across AZs, RDS Proxy |
| 70 | C | Application Load Balancer health checks, Auto Scaling |
| 71 | B | DynamoDB point-in-time recovery, RPO/RTO requirements |
| 72 | D | S3 VPC gateway endpoint, data transfer cost reduction |
| 73 | C, D | Bastion host security groups, external IP access |
| 74 | A, C | Web tier HTTPS, database tier security groups |
| 75 | A | API Gateway, Lambda, SQS for decoupling |
| 76 | B | DataSync over Direct Connect for secure transfer |
| 77 | C | API Gateway, Kinesis, Lambda for real-time processing |
| 78 | B | AWS Backup for DynamoDB, automated retention |
| 79 | A | DynamoDB on-demand capacity for unpredictable traffic |
| 80 | B | Secure AMI sharing with KMS key policy |
| 81 | C | SQS with Auto Scaling based on queue length |
| 82 | D | EventBridge for certificate expiration monitoring |
| 83 | C | CloudFront with custom origin for global optimization |
| 84 | B | Reserved Instances for production, On-Demand for dev/test |
| 85 | A | S3 Object Lock with versioning for compliance |
| 86 | A | AWS Secrets Manager for credential rotation |
| 87 | A | RDS Proxy for connection pooling during upgrades |
| 88 | A | S3 Requester Pays to shift transfer costs |
| 89 | A | S3 versioning with MFA Delete for protection |
| 90 | B | RDS read replica to offload read traffic |
| 91 | A | S3 gateway endpoint for private connectivity |
| 92 | A, C | VPC endpoint with bucket policy restrictions |
| 93 | B | Aurora database cloning for staging environment |
| 94 | C | S3 events, SQS, Lambda for serverless processing |
| 95 | D | RDS read replicas with same resources as source |
| 96 | D | IAM policy with source IP condition |
| 97 | D | FSx for Windows with Active Directory integration |
| 98 | C | SQS visibility timeout for Lambda processing |
| 99 | D | FSx for Lustre for high-performance file system |
| 100 | C | KMS with S3 for encryption and high availability |
| 101 | A | NAT gateways in each AZ for private subnet internet access |
| 102 | B, E | DataSync agent and location configuration |
| 103 | A | AWS Glue job bookmarks for incremental processing |
| 104 | A, C | AWS Shield Advanced and CloudFront for DDoS protection |
| 105 | D | Resource-based policy with least privilege |
| 106 | D | KMS with automatic rotation for compliance |
| 107 | B | API Gateway with Lambda for REST API |
| 108 | D | SNS fan-out to multiple SQS queues |
| 109 | D | S3 Object Lock with legal hold for flexible retention |
| 110 | C, D | S3 presigned URLs and Lambda for image processing |
| 111 | D | Amazon MQ, Auto Scaling, RDS Multi-AZ |
| 112 | A | AWS Fargate with ECS for containerized applications |
| 113 | C | Snowball Edge with AWS Glue for large data migration |
| 114 | C | Lambda with S3 and DynamoDB for scalable architecture |
| 115 | C | VPC endpoint for private S3 access |

---

## Study Tips

1. **Sequential Practice**: Work through these questions in order (66-115) to build knowledge progressively
2. **Focus Areas**: Pay special attention to storage lifecycle management, security groups, and serverless architectures
3. **Cost Optimization**: Many questions test your ability to choose the most cost-effective solution
4. **Service Integration**: Understand how AWS services work together (e.g., SQS + Lambda, S3 + CloudFront)
5. **Security Best Practices**: Know IAM policies, encryption options, and network security configurations

## Contributing

Feel free to contribute additional explanations, corrections, or improvements to this study guide.

## Disclaimer

These practice questions are for educational purposes only and are not affiliated with Amazon Web Services or the official AWS certification program. Windows File Server file system on AWS and set the Active Directory domain for authentication.

---



