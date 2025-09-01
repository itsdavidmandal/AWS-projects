# AWS Beanstalk

AWS Elastic Beanstalk is a cloud service that makes it easy to deploy, manage, and scale web applications and services without needing to deal with the underlying infrastructure. Developers simply upload their application code, and Beanstalk automatically handles tasks like provisioning servers, load balancing, scaling, and monitoring. 

# Beanstalk vs EC2

**Amazon EC2 (Elastic Compute Cloud)** provides raw virtual servers in the cloud, giving users full control over the operating system, software, networking, and security. It is flexible but requires manual setup, configuration, and scaling.EC2 is best for users who want maximum control over infrastructure. <br><br>
**AWS Elastic Beanstalk** is a Platform-as-a-Service (PaaS) that runs on top of EC2 and automates much of the heavy lifting. With Beanstalk, developers just upload their code, and AWS handles provisioning EC2 instances, load balancing, auto-scaling, and monitoring. Beanstalk is best for developers who prefer focusing on application code and letting AWS manage the environment.

# Applications in Beanstalk : 

An application in AWS Elastic Beanstalk is the top-level container that holds all the resources and configurations related to a project. It serves as an organizational unit that groups together the application versions (different uploaded code packages), environments (where the app runs), and saved configurations.

# Environments , Saved Configurations and Application Versions in Beanstalk

**Environment** is a collection of AWS resources (like EC2 instances, load balancers, and databases) that run a specific version of an application; you can have multiple environments such as “development,” “testing,” and “production” for the same app. <br> **Saved configurations** are reusable templates of environment settings (like instance type, scaling rules, and security groups) that can be applied when creating new environments, ensuring consistency and saving time.<br> **Application versions** represent specific, uploaded iterations of your application code (stored in Amazon S3), allowing you to deploy, roll back, or test different versions of your app easily within an environment.

# Service Role : 

A **service role in AWS Elastic Beanstalk** is an IAM (Identity and Access Management) role that grants Elastic Beanstalk permission to perform actions on your behalf. <br> This role allows Beanstalk to manage AWS resources required for your application, such as creating EC2 instances, configuring load balancers, storing logs in S3, or publishing metrics to CloudWatch. Without a service role, Beanstalk cannot automatically provision or manage these resources. <br>Essentially, it acts as a bridge between your application and AWS services, ensuring that Beanstalk can operate securely and efficiently while following the principle of least privilege.

# EC2 instance profile in Beanstalk : 

An EC2 instance profile in AWS Elastic Beanstalk is an IAM (Identity and Access Management) role attached to the EC2 instances that run your application within a Beanstalk environment. <br> This profile grants the instances permission to access other AWS services and resources, such as reading from S3 buckets, writing logs to CloudWatch, or interacting with RDS databases.

# EC2 instance profile in Beanstalk vs Service Role : 

The service role is assigned to Elastic Beanstalk itself, allowing the platform to create, configure, and manage AWS resources on your behalf, such as launching EC2 instances, setting up load balancers, or storing logs in S3.

<br>

The EC2 instance profile is attached to the EC2 instances running your application, granting the instances (and your application code) permission to access other AWS services, like reading from S3, writing to CloudWatch, or connecting to RDS databases.

*Essentially, the service role empowers Beanstalk as a service, while the instance profile empowers the individual EC2 instances within your environment.*
