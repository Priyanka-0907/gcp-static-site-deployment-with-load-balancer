# gcp-static-site-deployment-with-load-balancer
Static Website Deployment on Google Cloud Using Load Balancer, Cloud Storage & VPC Networking

# Overview

This project demonstrates deploying a static website on Google Cloud using a Cloud Storage bucket as the backend origin behind a global HTTP Load Balancer. The setup also includes a custom VPC network with firewall rules and follows cloud-engineering best practices for networking, storage, and load-balancing fundamentals.

This project reflects beginner→intermediate Google Cloud skills and cloud fundamentals, resource provisioning, and load-balanced content delivery.

# Architecture Components

The project uses the following Google Cloud services:

VPC Network – Custom network to organize cloud resources

Subnet – Regional private IP range inside the VPC

Firewall Rules – Allow essential traffic (HTTP)

Cloud Storage Bucket – Stores static website content

HTTP Load Balancer – Delivers bucket content using a global frontend

Backend Bucket – Allows the load balancer to use the bucket as a content origin

# High-Level Architecture Diagram (Conceptual)
Internet
   |
HTTP Load Balancer (Global)
   |
Backend Bucket (Static Website Content)
   |
Cloud Storage Bucket

# Steps Performed in the Project

1. Created a Custom VPC Network

Navigated to VPC Network → VPC Networks → Create VPC Network

Created a custom-mode network

Added one subnet in the desired region 

2. Configured Firewall Rules

Created firewall rules under the same VPC network

Allowed HTTP (80)

3. Created a Cloud Storage Bucket

Created a Standard storage bucket

Uploaded static site files (HTML/CSS/images)

4. Enabled Load Balancing

Navigated to Network Services → Load Balancing

Created a Global HTTP Load Balancer

Selected Instance Group as the backend type

Chose the Cloud Storage bucket created earlier as the content origin

Configured the frontend with an ephemeral public IP

Completed the load balancer setup

5. Final Architecture Ready

The load balancer now serves content stored inside the Cloud Storage bucket.


# Project Structure

Infra created through Google Cloud Console:

/infrastructure
   - VPC configuration
   - Subnet configuration
   - Firewall rule creation
   - Cloud Storage bucket creation
   - Load balancer setup 
   - Backend bucket configuration


# Skills Demonstrated

Google Cloud Console resource provisioning

VPC networking fundamentals

Creating and configuring firewall rules

Working with Cloud Storage

Setting up a global HTTP Load Balancer

Backend bucket configuration

Understanding static website deployment architecture

# Key Learning Outcomes

   How to route global traffic through a load balancer
   How Cloud Storage can be used as a static origin
   How networks and firewall rules apply to cloud resources even if compute instances are not used
   Importance of proper resource structuring for cloud deployments
