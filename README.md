# Project Overview

This project consists of three repositories that together offer a full-stack solution involving a web application, infrastructure setup, and serverless functions.

## 1. **WebApp Application**
This repository contains the source code for a cloud-based backend web application built with **Java** and **Spring Boot**, using **PostgreSQL** as the database. The application provides APIs to perform various operations and is designed for the **CSYE 6225: Network Structures and Cloud Computing** course.

- **Technologies**: Java (JDK 17), Spring Boot (v3.3.3), PostgreSQL (v16), Gradle.
- **Repository**: [WebApp](https://github.com/swamysmudiga/webapp)

---

## 2. **Terraform-AWS-Infrastructure as Code**
This repository provides the Terraform configuration to set up an **AWS Virtual Private Cloud (VPC)**. It helps automate infrastructure provisioning, leveraging Terraform to create and manage AWS resources.

- **Technologies**: Terraform, AWS CLI, AWS VPC, Public Subnets, Private Subnets, AWS EC2, Packer, AMI, AWS RDS, AWS S3, Route53, Bash, AWS KMS, SecretManager
- **Repository**: [Terraform-AWS-Infrastructure](https://github.com/swamysmudiga/terraform-aws-infra)

---

## 3. **AWS Serverless Lambda Function**
This repository contains a Lambda function designed to handle SNS-triggered events. The function sends verification emails and updates a database hosted on **Amazon RDS**. It integrates with the other two repositories, the web app and infrastructure, for full automation.

- **Technologies**: AWS Lambda, Amazon SNS, Amazon RDS, Mailgun (SMTP).
- **Repository**: [AWS Lambda Serverless](https://github.com/swamysmudiga/aws-lambda-serverless)

---

Each repository is designed to work independently while being part of a broader infrastructure, creating a cloud-based solution with automation and serverless components.
