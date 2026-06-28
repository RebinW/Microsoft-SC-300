# Create and manage cloud users

## Overview
Creating user accounts is one of the first steps in the identity lifecycle. Before a user can sign in. Before a user can sign in, recieve licenses, become member of a group, or access applications, the user first needs an identity. In lange organizations this process is often automated through user provisioning, but in this lab i'll create the account manually to show how it works in Entra ID.

In my lab environment, I'm running a hybrid identity setup where Active Directory is the source of authority. This means that any user acoount that needs to exist both on-premise and in Entra ID should always be created in Active Directory first and then synchronized to the cloud using Microsoft Entra Connect.

Because synchronization only works one way, user acoounts created directly in Entra ID are not synchronized back to Active Directory. Those users remain cloud-only identities. I've already covered the process of creating hybrid user accounts in my Active Directory project, so I won't repeat it here. Instead, this lab focuses on creating and managing cloud-only user accounts directly in Entra ID.

Instead of creating a rondon account,I'll create a dedicated cloud-only admin account. The account that creates the Microsoft Entra tenant automatically becomes the first Global Administrator, but following the principle of least privilege, that account shouldn't be used for everyday tasks. I'll use this new account throughout the rest of the project as I implement and test different admin roles, but for now i'm just going to create the identity.


## Objectives
- Create cloud-only user account
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


