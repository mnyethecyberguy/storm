---
draft: true
date: 
  created: 2025-08-08
  updated: 2025-08-08
authors:
  - mnye
categories:
  - AWS
  - Cloud Security
  - Security Architecture
tags:
  - AWS
  - Cloud Security
  - Security Architecture
---

# AWS Security Reference Architecture

The AWS Security Reference Architecture (AWS SRA) is a holistic set of guidelines for deploying the full complement of AWS security services in a multi-account environment. Use it to help design, implement, and manage AWS security services so that they align with AWS recommended practices. The recommendations are built around a single-page architecture that includes AWS security services—how they help achieve security objectives, where they can be best deployed and managed in your AWS accounts, and how they interact with other security services.

<!-- more -->

## SRA Building Blocks

AWS security services, their controls, and interactions are best employed on a foundation of AWS multi-account strategy and identity and access management guardrails. These guardrails set the ability for your implementation of least privilege, separation of duties, and privacy, and provide the support for decisions about what types of controls are needed, where each security service is managed, and how they may share data and permissions in the AWS SRA. 

## AWS SRA Examples

To help you get started building and implementing the guidance in the AWS SRA, AWS maintains an Infrastructure as Code (IaC) repository on GitHub[^2]. The repository contains code to help developers and engineers deploy AWS security-related services in either an AWS Organizations multi-account environment with or without AWS Control Tower as it's landing zone following patterns that align with the AWS Security Reference Architecture.

The templates are general in nature and their goal is to illustrate an implementation pattern rather than provide a complete solution. The AWS service configurations and resource deployments are deliberately very restrictive. You will need to modify and tailor these solutions to suit your environment and security needs.

The AWS SRA code repository provides code samples with both AWS CloudFormation and Terraform deployment options. The solution patterns support two environments: one requires AWS Control Tower and the other uses AWS Organizations without AWS Control Tower. 

A summary of the solutions in the AWS SRA repo include:

- CloudTrail
- GuardDuty
- Security Hub
- Inspector
- Firewall Manager
- Macie
- AWS Config
    - Config Aggregator
    - Conformance Pack
    - AWS Config Control Tower Management Account
- IAM
    - Access Analyzer
    - IAM Password Policy
- EC2 Default EBS Encryption
- S3 Block Account Public Access
- Detective
- Shield Advanced
- AMI Bakery
- Patch Manager

## Additional References

[^1]:
    AWS Security Reference Architecture. <https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/welcome.html>
[^2]:
    AWS Security Reference Architecture Examples. <https://github.com/aws-samples/aws-security-reference-architecture-examples>