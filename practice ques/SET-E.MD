# AWS Solutions Architect Associate Practice Questions

A comprehensive collection of practice questions for the AWS Certified Solutions Architect Associate exam, covering various AWS services and architectural patterns.

## Table of Contents
- [Overview](#overview)
- [Question Categories](#question-categories)
- [How to Use](#how-to-use)
- [Practice Questions](#practice-questions)
- [Answer Key](#answer-key)
- [Contributing](#contributing)

## Overview

This repository contains 30 carefully curated practice questions (Questions 261-290) that cover essential AWS services and architectural concepts for the Solutions Architect Associate certification. Each question includes multiple choice answers and focuses on real-world scenarios.

## Question Categories

The questions cover the following AWS services and concepts:
- **Content Delivery & Edge Services**: CloudFront, Lambda@Edge, Global Accelerator
- **Networking**: VPC, Load Balancers, Route 53, VPC Peering
- **Compute**: EC2, Auto Scaling, ECS, Fargate, Lambda
- **Storage**: S3, EFS, EBS, FSx
- **Database**: RDS, DynamoDB, ElastiCache, Aurora
- **Analytics**: Kinesis, Athena, QuickSight, EMR
- **Security**: IAM, KMS, Macie
- **Monitoring & Management**: CloudWatch, AWS Backup
- **Migration & Disaster Recovery**: Multi-AZ, Cross-Region strategies

## How to Use

1. Read each question carefully
2. Identify the key requirements and constraints
3. Consider the AWS Well-Architected Framework principles
4. Select the best answer(s) based on cost-effectiveness, security, and operational efficiency
5. Check your answers against the answer key
6. Review explanations for questions you got wrong

---

## Practice Questions

### Question 261
**Scenario**: A company recently announced the deployment of its retail website to a global audience. The website runs on multiple Amazon EC2 instances behind an Elastic Load Balancer. The instances run in an Auto Scaling group across multiple Availability Zones. The company wants to provide its customers with different versions of content based on the devices that the customers use to access the website.

**Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)**

A. Configure Amazon CloudFront to cache multiple versions of the content.
B. Configure a host header in a Network Load Balancer to forward traffic to different instances.
C. Configure a Lambda@Edge function to send specific objects to users based on the User-Agent header.
D. Configure AWS Global Accelerator. Forward requests to a Network Load Balancer (NLB). Configure the NLB to set up host-based routing to different EC2 instances.
E. Configure AWS Global Accelerator. Forward requests to a Network Load Balancer (NLB). Configure the NLB to set up path-based routing to different EC2 instances.

---

### Question 262
**Scenario**: A company plans to use Amazon ElastiCache for its multi-tier web application. A solutions architect creates a Cache VPC for the ElastiCache cluster and an App VPC for the application's Amazon EC2 instances. Both VPCs are in the us-east-1 Region. The solutions architect must implement a solution to provide the application's EC2 instances with access to the ElastiCache cluster.

**Which solution will meet these requirements MOST cost-effectively?**

A. Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule for the ElastiCache cluster's security group to allow inbound connection from the application's security group.
B. Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route traffic through the Transit VPC. Configure an inbound rule for the ElastiCache cluster's security group to allow inbound connection from the application's security group.
C. Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule for the peering connection's security group to allow inbound connection from the application's security group.
D. Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route traffic through the Transit VPC. Configure an inbound rule for the Transit VPC's security group to allow inbound connection from the application's security group.

---

### Question 263
**Scenario**: A company is building an application that consists of several microservices. The company has decided to use container technologies to deploy its software on AWS. The company needs a solution that minimizes the amount of ongoing effort for maintenance and scaling. The company cannot manage additional infrastructure.

**Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)**

A. Deploy an Amazon Elastic Container Service (Amazon ECS) cluster.
B. Deploy the Kubernetes control plane on Amazon EC2 instances that span multiple Availability Zones.
C. Deploy an Amazon Elastic Container Service (Amazon ECS) service with an Amazon EC2 launch type. Specify a desired task number level of greater than or equal to 2.
D. Deploy an Amazon Elastic Container Service (Amazon ECS) service with a Fargate launch type. Specify a desired task number level of greater than or equal to 2.
E. Deploy Kubernetes worker nodes on Amazon EC2 instances that span multiple Availability Zones. Create a deployment that specifies two or more replicas for each microservice.

---

### Question 264
**Scenario**: A company has a web application hosted over 10 Amazon EC2 instances with traffic directed by Amazon Route 53. The company occasionally experiences a timeout error when attempting to browse the application. The networking team finds that some DNS queries return IP addresses of unhealthy instances, resulting in the timeout error.

**What should a solutions architect implement to overcome these timeout errors?**

A. Create a Route 53 simple routing policy record for each EC2 instance. Associate a health check with each record.
B. Create a Route 53 failover routing policy record for each EC2 instance. Associate a health check with each record.
C. Create an Amazon CloudFront distribution with EC2 instances as its origin. Associate a health check with the EC2 instances.
D. Create an Application Load Balancer (ALB) with a health check in front of the EC2 instances. Route to the ALB from Route 53.

---

### Question 265
**Scenario**: A solutions architect needs to design a highly available application consisting of web, application, and database tiers. HTTPS content delivery should be as close to the edge as possible, with the least delivery time.

**Which solution meets these requirements and is MOST secure?**

A. Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in public subnets. Configure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.
B. Configure a public Application Load Balancer with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon CloudFront to deliver HTTPS content using the EC2 instances as the origin.
C. Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.
D. Configure a public Application Load Balancer with multiple redundant Amazon EC2 instances in public subnets. Configure Amazon CloudFront to deliver HTTPS content using the EC2 instances as the origin.

---

