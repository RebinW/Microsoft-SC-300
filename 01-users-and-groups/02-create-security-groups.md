# Creating, configuring and managing security groups

## Overview
There are two main group types in Microsoft Entra ID: **Security Groups** and **Microsoft 365 Groups**. These groups are used to organize and manage identities, making it much easier to manage access in larger environments. In this lab, i'm going to focus on **Security Groups**

Security Groups are the most common group type in both Microsoft Entra ID and on-premise Active Directory. Their main purpose is to manage access to resources by assigning permissions to a group instead of to individual users.

In on-premise Active Directory, you have the option to create either a Security Group or a Distribution Group. While the comparison isn't exactly 1-1 match, I think it's useful to compare them like this:
- On-premise Security Group -> Entra ID Security Group
- On-premise Distribution Groups -> Microsoft 365 Groups

I already have a few security groups in my tenant that were synchronized from my on-premise Active Directory using Microsoft Entra Connect. For this lab, i'm going to create the security group directly in Entra ID to show how it is done. Since the group is created in Entra ID, it will be a cloud-only security group. Users and groups created on-premise can be synchronized to Entra ID, but synchronization does not happen the other way around, thats why they stay cloud-only.

Security groups can have to membership types. The group can either use **Assigned** membership, where users are added and removed manually, or **Dynamic** membership, where users are added and removed automatically based on a set of rules.

In this lab, I'll create an **Assigned Security Group** and manually add users to it. In the next lab. I'll take a closer look at Dynamic security groups and how dynamic membership works.

## Objectives
- Create cloud-only user accounts
- Configure required user properties
- Verify successful user creation
- Understand the characteristics of cloud-only users

## Environment
- Identity Provider: Entra ID
- Licenses: Microsoft 365 E5
- Tenant: KlarStroem
- Role used: Global Administrator
- License requirements
  - For this lab so for none  

## Implementation
#### Step 1: 

## Verification

## Results  

## Lessons Learned  


Sign-in logs  
Audit logs  
Provisioning logs  
PIM audit history  
Diagnostic settings  
Workbooks 

