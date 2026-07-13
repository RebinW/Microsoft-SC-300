# Replacing security defaults with a baseline CA policy

## Overview
Security defaults are by default enabled on all new tenants, and provides a solid preconfigured security baseline such as requiring MFA registration for all users in the tenant, blocking legacy authentication, and protecting administrator accounts.

In this lab, I'm going to replace the MFA registration requirement that security defaults provides by implementing my first Conditional Access policy. This will ensure that we have a solid security baseline to start out with and then we can slowly build other policies on top. The most important thing is to ensure that all users accounts have this baseline security and are required to perform MFA when they are accessing resources.

Conditional Access policies can analyze various signals, such as user, device, application, location, and more. Based on these signals it can then automate decisions and enforece policies for accessing specific resources, if configured correctly CA policies really supports the zero-trust mindset.

![Conditional access overview](screenshots/caoverview.png)

In future labs we're going to build more complex CA policies where we focus on specific signals such as specific user accounts/user roles, devices, location and resources. We're then going to specify more strict access controls such as requiring specific authentication strengh. 

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
  - The Conditional Access feature requires at least a Entra ID P1 license for standard rules
  - Creating CA policies with signals from Identity protection (Risky sign-ins, Risky users) Requires a P2 license.

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

