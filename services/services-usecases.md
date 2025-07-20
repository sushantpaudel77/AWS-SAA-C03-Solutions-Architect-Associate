# AWS Services Guide for SAA-C03 Exam

## Compute Services

### Amazon EC2 (Elastic Compute Cloud)
**Definition:** Virtual servers in the cloud providing scalable computing capacity.

**Key Use Cases:**
- Web applications and websites
- Development and testing environments
- High-performance computing (HPC)
- Batch processing
- Enterprise applications migration

**Exam Focus:** Instance types, pricing models (On-Demand, Reserved, Spot), placement groups, security groups, key pairs

### AWS Lambda
**Definition:** Serverless compute service that runs code in response to events without managing servers.

**Key Use Cases:**
- Event-driven applications
- Real-time file processing
- API backends with API Gateway
- Scheduled tasks and automation
- Microservices architectures

**Exam Focus:** Event sources, concurrency limits, timeout limits, memory allocation, cold starts

### Amazon ECS (Elastic Container Service)
**Definition:** Fully managed container orchestration service for Docker containers.

**Key Use Cases:**
- Microservices applications
- Batch processing jobs
- Machine learning model serving
- Web applications with containers

**Exam Focus:** Task definitions, services, clusters, Fargate vs EC2 launch types

### Amazon EKS (Elastic Kubernetes Service)
**Definition:** Managed Kubernetes service for running Kubernetes applications.

**Key Use Cases:**
- Container orchestration at scale
- Multi-cloud and hybrid deployments
- Applications requiring Kubernetes-specific features

**Exam Focus:** Node groups, managed vs self-managed nodes, integration with other AWS services

### AWS Fargate
**Definition:** Serverless compute engine for containers that works with ECS and EKS.

**Key Use Cases:**
- Running containers without managing infrastructure
- Event-driven container workloads
- Microservices with unpredictable traffic patterns

**Exam Focus:** Task-level resource allocation, networking modes, pricing model

## Storage Services

### Amazon S3 (Simple Storage Service)
**Definition:** Object storage service offering scalability, data availability, security, and performance.

**Key Use Cases:**
- Static website hosting
- Data backup and archiving
- Data lakes and big data analytics
- Content distribution
- Application data storage

**Exam Focus:** Storage classes, lifecycle policies, versioning, cross-region replication, encryption, bucket policies

### Amazon EBS (Elastic Block Store)
**Definition:** High-performance block storage service for EC2 instances.

**Key Use Cases:**
- Database storage
- File system storage
- Boot volumes
- Enterprise applications requiring consistent IOPS

**Exam Focus:** Volume types (gp2, gp3, io1, io2, st1, sc1), encryption, snapshots, Multi-Attach

### Amazon EFS (Elastic File System)
**Definition:** Fully managed NFS file system for EC2 instances.

**Key Use Cases:**
- Shared storage for multiple EC2 instances
- Content repositories and web serving
- Data analytics workloads
- Application development and testing

**Exam Focus:** Performance modes, throughput modes, storage classes, mount targets

### AWS Storage Gateway
**Definition:** Hybrid cloud storage service connecting on-premises environments to AWS storage services.

**Key Use Cases:**
- Hybrid cloud storage integration
- Data backup to cloud
- Archive and disaster recovery
- Moving application data to cloud

**Exam Focus:** File Gateway, Volume Gateway (Stored/Cached volumes), Tape Gateway

### Amazon FSx
**Definition:** Fully managed file systems for compute workloads.

**Key Use Cases:**
- High-performance computing (HPC)
- Windows-based applications (FSx for Windows File Server)
- Lustre file system for compute workloads (FSx for Lustre)

**Exam Focus:** FSx for Windows vs FSx for Lustre, integration with other AWS services

## Database Services

### Amazon RDS (Relational Database Service)
**Definition:** Managed relational database service supporting multiple database engines.

**Key Use Cases:**
- Web and mobile applications
- E-commerce platforms
- Online gaming applications
- Enterprise applications

**Exam Focus:** Multi-AZ deployments, Read Replicas, backup and restore, engine types, parameter groups

### Amazon DynamoDB
**Definition:** Fully managed NoSQL database service with fast performance at any scale.

**Key Use Cases:**
- Mobile and web applications
- Gaming applications
- Real-time personalization
- IoT applications

**Exam Focus:** Global tables, DynamoDB Accelerator (DAX), backup and restore, Global Secondary Indexes

### Amazon Redshift
**Definition:** Fully managed data warehouse service for analytics workloads.

**Key Use Cases:**
- Business intelligence and reporting
- Data warehousing and analytics
- Large-scale data processing

**Exam Focus:** Columnar storage, compression, distribution styles, sort keys, workload management

### Amazon ElastiCache
**Definition:** In-memory caching service supporting Redis and Memcached.

**Key Use Cases:**
- Application performance improvement
- Session management
- Real-time analytics
- Gaming leaderboards

**Exam Focus:** Redis vs Memcached, cluster modes, backup and restore, security

### Amazon DocumentDB
**Definition:** Fully managed document database service compatible with MongoDB.

**Key Use Cases:**
- Content management systems
- User profiles and personalization
- Real-time analytics
- Mobile applications

**Exam Focus:** MongoDB compatibility, clustering, backup strategies

## Networking Services

### Amazon VPC (Virtual Private Cloud)
**Definition:** Logically isolated section of AWS cloud where you can launch resources in a defined virtual network.

**Key Use Cases:**
- Secure application hosting
- Multi-tier web applications
- Disaster recovery
- Hybrid cloud connectivity

**Exam Focus:** Subnets, route tables, internet gateways, NAT gateways, security groups, NACLs, VPC peering

### AWS Direct Connect
**Definition:** Dedicated network connection from on-premises to AWS.

**Key Use Cases:**
- Hybrid cloud architectures
- High bandwidth requirements
- Consistent network performance
- Data transfer cost optimization

**Exam Focus:** Virtual interfaces, BGP routing, redundancy options, bandwidth options

### Amazon Route 53
**Definition:** Scalable DNS web service and domain registration.

**Key Use Cases:**
- Domain name registration and management
- Traffic routing to applications
- Health checking and failover
- Load balancing across regions

**Exam Focus:** Routing policies, health checks, alias records, private hosted zones

### AWS CloudFront
**Definition:** Content delivery network (CDN) service for fast content delivery.

**Key Use Cases:**
- Website acceleration
- Video streaming
- Software distribution
- API acceleration

**Exam Focus:** Origins, behaviors, caching strategies, signed URLs/cookies, WAF integration

### Application Load Balancer (ALB)
**Definition:** Layer 7 load balancer for HTTP and HTTPS traffic.

**Key Use Cases:**
- Microservices and container applications
- Advanced routing requirements
- SSL/TLS termination
- WebSocket and HTTP/2 support

**Exam Focus:** Target groups, listener rules, health checks, sticky sessions

### Network Load Balancer (NLB)
**Definition:** Layer 4 load balancer for TCP and UDP traffic.

**Key Use Cases:**
- High-performance applications
- Static IP requirements
- TCP/UDP load balancing
- Extreme performance requirements

**Exam Focus:** Target types, cross-zone load balancing, static IP addresses

### AWS API Gateway
**Definition:** Fully managed service for creating, publishing, and managing APIs.

**Key Use Cases:**
- RESTful API creation
- WebSocket APIs
- API monetization
- Microservices architecture

**Exam Focus:** Integration types, throttling, caching, authentication methods

### AWS Global Accelerator
**Definition:** Networking service that improves the performance of applications with global users by using AWS's global network infrastructure.

**Key Use Cases:**
- Improving application performance for global users
- Traffic routing to optimal endpoints
- DDoS protection and failover
- Gaming applications requiring low latency
- Voice over IP (VoIP) applications

**Exam Focus:** Anycast IP addresses, traffic dials, endpoint weights, health checks, comparison with CloudFront

## Security Services

### AWS IAM (Identity and Access Management)
**Definition:** Service for managing access to AWS services and resources securely.

**Key Use Cases:**
- User and group management
- Role-based access control
- Cross-account access
- Identity federation

**Exam Focus:** Policies, roles, users, groups, MFA, cross-account access, policy evaluation logic

### AWS KMS (Key Management Service)
**Definition:** Managed service for creating and controlling encryption keys.

**Key Use Cases:**
- Data encryption at rest and in transit
- Compliance requirements
- Centralized key management
- Integration with AWS services

**Exam Focus:** Customer managed keys, AWS managed keys, key rotation, grants

### AWS Certificate Manager (ACM)
**Definition:** Service for provisioning and managing SSL/TLS certificates.

**Key Use Cases:**
- SSL/TLS certificate management
- Load balancer certificate deployment
- CloudFront certificate management

**Exam Focus:** Certificate validation, automatic renewal, integration with AWS services

### AWS WAF (Web Application Firewall)
**Definition:** Web application firewall protecting web applications from common web exploits.

**Key Use Cases:**
- Protection against SQL injection
- Cross-site scripting (XSS) protection
- Rate limiting and DDoS protection
- Geographic restrictions

**Exam Focus:** Web ACLs, rules, conditions, integration with CloudFront and ALB

### AWS Shield
**Definition:** DDoS protection service for applications running on AWS.

**Key Use Cases:**
- DDoS attack protection
- Network and transport layer protection
- Application layer protection (Shield Advanced)

**Exam Focus:** Shield Standard vs Advanced, integration with other services

### AWS Secrets Manager
**Definition:** Service for managing secrets like database passwords and API keys.

**Key Use Cases:**
- Database credential rotation
- API key management
- Application secrets storage
- Cross-service authentication

**Exam Focus:** Automatic rotation, encryption, versioning, integration with RDS

### AWS Security Hub
**Definition:** Cloud security posture management service that centralizes security findings from multiple AWS security services.

**Key Use Cases:**
- Centralized security dashboard
- Security compliance monitoring
- Multi-service security findings aggregation
- Automated security checks

**Exam Focus:** Integration with GuardDuty, Inspector, Macie, Config; findings format, compliance standards

### Amazon GuardDuty
**Definition:** Intelligent threat detection service that uses machine learning to identify malicious activity.

**Key Use Cases:**
- Threat detection and monitoring
- Malicious IP and domain identification
- Compromised instance detection
- Cryptocurrency mining detection

**Exam Focus:** No agents required, CloudTrail/VPC Flow Logs analysis, finding types, integration with Security Hub

### Amazon Inspector
**Definition:** Automated security assessment service for applications and EC2 instances.

**Key Use Cases:**
- Application vulnerability assessment
- EC2 instance security assessment
- Container image vulnerability scanning
- Network reachability analysis

**Exam Focus:** Assessment targets, rules packages, agent-based vs agentless, vulnerability reporting

### Amazon Macie
**Definition:** Data security service that uses machine learning to discover, classify, and protect sensitive data.

**Key Use Cases:**
- PII and sensitive data discovery
- S3 data classification
- Data security monitoring
- Compliance reporting

**Exam Focus:** S3 integration, data classification jobs, sensitive data types, findings and alerts

### AWS Network Firewall
**Definition:** Managed firewall service for VPCs providing network protection at the perimeter.

**Key Use Cases:**
- VPC perimeter protection
- Intrusion detection and prevention
- URL/domain filtering
- Advanced network security

**Exam Focus:** Firewall policies, rule groups, deployment models, integration with VPC

### AWS Directory Service
**Definition:** Managed directory services including Simple AD, Managed Microsoft AD, and AD Connector.

**Key Use Cases:**
- Active Directory integration
- User authentication and authorization
- Application directory services
- SSO integration

**Exam Focus:** Simple AD vs Managed Microsoft AD vs AD Connector, trust relationships, integration with AWS services

## Monitoring and Management Services

### Amazon CloudWatch
**Definition:** Monitoring and observability service for AWS resources and applications.

**Key Use Cases:**
- Infrastructure monitoring
- Application performance monitoring
- Log aggregation and analysis
- Automated actions based on metrics

**Exam Focus:** Metrics, alarms, dashboards, logs, custom metrics, CloudWatch Events/EventBridge

### AWS CloudTrail
**Definition:** Service for logging and monitoring account activity across AWS infrastructure.

**Key Use Cases:**
- Compliance and auditing
- Security analysis
- Troubleshooting operational issues
- Change tracking

**Exam Focus:** Event history, data events vs management events, log file integrity

### AWS Config
**Definition:** Service for assessing, auditing, and evaluating AWS resource configurations.

**Key Use Cases:**
- Configuration compliance monitoring
- Resource change tracking
- Security analysis
- Troubleshooting

**Exam Focus:** Configuration items, rules, remediation actions, conformance packs

### AWS Systems Manager
**Definition:** Service for managing EC2 instances and on-premises servers at scale.

**Key Use Cases:**
- Patch management
- Configuration management
- Remote command execution
- Parameter storage

**Exam Focus:** Session Manager, Parameter Store, Patch Manager, Run Command

### AWS CloudFormation
**Definition:** Infrastructure as Code service for modeling and provisioning AWS resources.

**Key Use Cases:**
- Infrastructure automation
- Consistent environment deployment
- Disaster recovery
- Resource lifecycle management

**Exam Focus:** Templates, stacks, drift detection, nested stacks, stack sets

## Analytics Services

### Amazon Kinesis
**Definition:** Platform for streaming data on AWS.

**Key Use Cases:**
- Real-time data processing
- Log and event data collection
- Real-time analytics
- Machine learning on streaming data

**Exam Focus:** Kinesis Data Streams, Kinesis Data Firehose, Kinesis Analytics, sharding

### AWS Glue
**Definition:** Fully managed extract, transform, and load (ETL) service.

**Key Use Cases:**
- Data preparation for analytics
- Data catalog creation
- ETL job automation
- Schema discovery

**Exam Focus:** Data catalog, crawlers, ETL jobs, triggers

### Amazon Athena
**Definition:** Interactive query service for analyzing data in S3 using SQL.

**Key Use Cases:**
- Ad-hoc data analysis
- Log file analysis
- Business intelligence
- Data lake querying

**Exam Focus:** Query performance optimization, partitioning, columnar formats

## Migration Services

### AWS Database Migration Service (DMS)
**Definition:** Service for migrating databases to AWS quickly and securely.

**Key Use Cases:**
- Database migration to AWS
- Continuous data replication
- Database consolidation
- Development and testing

**Exam Focus:** Homogeneous vs heterogeneous migrations, ongoing replication, source and target endpoints

### AWS Server Migration Service (SMS)
**Definition:** Agentless service for migrating on-premises workloads to AWS.

**Key Use Cases:**
- VM migration to EC2
- Incremental replication
- Large-scale migrations
- Testing migrations

**Exam Focus:** Connector deployment, replication jobs, application migration

### AWS DataSync
**Definition:** Data transfer service for moving large amounts of data between on-premises and AWS.

**Key Use Cases:**
- One-time data migration
- Regular data synchronization
- Data lake ingestion
- Archive and backup

**Exam Focus:** Transfer protocols, bandwidth throttling, data integrity verification

### AWS Application Discovery Service
**Definition:** Service that helps plan migration by collecting configuration and usage data about on-premises servers.

**Key Use Cases:**
- Migration planning and assessment
- Server dependency mapping
- Migration cost estimation
- Application discovery

**Exam Focus:** Agentless vs agent-based discovery, integration with Migration Hub

### AWS Migration Hub
**Definition:** Central location to track the progress of application migrations across multiple AWS tools.

**Key Use Cases:**
- Migration project tracking
- Cross-tool migration visibility
- Migration status monitoring
- Migration strategy planning

**Exam Focus:** Integration with migration tools, tracking capabilities, migration strategies

## Integration Services

### Amazon SQS (Simple Queue Service)
**Definition:** Fully managed message queuing service for decoupling applications.

**Key Use Cases:**
- Application decoupling
- Microservices communication
- Batch job processing
- Order processing systems

**Exam Focus:** Standard vs FIFO queues, visibility timeout, dead letter queues, message attributes

### Amazon SNS (Simple Notification Service)
**Definition:** Fully managed messaging service for application-to-application and application-to-person communication.

**Key Use Cases:**
- Fan-out messaging
- Mobile push notifications
- Email and SMS notifications
- Application alerts

**Exam Focus:** Topics, subscriptions, message filtering, delivery policies

### Amazon EventBridge
**Definition:** Serverless event bus service for connecting applications with data from various sources.

**Key Use Cases:**
- Event-driven architectures
- Application integration
- SaaS integration
- Custom application events

**Exam Focus:** Event buses, rules, targets, event patterns

### AWS Step Functions
**Definition:** Serverless orchestration service for coordinating distributed applications and microservices using visual workflows.

**Key Use Cases:**
- Workflow orchestration
- Microservices coordination
- Data processing pipelines
- Error handling and retry logic

**Exam Focus:** State machines, task states, parallel execution, error handling, integration with Lambda and other AWS services

## Exam-Specific Key Concepts

### High Availability and Fault Tolerance
- Multi-AZ deployments
- Auto Scaling groups
- Load balancers
- Cross-region replication
- Health checks and failover

### Cost Optimization
- Reserved instances and Savings Plans
- Spot instances
- S3 storage classes and lifecycle policies
- CloudWatch for cost monitoring
- Trusted Advisor recommendations

### Performance Optimization
- CloudFront for content delivery
- ElastiCache for caching
- Read Replicas for databases
- Instance types and sizes
- Storage optimization

### Security Best Practices
- Principle of least privilege
- Encryption at rest and in transit
- MFA implementation
- VPC security (Security Groups, NACLs)
- Compliance frameworks

### Disaster Recovery Strategies
- Backup and restore
- Pilot light
- Warm standby
- Multi-site active-active
- RTO and RPO considerations

## Additional Important Services and Concepts

### AWS Backup
**Definition:** Fully managed backup service that centralizes and automates backups across AWS services.

**Key Use Cases:**
- Centralized backup management
- Cross-service backup policies
- Compliance and governance
- Disaster recovery planning

**Exam Focus:** Backup plans, backup vaults, cross-region backup, point-in-time recovery

### Amazon WorkSpaces
**Definition:** Managed desktop computing service in the cloud.

**Key Use Cases:**
- Virtual desktop infrastructure (VDI)
- Remote workforce enablement
- BYOD policies
- Persistent desktops

**Exam Focus:** Deployment models, directory integration, performance bundles

### AWS Transit Gateway
**Definition:** Network transit hub for connecting VPCs and on-premises networks.

**Key Use Cases:**
- Simplifying network connectivity
- Centralized network management
- Multi-region connectivity
- Hub-and-spoke network architecture

**Exam Focus:** Route tables, attachments, peering, multicast support

### AWS PrivateLink
**Definition:** Technology for accessing AWS services privately without internet gateways or NAT devices.

**Key Use Cases:**
- Private connectivity to AWS services
- SaaS connectivity without internet exposure
- Secure service-to-service communication
- Hybrid cloud connectivity

**Exam Focus:** VPC endpoints (Interface vs Gateway), endpoint policies, DNS resolution

### AWS Organizations
**Definition:** Account management service for centrally managing multiple AWS accounts.

**Key Use Cases:**
- Multi-account management
- Consolidated billing
- Service Control Policies (SCPs)
- Account governance

**Exam Focus:** Organizational Units (OUs), SCPs, consolidated billing, account creation

### AWS Control Tower
**Definition:** Service for setting up and governing a secure, compliant multi-account AWS environment.

**Key Use Cases:**
- Landing zone setup
- Guardrails implementation
- Account governance at scale
- Compliance automation

**Exam Focus:** Landing zones, guardrails, Account Factory, integration with Organizations

### Key Terminologies and Concepts

#### S3 Storage Classes
- **S3 Standard:** Frequently accessed data
- **S3 Standard-IA:** Infrequently accessed data
- **S3 One Zone-IA:** Non-critical, infrequently accessed data
- **S3 Glacier Instant Retrieval:** Archive with millisecond access
- **S3 Glacier Flexible Retrieval:** Archive with minute to hour retrieval
- **S3 Glacier Deep Archive:** Long-term archive with 12+ hour retrieval
- **S3 Intelligent-Tiering:** Automatic cost optimization

#### EC2 Instance Types (Common Families)
- **General Purpose:** T3, T4g, M5, M6i (balanced compute, memory, networking)
- **Compute Optimized:** C5, C6i (high-performance processors)
- **Memory Optimized:** R5, R6i, X1e (high memory-to-CPU ratios)
- **Storage Optimized:** I3, I4i, D2 (high sequential read/write to local storage)
- **Accelerated Computing:** P3, P4, G4 (GPU instances for ML/graphics)

#### EBS Volume Types
- **gp2:** General purpose SSD (3 IOPS/GiB baseline, burstable to 3,000 IOPS)
- **gp3:** General purpose SSD (3,000 IOPS baseline, configurable up to 16,000 IOPS)
- **io1/io2:** Provisioned IOPS SSD (up to 64,000 IOPS for io2)
- **st1:** Throughput optimized HDD (for big data, data warehouses)
- **sc1:** Cold HDD (lowest cost for infrequent access)

#### RDS Engine Options
- **Amazon Aurora:** MySQL/PostgreSQL compatible with cloud-native performance
- **MySQL:** Open-source relational database
- **PostgreSQL:** Advanced open-source relational database
- **MariaDB:** MySQL-compatible database
- **Oracle:** Enterprise database with licensing options
- **SQL Server:** Microsoft SQL Server with licensing options

#### VPC Components
- **Subnets:** Logical subdivision of VPC IP address range
- **Route Tables:** Rules determining where network traffic is directed
- **Internet Gateway (IGW):** Gateway for internet access
- **NAT Gateway/Instance:** Outbound internet access for private subnets
- **VPC Peering:** Direct network route between VPCs
- **Security Groups:** Instance-level firewall (stateful)
- **Network ACLs:** Subnet-level firewall (stateless)

#### Auto Scaling Concepts
- **Launch Template/Configuration:** Template for launching instances
- **Auto Scaling Group (ASG):** Collection of instances with scaling policies
- **Scaling Policies:** Rules for when to scale in/out
- **Target Tracking:** Maintain specific metric target
- **Step Scaling:** Scale based on CloudWatch alarm thresholds
- **Scheduled Scaling:** Scale based on time/date

#### Load Balancer Types Comparison
- **Application Load Balancer (ALB):** Layer 7, HTTP/HTTPS, advanced routing
- **Network Load Balancer (NLB):** Layer 4, TCP/UDP, ultra-high performance
- **Gateway Load Balancer (GLB):** Layer 3, transparent network gateway
- **Classic Load Balancer (CLB):** Legacy, both Layer 4 and 7 (deprecated for new apps)

#### Lambda Limits and Concepts
- **Memory:** 128 MB to 10,240 MB (1 MB increments)
- **Timeout:** Maximum 15 minutes
- **Payload:** 6 MB synchronous, 256 KB asynchronous
- **Concurrent Executions:** 1,000 default (can be increased)
- **Cold Start:** Initial startup latency for new containers
- **Provisioned Concurrency:** Pre-warmed execution environments

#### DynamoDB Concepts
- **Partition Key:** Primary key component for data distribution
- **Sort Key:** Optional key component for sorting within partition
- **Global Secondary Index (GSI):** Index with different partition/sort key
- **Local Secondary Index (LSI):** Index with same partition key, different sort key
- **Read/Write Capacity Units:** Throughput measurements
- **Eventually Consistent:** Default read consistency
- **Strongly Consistent:** Optional read consistency with higher latency