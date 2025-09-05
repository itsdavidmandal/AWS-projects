# Build a Virtual Private Cloud

This project demonstrates the creation and configuration of an **Amazon Virtual Private Cloud (VPC)** to gain hands-on experience with AWS networking fundamentals.

## 🚀 Project Overview

The goal of this project was to set up a customized, secure network environment on AWS using VPCs. It covers key concepts such as IP addressing, CIDR blocks, subnets, availability zones, and internet gateways. The project was simple but insightful, showing how these concepts translate into practical cloud networking.

* **Time taken**: \~30 minutes

## 📘 Key Concepts Covered

### Amazon VPC

Amazon VPC is a service that lets you create an isolated and configurable network environment in the AWS cloud. It allows fine-grained control over routing, IP addressing, and security.

### Default VPC

Every AWS account comes with a default VPC for quickly launching and testing resources without extensive configuration.

### IP Addressing & CIDR

I defined an **IPv4 CIDR block** (e.g., `10.0.0.0/16`) to allocate IP ranges. CIDR provides flexibility in representing address ranges and helps prevent wasted IPs.

### Subnets

Subnets divide a VPC’s CIDR block into smaller networks for better organization and security.

* I enabled **auto-assign public IPv4 addresses** to ensure EC2 instances launched in the subnet automatically receive public IPs.
* Public vs. Private Subnets: Public subnets allow internet communication; private ones don’t.

### Availability Zones

Subnets exist within a single Availability Zone. By distributing resources across multiple AZs, high availability and fault tolerance are achieved.

### Internet Gateway

An Internet Gateway connects a VPC to the internet, enabling instances with public IPs to send and receive traffic. Attaching an IGW was a crucial step in making my subnet public.

## ✅ Takeaways

* Gained practical knowledge of AWS networking basics.
* Learned how to create a VPC, subnets, and connect them to the internet.
* Understood the difference between public and private subnets.
