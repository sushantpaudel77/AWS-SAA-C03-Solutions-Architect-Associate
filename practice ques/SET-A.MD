📘 AWS Solutions Architect Practice Questions
1. Data Aggregation from Global Sites

    A company collects data for temperature, humidity, and atmospheric pressure in cities across multiple continents. The average volume of data that the company collects from each site daily is 500 GB. Each site has a high-speed Internet connection.
    The company wants to aggregate the data from all these global sites as quickly as possible in a single Amazon S3 bucket. The solution must minimize operational complexity.
    Which solution meets these requirements?

    ✅ Turn on S3 Transfer Acceleration on the destination S3 bucket. Use multipart uploads to directly upload site data to the destination S3 bucket.

    Upload the data from each site to an S3 bucket in the closest Region. Use S3 Cross-Region Replication to copy objects to the destination S3 bucket. Then remove the data from the origin S3 bucket.

    Schedule AWS Snowball Edge Storage Optimized device jobs daily to transfer data from each site to the closest Region. Use S3 Cross-Region Replication to copy objects to the destination S3 bucket.

    Upload the data from each site to an Amazon EC2 instance in the closest Region. Store the data in an EBS volume. Take a snapshot and copy to the destination Region.

2. Analyze JSON Logs with Least Overhead

    A company needs to analyze JSON log files stored in an S3 bucket with minimal changes and operational overhead.
    What should the architect do?

    Use Amazon Redshift to load and query the logs.

    Use Amazon CloudWatch Logs and run queries.

    ✅ Use Amazon Athena directly with Amazon S3 to run the queries as needed.

    Use AWS Glue and a Spark cluster on Amazon EMR.

3. Limit S3 Access to AWS Organization Accounts

    A company wants only AWS Organization users to access a central S3 bucket.
    What’s the simplest solution?

    ✅ Add the aws:PrincipalOrgID global condition key to the S3 bucket policy.

    Create OUs and use aws:PrincipalOrgPaths.

    Use AWS CloudTrail to track organization changes and update policies.

    Tag users and use aws:PrincipalTag.

4. Private Access to S3 from EC2 (No Internet)

    EC2 instance in VPC needs to access S3 privately without internet.
    What should be done?

    ✅ Create a gateway VPC endpoint to the S3 bucket.

    Stream logs to CloudWatch and export.

    Create an EC2 instance profile.

    Create an API Gateway with a private link.

5. User Documents Split Across AZs

    User documents are stored on two EC2s with separate EBS volumes across AZs. Load balancer causes inconsistency in document view.
    How to fix this?

    Copy data across both volumes.

    Load balance based on user session.

    ✅ Use Amazon EFS and update the app to save to EFS.

    Load balance to both servers and serve from each.

6. Migrate Large Video Files (70 TB)

    Migrate on-prem NFS large video files to S3 with minimal bandwidth use.
    What’s the best approach?

    Use AWS CLI to upload to S3.

    ✅ Use AWS Snowball Edge for offline data transfer.

    Use S3 File Gateway and transfer data.

    Set up Direct Connect and use S3 File Gateway.

7. Decoupling Message Ingestion at High Volume

    Application needs to ingest and distribute messages at up to 100,000/sec.
    What’s the best decoupled and scalable solution?

    Use Kinesis Data Analytics and consumers.

    Use EC2 Auto Scaling group.

    Use Kinesis Data Stream + Lambda + DynamoDB.

    ✅ Publish messages to SNS with SQS subscriptions for consumers.

8. Modernize Distributed App with Auto Scaling

    App uses a primary server coordinating compute nodes.
    How to make it scalable and resilient?

    ✅ Use SQS queue for jobs, EC2 Auto Scaling based on queue size.

    Same as above but with scheduled scaling.

    Use CloudTrail or EventBridge with EC2 ASG.

    Use EventBridge directly to coordinate jobs.

9. Lifecycle Management of SMB File Server

    Files are hot for 7 days then cold. 70 TB data. Storage nearing full.
    How to manage lifecycle and avoid issues?

    Use DataSync to archive files older than 7 days.

    ✅ Use S3 File Gateway and S3 Lifecycle to Glacier Deep Archive.

    Use FSx for Windows File Server.

    Install S3 access utility on user machines.

10. Order Processing in Sequence

    Orders come via API Gateway. Process must maintain order.
    What’s the right architecture?

    Use SNS + Lambda.

    ✅ Use API Gateway → SQS FIFO Queue → Lambda.

    Use an API Gateway authorizer to block.

    Use SQS standard queue + Lambda.

11. Credential Management for EC2-Aurora

    EC2 app uses Aurora with creds stored locally.
    How to reduce operational overhead?

    ✅ Use AWS Secrets Manager with rotation.

    Use Systems Manager Parameter Store with rotation.

    Store encrypted creds in S3.

    Store creds in encrypted EBS volume.

12. Improve Performance for Static and Dynamic Web App Content

    EC2 + ALB app with S3 static content. Want lower latency.
    What’s the best setup?

    ✅ Use CloudFront with S3 and ALB as origins, Route 53 to CloudFront.

    Use CloudFront + Global Accelerator.

    Use two domains for ALB and S3 via Global Accelerator.

    Use Global Accelerator and CloudFront as endpoints.

13. Rotate RDS Credentials Across Regions

    Rotate MySQL creds monthly in multiple Regions.
    What’s simplest?

    ✅ Use AWS Secrets Manager with multi-Region replication and rotation.

    Use Systems Manager Parameter Store with multi-Region replication.

    Store secrets in S3 and use Lambda via EventBridge.

    Use KMS + DynamoDB Global Table + Lambda.

14. Scaling Read-Heavy Database for Ecommerce App

    EC2 app writes to MySQL on large EC2. Read load increases under scale.
    What’s the scalable solution?

    Use Amazon Redshift.

    Use RDS Single-AZ with read replicas.

    ✅ Use Amazon Aurora with Multi-AZ and Aurora Auto Scaling.

    Use ElastiCache with Spot Instances.

15. Traffic Inspection for VPC

    Previously used on-prem inspection server. Need AWS equivalent.
    What’s the solution?

    Use Amazon GuardDuty.

    Use Traffic Mirroring.

    ✅ Use AWS Network Firewall with rules.

    Use AWS Firewall Manager.

16. Visualize Data Lake in S3 and RDS

    Visualize data from S3 + RDS, with restricted access per user group.
    What’s best?

    ✅ Use Amazon QuickSight with datasets, publish dashboards and share per IAM role.

    Use QuickSight with user/group-level permissions.

    Use AWS Glue + Athena + S3 reports.

    Use Glue + Federated Query + Athena.

17. Give EC2 Access to S3 Bucket

    Two EC2 instances need S3 access.
    How to allow this?

    ✅ Create an IAM role with S3 access and attach to EC2.

    Create IAM policy and attach to EC2.

    Use IAM group.

    Use IAM user.

18. Image Compression with Stateless Lambda Workflow

    Images are uploaded to S3 and processed to smaller sizes by Lambda.
    Which two actions are correct? (Choose 2)

    ✅ Configure S3 to send a notification to an SQS queue.

    ✅ Configure Lambda to use the SQS queue as event source.

    Monitor S3 in Lambda, write filenames to memory file.

    Use EC2 to monitor SQS and invoke Lambda.

    Use EventBridge to email admin on image upload.

19. Packet Inspection via 3rd Party Firewall in AWS

    Web app in public subnet; want to inspect traffic with marketplace firewall.
    What’s best integration?

    Use NLB to route to the appliance.

    Use ALB to route to the appliance.

    Use transit gateway and route tables.

    ✅ Use Gateway Load Balancer + endpoint to forward packets.

20. Clone Production EBS Data Quickly to Test

    Want fast cloning of production EBS data to test env with isolation.
    Which is fastest with consistent performance?

    Use EBS snapshots and restore to EC2 instance store.

    Use EBS Multi-Attach to clone.

    Initialize new EBS volumes and restore.

    ✅ Use EBS snapshots + fast snapshot restore + new volumes.