# EC2 : 

Amazon Web Services Elastic Compute Cloud (AWS EC2) is a cloud service that provides scalable virtual servers, known as instances, for running applications and workloads. Instead of buying physical hardware, users can quickly launch and manage these virtual machines with varying configurations of CPU, memory, storage, and networking to suit different needs.

Here's what the three words mean: <br>
1️⃣ Elastic = flexible. This service can easily adapt and change in size and power to fit your needs.<br>
2️⃣ Compute = computing power. EC2 provides virtual computers that can do various tasks, just like your personal computer.<br>
3️⃣ Cloud = available over the internet.<br>

#  EC2 instances : 

EC2 instances are the virtual servers that run on Amazon’s Elastic Compute Cloud (EC2) platform. Each instance acts like a traditional server but is hosted in the cloud, giving users the flexibility to choose hardware configurations such as CPU, memory, storage, and networking capacity based on their application needs.

# AMI : 

An Amazon Machine Image (AMI) is a preconfigured template provided by AWS that contains the operating system, application server, and applications needed to launch an EC2 instance. It serves as the blueprint for creating instances, ensuring consistency and saving time when deploying multiple servers with the same setup.

# Prod and dev environment : 

## Prod environment : 

It the live system where the application is deployed for real users, handling actual data and business operations. Production environments prioritize stability, security, and performance, with strict change controls to minimize downtime or errors. 

## Dev environment

A development (dev) environment and a production (prod) environment serve different purposes in the software lifecycle. The dev environment is where developers build, test, and experiment with code, often using mock data and tools that allow frequent changes without affecting end users. It is designed to be flexible, enabling debugging, feature testing, and rapid iteration.

# Instance type : 

An instance type in AWS defines the specific hardware configuration of an EC2 instance, including its **CPU, memory, storage, and network capacity**. AWS offers a wide variety of instance types organized into families such as General Purpose, Compute Optimized, Memory Optimized, Storage Optimized, and GPU instances, each designed to handle different workloads.

# Key Pair : 

Key Pair is a set of cryptographic keys used to securely access EC2 instances. It consists of a **public key**, which AWS stores, and a **private key**, which the user downloads and keeps safe. <br>When an EC2 instance is launched with a key pair, the public key is embedded on the instance, allowing the user to securely connect via SSH (for Linux) or RDP (for Windows) using the private key. <br>Key pairs eliminate the need for traditional passwords, providing a secure, encrypted method for authentication and ensuring that only users with the correct private key can access the instance.

# Tags : 

In AWS, tags are metadata labels assigned to resources, such as EC2 instances, S3 buckets, or RDS databases, to help organize, manage, and identify them. <br>Each tag consists of a key and a value pair. Tags make it easier to categorize resources based on purpose, ownership, or environment, enabling efficient searching, reporting, and cost tracking across an organization. They are especially useful in large-scale cloud deployments, where thousands of resources may exist, helping teams maintain clarity, enforce policies, and simplify automation.

# IAM : 

AWS Identity and Access Management (IAM) is a service that helps you securely control access to AWS resources. It allows you to create and manage users, groups, and roles, and assign them permissions that define what actions they can perform on specific resources.

# Policy : 

In AWS, a policy is a document that defines permissions for actions on specific resources, written in JSON format. Policies specify who (user, group, or role) can perform what actions (like read, write, or delete) on which resources under certain conditions.

Policies in AWS define and enforce permissions for users, groups, or roles, controlling what actions they can perform on specific resources. Essentially, they answer the question, “Who can do what on which resources?”

# Effect, Action and Resource in a JSON policy:

**Effect** specifies whether the policy **allows** or **denies** the actions listed, controlling whether access is granted or blocked. <br>**Action** defines the specific operations that are permitted or denied, such as starting or stopping an EC2 instance, reading from an S3 bucket, or describing resources; it determines **what the user can do**. <br>**Resource** identifies the AWS resources to which the actions apply, like a particular EC2 instance, S3 bucket, or all resources (`*`), specifying **where the permissions are effective**. 

# AWS account alias

An AWS account alias is a custom name that you can assign to your AWS account to make it easier to identify and access, instead of using the default account ID, which is a long numeric string.

# IAM group 

An IAM group in AWS is a collection of IAM users that allows you to manage permissions collectively rather than individually. Instead of assigning policies to each user separately, you attach policies to a group, and all users in that group automatically inherit those permissions.

# IAM user 

An IAM user in AWS is an identity created within an AWS account to represent a person, application, or service that needs access to AWS resources.

