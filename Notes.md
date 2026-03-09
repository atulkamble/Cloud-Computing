# CHAPTER 1

# Introduction to Cloud Computing Tools

(8 Sessions)

---

# 1.1 Overview of Cloud Computing Tools

## What are Cloud Computing Tools?

Cloud computing tools are **software platforms and services used to build, manage, deploy, monitor, and secure applications in cloud environments.**

They help organizations:

• Deploy infrastructure
• Automate operations
• Monitor systems
• Secure resources
• Scale applications

---

## Cloud Computing Architecture

```
Users
   │
Internet
   │
Cloud Platform
   │
 ┌───────────────┐
 │ Compute       │
 │ Storage       │
 │ Networking    │
 │ Databases     │
 │ Security      │
 └───────────────┘
```

---

## Types of Cloud Tools

| Tool Type            | Purpose                 |
| -------------------- | ----------------------- |
| Infrastructure Tools | Create cloud resources  |
| Container Tools      | Package applications    |
| Monitoring Tools     | Observe system health   |
| Security Tools       | Protect cloud workloads |
| Automation Tools     | Automate infrastructure |
| DevOps Tools         | CI/CD and deployment    |

---

## Common Cloud Tools Ecosystem

```
              Cloud Platforms
       AWS | Azure | Google Cloud
                   │
         Infrastructure Automation
      Terraform | CloudFormation
                   │
         Configuration Management
        Ansible | Chef | Puppet
                   │
           Container Platform
           Docker | Kubernetes
                   │
             Monitoring
        Prometheus | Grafana
                   │
              Security
          IAM | Key Vault
```

---

## Benefits of Cloud Tools

| Benefit           | Description                        |
| ----------------- | ---------------------------------- |
| Automation        | Reduce manual work                 |
| Scalability       | Scale infrastructure automatically |
| High Availability | Fault tolerant systems             |
| Cost Efficiency   | Pay only for usage                 |
| Speed             | Rapid deployment                   |

---

## Real Example

Company deploying **web application**.

Without Cloud Tools

Manual server setup
Manual deployment
Manual monitoring

With Cloud Tools

Terraform → create servers
Docker → package app
Kubernetes → manage containers
Prometheus → monitoring

---

## Lab Idea

Create simple cloud environment

```
Create VM
Install Docker
Deploy NGINX container
Monitor logs
```

---

# PPT Slides (Chapter 1)

Slide 1
Introduction to Cloud Tools

Slide 2
What is Cloud Computing

Slide 3
Cloud Service Models

Slide 4
Types of Cloud Tools

Slide 5
Cloud Ecosystem Diagram

Slide 6
Benefits of Cloud Tools

Slide 7
Real World Architecture

Slide 8
Hands-on Lab

---

# 1.2 Cloud Platforms

---

# AWS (Amazon Web Services)

## Overview

Largest cloud provider globally.

Provides **200+ cloud services**.

---

## Key AWS Services

| Service | Purpose              |
| ------- | -------------------- |
| EC2     | Virtual machines     |
| S3      | Object storage       |
| RDS     | Managed database     |
| Lambda  | Serverless computing |
| VPC     | Networking           |

---

## AWS Architecture

```
Region
  │
Availability Zones
  │
EC2 Instances
  │
Application
```

---

## Advantages

• Highly scalable
• Large ecosystem
• Global infrastructure
• Mature services

---

# Microsoft Azure

Azure is Microsoft's cloud platform.

Highly integrated with:

• Windows
• Active Directory
• Microsoft tools

---

## Key Azure Services

| Service                  | Purpose                 |
| ------------------------ | ----------------------- |
| Azure VM                 | Virtual machines        |
| Azure Blob               | Storage                 |
| Azure SQL                | Database                |
| Azure Kubernetes Service | Container orchestration |
| Azure DevOps             | CI/CD                   |

---

# Google Cloud Platform (GCP)

Google's cloud offering focused on:

• Data analytics
• AI
• Machine learning

---

## Key GCP Services

| Service         | Purpose            |
| --------------- | ------------------ |
| Compute Engine  | Virtual machines   |
| Cloud Storage   | Object storage     |
| BigQuery        | Data analytics     |
| GKE             | Kubernetes service |
| Cloud Functions | Serverless         |

---

# Cloud Comparison

| Feature                | AWS      | Azure       | GCP         |
| ---------------------- | -------- | ----------- | ----------- |
| Market Share           | Highest  | 2nd         | 3rd         |
| Enterprise Integration | Medium   | Very High   | Medium      |
| AI/ML                  | Good     | Good        | Best        |
| Pricing                | Flexible | Competitive | Competitive |

---

# Lab Idea

Create VM on cloud

Example Azure CLI

```
az group create \
--name demo-rg \
--location eastus

az vm create \
--resource-group demo-rg \
--name demo-vm \
--image Ubuntu2204 \
--admin-username azureuser \
--generate-ssh-keys
```

---

# PPT Slides (Cloud Platforms)

Slide 1
Cloud Platforms Overview

Slide 2
AWS Overview

Slide 3
Azure Overview

Slide 4
GCP Overview

Slide 5
Cloud Comparison

Slide 6
Use Cases

---

# CHAPTER 2

# Virtualization and Containerization Tools

(6 Sessions)

---

# 2.1 Virtualization

Virtualization allows **multiple operating systems to run on a single physical machine.**

---

## Hypervisor

Software that creates virtual machines.

Two types:

### Type 1 (Bare Metal)

```
Hardware
   │
Hypervisor
   │
Virtual Machines
```

Examples

• VMware ESXi
• Hyper-V
• KVM

---

### Type 2 Hypervisor

```
Hardware
 │
Host OS
 │
Hypervisor
 │
VM
```

Example

• VirtualBox

---

# Virtualization Tools

| Tool    | Description               |
| ------- | ------------------------- |
| VMware  | Enterprise virtualization |
| Hyper-V | Microsoft virtualization  |
| KVM     | Linux virtualization      |

---

# Benefits

• Resource utilization
• Isolation
• High availability
• Disaster recovery

---

# Containers

Containers package applications with dependencies.

Unlike VMs:

Containers share host OS.

---

## Container Architecture

```
Hardware
   │
Host OS
   │
Container Engine
   │
Containers
```

---

# Docker

Docker is the most popular container platform.

---

## Docker Workflow

```
Application Code
       │
Dockerfile
       │
Docker Build
       │
Docker Image
       │
Docker Container
```

---

# Example Dockerfile

```
FROM python:3.10

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

CMD ["python","app.py"]
```

---

# Kubernetes

Kubernetes manages containers at scale.

---

## Kubernetes Architecture

```
Cluster
 ├── Master Node
 │    ├ API Server
 │    ├ Scheduler
 │    └ Controller
 │
 └── Worker Nodes
      ├ Pods
      ├ Containers
      └ Kubelet
```

---

# Kubernetes Objects

| Object     | Purpose                  |
| ---------- | ------------------------ |
| Pod        | Smallest deployable unit |
| Service    | Networking               |
| Deployment | Manage pods              |
| ConfigMap  | Configuration            |

---

# Example Kubernetes Deployment

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp
spec:
  replicas: 3
  template:
    spec:
      containers:
      - name: web
        image: nginx
```

---

# Serverless Computing

Serverless runs code **without managing servers**.

Examples

• AWS Lambda
• Azure Functions
• Google Cloud Functions

---

## Serverless Architecture

```
User Request
     │
API Gateway
     │
Lambda Function
     │
Database
```

---

# PPT Slides

Slide 1
Virtualization Concepts

Slide 2
Hypervisors

Slide 3
Docker Overview

Slide 4
Container vs VM

Slide 5
Kubernetes Architecture

Slide 6
Serverless Computing

---

# CHAPTER 3

# Cloud Security Tools and Techniques

(8 Sessions)

---

# Cloud Security Concepts

Cloud environments are **multi-tenant**, meaning multiple customers share infrastructure.

Security goals:

• Confidentiality
• Integrity
• Availability

---

# Identity and Access Management (IAM)

IAM controls **who can access cloud resources.**

---

## IAM Components

| Component | Description         |
| --------- | ------------------- |
| User      | Individual account  |
| Group     | Collection of users |
| Policy    | Permission rules    |
| Role      | Temporary access    |

---

Example AWS IAM Policy

```
{
 "Effect": "Allow",
 "Action": "s3:*",
 "Resource": "*"
}
```

---

# Azure Active Directory

Azure AD manages:

• User authentication
• Single Sign-On
• Multi-factor authentication

---

# Encryption

Encryption protects data.

Two types:

| Type            | Description     |
| --------------- | --------------- |
| Data at Rest    | Stored data     |
| Data in Transit | Network traffic |

---

# Security Tools

| Tool                          | Purpose             |
| ----------------------------- | ------------------- |
| AWS GuardDuty                 | Threat detection    |
| Azure Defender                | Security monitoring |
| Cloud Security Command Center | GCP security        |

---

# Data Compliance

Organizations must follow regulations.

Examples:

| Compliance | Description           |
| ---------- | --------------------- |
| GDPR       | European privacy law  |
| HIPAA      | Healthcare security   |
| PCI DSS    | Payment card security |

---

# PPT Slides

Slide 1
Cloud Security Overview

Slide 2
IAM Concepts

Slide 3
Encryption

Slide 4
Security Monitoring

Slide 5
Compliance

---

# CHAPTER 4

# Cloud Networking and Monitoring Tools

(7 Sessions)

---

# Cloud Networking

Cloud networking connects resources securely.

---

## Virtual Private Cloud (VPC)

VPC is an isolated network in cloud.

```
Internet
   │
Gateway
   │
VPC
 ├ Public Subnet
 └ Private Subnet
```

---

# VPN

VPN connects on-premise network to cloud.

---

# Monitoring Tools

Monitoring ensures application health.

---

## AWS CloudWatch

Monitors:

• CPU usage
• Memory
• Logs
• Alerts

---

Example Command

```
aws cloudwatch put-metric-alarm
```

---

# Azure Monitor

Provides

• Metrics
• Logs
• Alerts
• Dashboards

---

# Cost Management

Cloud cost tools track spending.

Examples

| Tool                  | Cloud  |
| --------------------- | ------ |
| AWS Cost Explorer     | AWS    |
| Azure Cost Management | Azure  |
| GCP Billing           | Google |

---

# PPT Slides

Slide 1
Cloud Networking

Slide 2
VPC Architecture

Slide 3
VPN

Slide 4
Monitoring Tools

Slide 5
Cost Management

---

# CHAPTER 5

# Cloud Automation and DevOps Tools

(6 Sessions)

---

# DevOps in Cloud

DevOps integrates:

Development + Operations

Goal:

Fast, reliable software delivery.

---

# DevOps Toolchain

```
Developer
   │
Git
   │
CI Tool (Jenkins)
   │
Build
   │
Docker Image
   │
Kubernetes Deployment
```

---

# Git

Version control system.

Commands

```
git init
git add .
git commit -m "code"
git push
```

---

# Jenkins

Automation server used for CI/CD.

---

## Jenkins Pipeline

```
pipeline {
 agent any
 stages {
   stage('Build') { }
   stage('Test') { }
   stage('Deploy') { }
 }
}
```

---

# Terraform

Infrastructure as Code tool.

---

Example Terraform

```
resource "aws_instance" "web" {
  ami           = "ami-123"
  instance_type = "t2.micro"
}
```

---

# CI/CD Pipeline

```
Code
 │
Build
 │
Test
 │
Docker Image
 │
Deploy
 │
Production
```

---

# PPT Slides

Slide 1
DevOps Introduction

Slide 2
CI/CD Pipeline

Slide 3
Git

Slide 4
Jenkins

Slide 5
Terraform

Slide 6
Automation Benefits

---
