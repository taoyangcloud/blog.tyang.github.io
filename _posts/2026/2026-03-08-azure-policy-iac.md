---
title: Deploying Azure Policy with Infrastructure as Code (IaC)
date: 2026-03-08 10:00
author: Tao Yang
permalink: /2026/03/08/deploying-azure-policy-iac
summary:
categories:
  - Azure
tags:
  - Azure
  - Azure Policy
  - DevOps
  - Infrastructure as Code
---

## Background

I have developed several Azure Policy-related solutions for various customers over the last 4-5 years. Some of these patterns have kept evolving over time.

I have decided to open source these solutions and share with the community. At the moment, there are at least 3 solutions that I have in mind.

This is considered the first installment of the series, which is a pattern I have developed for deploying Azure Policy with Infrastructure as Code (IaC) using Azure DevOps or GitHub Actions.

**AzPolicyFactory** is a pattern I started building around 2021 and has gone through many iterations based on the feedback from customers and the changes in Azure Policy itself. I believe it has reached a mature level and provides a safe and efficient way to manage Azure Policy at scale, especially in large organizations with complex environments.

The next 2 patterns I'm planning to open source will work well with this pattern, and I will share more details about them in the future. Stay tuned!

## AzPolicyFactory Introduction

![AzPolicyFactory](./../../../assets/images/2026/03/azpolicyfactory-banner.png)

**AzPolicyFactory** provides a comprehensive set of IaC solutions for testing, deploying and managing Azure Policy resources at scale.

By leveraging these IaC templates and pipelines, organizations can automate the deployment and management of Azure Policy resources, ensuring consistent governance across their Azure environments while reducing manual effort and the risk of misconfigurations.

**AzPolicyFactory** ships with 4 separate but interconnected Azure DevOps pipelines and GitHub Actions workflows that cover the entire lifecycle of Azure Policy resources, including:

- **Policy Definitions**
- **Policy Initiatives**
- **Policy Assignments**
- **Policy Exemptions**

The solution automates the entire lifecycle of Azure Policy resources — from code commit through testing and validation to production deployment — ensuring quality and correctness at every stage.

![High-Level-Process](./../../../assets/images/2026/03/azpolicyfactory-high-level-process.png)

The Azure Policy IaC solution in this repository includes the following key features:

- Supports both **Azure DevOps pipelines** and **GitHub Actions workflows** for maximum flexibility and compatibility with different CI/CD platforms.
- Comprehensive set of Bicep modules and templates for deploying Azure Policy resources, following best practices for modularity, reusability, and maintainability.
- Comprehensive set of tests and validation at different stages of the CI/CD pipelines to ensure the quality and correctness of the Azure Policy resources being deployed.
- Follows industry best practices for Azure Policy management, safe deployment, code scan, and PR validation to ensure that the Azure Policy resources are deployed in a secure and compliant manner.
- Unit tests for every policy resource being deployed.
- Policy Integration Test (coming soon) to validate the functionality and effectiveness of the deployed Azure Policy resources in enforcing the desired governance and compliance requirements.

## Learn More

You can find the AzPolicyFactory solution in the following GitHub repository: [AzPolicyFactory](https://aka.ms/AzPolicyFactory). I have included very comprehensive documentation in the repository to help you get started.

## What's Next?

~~Since I only joined Microsoft a little over a month ago, I am still finding my way around. My plan is to try to move this repository to the Azure GitHub organization. If I manage to do that, I will update this post with the new link. In the meantime, you can check out the repository in my personal GitHub account.~~

**2026-04-05 Update**: I have successfully moved the repository to the Azure GitHub organization. You can now find it at [aka.ms/AzPolicyFactory](https://aka.ms/AzPolicyFactory). Unfortunately, it's not move, but initialize a new repo and copy the code over. So the stars and forks are not moved. If you have already starred or forked the original repo, please update to the new one. I will archive the original repo soon.

Next, I'm planning to release a solution I spent over 8 months developing, which I completed about 18 months ago — a framework for Azure Policy integration testing. I'm in the process of finding a good place to release it within Microsoft. Hopefully it won't be too long before I can share it with the community. Stay tuned!
