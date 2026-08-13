# Microsoft Entra Entitlement Management: Governed Payroll Access

## Overview
Microsoft Entra Entitlement Management is part of Identity Governance and provides a structured way of managing access to resources. It brings together several concepts, including catalogs, access packages, resources, assignments, and policies. Policies allow us to define how access is granted and governed, including who can request access, whether approval is required, who should approve the request, how long the access should remain valid, and whether it should be reviewed.

A catalog acts as a logical container for resources that we want to govern. These resources can then be included in access packages, which bundle together the access a user needs for a particular purpose. Instead of managing access to each resource separately, we can assign the access package and govern the access through its policies.

An important distinction when working with Entitlement Management is the difference between birthright access and governed access. Not every type of access needs an access package. For example, if an organization has 10 employees in the HR department, all 10 employees might need access to the same standard HR resources. This could include an HR SharePoint site, standard applications, and other resources required for their daily work. This is birthright access, since the employees receive it based on who they are within the organization.

For this type of access, dynamic groups can be a better solution. Membership could, for example, be based on the department attribute. When an employee joins HR, the employee automatically becomes a member of the relevant groups. If the employee later moves to another department, the change in the department attribute automatically changes the corresponding group memberships.

Entitlement Management becomes useful when access requires additional governance. Out of the 10 HR employees, perhaps only 2 work with payroll. Being an HR employee alone should therefore not automatically provide access to payroll resources. These employees might need to request access, receive approval from a manager or resource owner, and have their access reviewed or expire after a defined period.

In this lab, I will use this scenario to create governed payroll access for selected HR employees. I will create an HR catalog, onboard the required resources, create a Payroll Access access package, define its policies, and test the complete process from requesting and approving the access to verifying the resulting assignment and resource access.

## Objectives
- 

## Environment
- Identity Provider: Entra ID
- Licenses: Microsoft 365 E5
- Tenant: KlarStroem
- Role used: Global Administrator
- License requirements
  - Using Identity governance capabilities in Entra ID requires the Entra ID P2 license 

## Implementation
#### Step 1: 

## Verification

## Results  

## Lessons Learned  

