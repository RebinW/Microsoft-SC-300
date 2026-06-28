# Create and manage cloud users

## Overview
In my lab environment, I'm running a hybrid identity setup where Active Directory is the source of authority. This means that any user acoount that needs to exist both on-premise and in Entra ID should always be created in Active Directory first and then synchronized to the cloud using Microsoft Entra Connect.

Because synchronization only works one way, user acoounts created directly in Entra ID are not synchronized back to Active Directory. Those users remain cloud-only identities.

I've already covered the process of creating hybrid user accounts in my Active Directory project, so I won't repeat it here. Instead, this lab focuses on creating and managing cloud-only user accounts directly in Entra ID.

DIAGRAM HYBRID

To summarize:
- Users created in Active Directory and synchronized to Entra ID become hybrid users.
- Users created directly in Entra ID become cloud-only users and are managed from the cloud.

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


