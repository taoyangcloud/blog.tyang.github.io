---
title: Policy Integration Testing Framework in AzPolicyFactory
date: 2026-04-05 10:00
author: Tao Yang
permalink: /2026/04/05/policy-int-test-in-azpolicyfactory
summary:
categories:
  - Azure
tags:
  - Azure
  - Azure Policy
  - DevOps
  - Infrastructure as Code

---

One of the most challenging and time-consuming aspects of managing Azure Policy at scale is ensuring the policy does what it's supposed to do without causing unexpected issues in the environment. This is especially important in large organizations with complex environments, where a single misconfiguration can have significant consequences.

In the past, I have seen customers doing this manually and capturing the evidence in a very ad-hoc way. Since the policy resources are constantly evolving in any Azure environments, the test effort should be continuous to ensure (1) new or updated policies are working as expected, and (2) the existing policies are still effective after any policy changes.

The Policy Integration Test is a framework that I have spent over 8 months developing to address this challenge. It provides an automated way to test policy resources in a real environment, and programmatically capture the evidence using standard testing framework `Pester`. The test cases can be automatically triggered when a PR is raised in your Policy IaC repository, or manually executed on demand.

The Policy Integration Test is an important part of the AzPolicyFactory solution, it is in fact the value proposition of the solution. It provides a comprehensive set of tests and validations at different stages of the CI/CD pipelines to ensure the quality and correctness of the Azure Policy resources being deployed.

Today, I have finished the migration of the existing AzPolicyFactory solution to the new repository in the Azure GitHub organization, together with the addition of the Policy Integration Test framework. You can find the new repository at [aka.ms/AzPolicyFactory](https://aka.ms/AzPolicyFactory). I have included very comprehensive documentation in the repository to help you get started with the Policy Integration Test framework.

The Policy Integration Test solution supports both Azure DevOps pipelines and GitHub Actions workflows.

It supports both Azure Bicep and Terraform in the test cases.

Here are some screenshots of the Policy Integration Test framework in action:

**Azure DevOps:**

![1](./../../../assets/images/2026/04/pol-int-test-ado-01.jpg)

![2](./../../../assets/images/2026/04/pol-int-test-ado-02.jpg)

**GitHub Action Workflow:**

![3](./../../../assets/images/2026/04/pol-int-test-gh-01.jpg)

![4](./../../../assets/images/2026/04/pol-int-test-gh-02.jpg)

You can find detailed documentation about Policy Integration Test or AzPolicyFactory solution as a whole in the GitHub repository.

P.S. Since the release of AzPolicyFactory solution last month, I have received a few requests for me to document the feature comparison between AzPolicyFactory and other popular open source solutions.

My focus has been and always will be building the AzPolicyFactory solution. I will **not** document such comparison. If you have any specific questions or are requesting that I produce detailed documentation on a specific topic related to AzPolicyFactory, please raise an issue in the GitHub repository.

You can also use your favourite AI model to summarize the differences for you as long as the solutions you want to compare are well-documented.

Hopefully as you can see, the focus on AzPolicyFactory is **testing** and **validation**. Deploying Azure Policy or any Azure resources is not hard, there are many ways to achieve this.

Looking back and seeing how much time I have spent on all the features in AzPolicyFactory (and the upcoming release of a brand new solution that I have planned), to me the policy resource deployment part of the solution is something I have spent maybe 5% of the entire time on.

Lastly, please feel free to raise issues in the GitHub repository if you have questions or run into issues.

Looking forward to seeing how the `AzPolicyFactory` solution can help you in managing Azure Policy at scale in your organization!
