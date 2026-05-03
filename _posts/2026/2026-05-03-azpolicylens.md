---
title: AzPolicyLens - Automated Azure Policy Insights and Reporting
date: 2026-05-03 10:00
author: Tao Yang
permalink: /2026/05/03/azpolicylens
summary:
categories:
  - Azure
tags:
  - Azure
  - Azure Policy
  - DevOps
gallery:
  - image_path: /assets/images/2026/05/azpolicylens-gallery-01.jpg
    url: /assets/images/2026/05/azpolicylens-gallery-01.jpg
    alt: Main page of the generated detailed wiki
    title: Detailed Wiki Main Page
  - image_path: /assets/images/2026/05/azpolicylens-gallery-02.jpg
    url: /assets/images/2026/05/azpolicylens-gallery-02.jpg
    alt: Management Group Summary on the detailed wiki main page
    title: Management Group Summary
  - image_path: /assets/images/2026/05/azpolicylens-gallery-03.jpg
    url: /assets/images/2026/05/azpolicylens-gallery-03.jpg
    alt: Policy Definition Syntax Validation Report from the Policy Definition page in the detailed wiki
    title: Policy Definition Syntax Validation Report
  - image_path: /assets/images/2026/05/azpolicylens-gallery-04.jpg
    url: /assets/images/2026/05/azpolicylens-gallery-04.jpg
    alt: Assignment Compliance Summary from the Policy Assignment page
    title: Assignment Compliance Summary
  - image_path: /assets/images/2026/05/azpolicylens-gallery-05.jpg
    url: /assets/images/2026/05/azpolicylens-gallery-05.jpg
    alt: Overall compliance summary of a built-in security framework (ISO 27001 in this case) on the Security Control Catalog page
    title: Overall Compliance Summary of a Security Framework
  - image_path: /assets/images/2026/05/azpolicylens-gallery-06.jpg
    url: /assets/images/2026/05/azpolicylens-gallery-06.jpg
    alt: Overall compliance summary of a custom security control framework (organization's internal framework in this case) on the Security Control Catalog page
    title: Overall Compliance Summary of a Custom Security Control Framework
  - image_path: /assets/images/2026/05/azpolicylens-gallery-07.jpg
    url: /assets/images/2026/05/azpolicylens-gallery-07.jpg
    alt: Recommendations from the Analysis page in the detailed wiki
    title: Recommendations from the Analysis page
  - image_path: /assets/images/2026/05/azpolicylens-gallery-08.jpg
    url: /assets/images/2026/05/azpolicylens-gallery-08.jpg
    alt: Raw JSON definition for the policy initiative
    title: Raw JSON Definition for the Policy Initiative
  - image_path: /assets/images/2026/05/azpolicylens-gallery-09.jpg
    url: /assets/images/2026/05/azpolicylens-gallery-09.jpg
    alt: Policy category summary in the detailed wiki
    title: Policy Category Summary

---

![banner](/assets/images/2026/05/azpolicylens-banner.jpg)

## Introduction

AzPolicyLens is a solution that automatically generates insights and reports based on Azure Policy data. It provides a comprehensive view of the policy compliance status across your Azure environment, helping you identify areas of non-compliance and take corrective actions.

This solution has been in active development for the last 12 months, and I am excited to share that I have finally released it to the public. You can find the project at [aka.ms/AzPolicyLens](https://aka.ms/AzPolicyLens).

In this blog post, I will provide an overview of AzPolicyLens, its features, and how it can benefit your organization.

## Problem Statement

While working in many customer environments over the last few years, I have observed the following challenges related to Azure Policy:

- Lack of visibility
- Lack of policy compliance reporting and monitoring
- Inconsistent, overlapping, incorrect policy definitions
- Lack of documentation for application teams, i.e.:
  - How should we configure our Azure resources
  - What is the service offering from the Azure landing zone?
- Lack of security control mapping
- Lack of compliance reporting dimensions

With these challenges in mind, I set out to create a solution that would address these issues and provide a comprehensive view of Azure Policy compliance across an organization.

## Features of AzPolicyLens

AzPolicyLens is an automated solution that generates insights and reports based on Azure Policy data.

It supports the two most commonly used DevOps tools, Azure DevOps and GitHub. It provides an Azure DevOps pipeline and a GitHub Actions workflow to generate Markdown wiki content for both Azure DevOps code wiki and GitHub wiki.

The target audience for the generated wiki includes:

- Azure platform engineers and administrators
- Azure cloud architects
- Security Architects and Security Operations teams
- Application developers and architects
- Compliance and audit teams

## Offering

The solution offers:

- Detailed wiki for cloud engineering and security teams
- Security control catalog for native built-in and custom controls
- Ability to integrate internal security controls into the wiki (treated the same as built-in security controls)
- Tailored wiki for each application team focusing on their own data
- Integration with existing CI/CD platforms (supports Azure DevOps and GitHub Actions)

The detailed features can be found in the [Feature Comparison](https://github.com/Azure/AzPolicyLens/blob/main/docs/README.md#feature-comparison) section of the solution documentation.

## Image Gallery

:memo: Here are some screenshots (Click to enlarge) of the generated wiki content from AzPolicyLens (for comprehensive sample wiki sites, please refer to the [demo wiki sites](https://github.com/Azure/AzPolicyLens#demo)).

{% include gallery caption="Click any image to view it in full size." %}

## Wiki Pipelines

The pipelines are designed to run either manually or on a schedule, with security in mind. No privileged roles are required to gather the data (only the `Reader` role is required in Azure). The pipelines perform a single discovery and use the same discovery data to generate one or more copies of the wiki for different personas and teams.

The discovery data does not contain any sensitive information and can be configured to be encrypted at rest with customer-managed keys.

![banner](/assets/images/2026/05/azpolicylens-pipeline-flow.jpg)

## Benefits

By using AzPolicyLens, organizations can gain the following benefits:

- Visibility into policy compliance and security posture
- Inclusion in the landing zone service offering for application teams (customers)
- Integration of in-house security controls with policy reporting
- A library of external and internal security frameworks and controls for reference and use in policy development
- Compliance reporting across multiple dimensions:
  - In the overall specified scope
  - By individual subscriptions
  - By policy assignments
  - **By security frameworks**
  - **By custom security controls**
  - **By specific security controls**
  - **By policy categories**
- Insights into areas for improvement and actionable recommendations
- Assistance with ongoing policy development and maintenance
- For Azure cloud consultants and partner solution providers, this solution can be used as a tool for an initial assessment of a customer's existing Azure environment, as well as ongoing monitoring and reporting.

## Conclusion

Whether you are responsible for your organization's Azure environment or you are an Azure consultant working with a customer's Azure environment, I strongly recommend giving this solution a try, as I believe it solves many common challenges related to Azure Policy management and compliance reporting.

## Credits

Over the last 12 months, from an initial prototype based on a customer's request to a fully released solution, I have received a lot of feedback and suggestions from many people. I want to take this opportunity to thank everyone who has contributed to the development of this solution, including:

- Thanks to [Pete Zerger](https://www.linkedin.com/in/petezerger/) and [NingNing Zhao](https://www.linkedin.com/in/ningning/) - my favourite CISSPs - for their valuable feedback and suggestions from the perspective of security practitioners at different levels, which was crucial in designing a solution that meets the needs of different personas in the security and compliance space.
- Thanks to [Alex Verkinderen](https://www.linkedin.com/in/alexandreverkinderen/) and [Ahmad Abdalla](https://www.linkedin.com/in/ahmadabdalla/) for their feedback and suggestions from an Azure platform engineering perspective, which was crucial in designing a solution that meets the needs of Azure platform engineers and architects.
- Thanks to [Johan Dahlbom](https://www.linkedin.com/in/johandahlbom/), [Alessandro Cardoso](https://www.linkedin.com/in/alessandrocardoso/), [Andreas Washita](https://www.linkedin.com/in/andreaswasita/), [Sebastian Gräf](https://www.linkedin.com/in/sgraef/), and many other colleagues within Microsoft for the guidance and encouragement that helped me navigate the internal process of releasing this as an open-source solution under the Microsoft banner.
- Thanks to the project team from the customer (whom I cannot name here) for the initial request and for the time and support to develop the first prototype in the customer's environment, which became the foundation of this solution.
- Lastly, thanks to Ahmad and Sebastian for accompanying me on this project and becoming co-owners (a Microsoft requirement for this type of project).
