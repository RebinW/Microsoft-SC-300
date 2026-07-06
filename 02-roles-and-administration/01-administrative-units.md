# Create an Administrative Unit and scope administrative privileges

## Overview
An administrative Unit (AU) is a resource in Entra ID that serves as a container for other resources, which can be users, groups, or devices. The purpose of grouping these resources is to delegate administrative management within a defined scope.

Normally, when an administrator assigns a Microsoft Entra role such as User Administrator, the role applies across the entire tenant. This means the administrator can manage all users in the directory according to the permissions the role holds.

Administrative Units allows us to limit that scope so administrators only recieve administrative privileges over the resources that are members of a specific administrative unit. This means a User Administrator cannot manage resources outside of the assigned administrative unit, this helps the organization to follow the principle of least privilege.

For this lab, I'm going to create an administrative unit that contains all users from the Aarhus office. I will then assign the User Administrator role to a delegated administrator and scope that role to the AU. This means the administrator will only be able to manage users in Aarhus and will not have administrative permissions over users in any other office. 

Explain:
- What i'm implementing
- Why it's important
- Where it's used in enterprise environments

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

Learning material:
- [Administrative units in Microsoft Entra ID](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/administrative-units)
