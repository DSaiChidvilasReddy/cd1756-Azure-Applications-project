# Article CMS Deployment – Resource Analysis and Justification

## Overview

In this project, I deployed a simple Article Content Management System (CMS) on Microsoft Azure.  
The application allows users to log in, view articles, create new articles, and upload images.  
The backend uses a Python Flask web application, Azure SQL Database for storing article data, and Azure Blob Storage for storing images.

For deploying the application, I analyzed two Azure options:
1. Virtual Machine (VM)
2. Azure App Service

Below is my comparison and final choice.

---

## Option 1: Virtual Machine (VM)

### Cost
Using a Virtual Machine can be more expensive in the long run because the VM runs continuously unless it is manually stopped. Even for small workloads, the VM is billed for compute, storage, and networking.

### Scalability
Scalability with a VM is limited and mostly manual. If traffic increases, we need to resize the VM or create additional VMs and configure load balancing, which requires extra effort and configuration.

### Availability
Availability depends on how the VM is configured. By default, a single VM is a single point of failure. To achieve high availability, additional setup such as availability sets or zones is required.

### Workflow
Managing a VM requires more operational work. We need to handle OS updates, security patches, web server configuration, and application deployment manually. This increases complexity for beginners.

---

## Option 2: Azure App Service

### Cost
Azure App Service provides a Free or low-cost tier, which is suitable for development and small projects like this CMS application. It is more cost-effective because we only pay for the service plan and do not manage the underlying infrastructure.

### Scalability
App Service supports easy scaling. Scaling up or down can be done with a few clicks, and Azure manages the infrastructure automatically. This makes it suitable for applications that may grow in the future.

### Availability
Azure App Service provides built-in availability and reliability. Microsoft manages the servers, OS updates, and infrastructure, which reduces the risk of downtime compared to a single VM.

### Workflow
The workflow is much simpler with App Service. The application can be deployed directly from GitHub, environment variables can be managed in the Azure Portal, and logging and monitoring are built-in. This is very helpful for beginners.

---

## Final Choice and Justification

I chose **Azure App Service** to deploy the CMS application.

App Service is easier to use, requires less manual configuration, and is more beginner-friendly compared to a Virtual Machine. It also provides better scalability and availability without additional setup. Since this project focuses on application functionality rather than infrastructure management, App Service is the better choice.

---

## Impact of the Chosen Resource

By choosing Azure App Service, the application does not require manual server management.  
The application configuration is handled using environment variables, and deployment is simplified using GitHub integration.  
If the application traffic increases in the future, scaling can be done easily without changing the application code.

Overall, Azure App Service fits the requirements of this CMS application and is well suited for learning and development purposes.
