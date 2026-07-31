# OAuth Consent and Enterprise Application Lifecycle

## Overview

In a previous lab, I worked with app registrations and enterprise applications in Microsoft Entra ID. When we register an application, we define which permissions the application is allowed to request. These permissions are not granted simply because they have been added to the app registration. Consent must still be given before the application receives access.

Once an application is used inside a tenant, a service principal is created. This service principal appears under Enterprise applications and represents the application inside the local tenant. From here, administrators can inspect the permissions that have been granted, see whether consent was given by a user or an administrator, review which users are using the application and control how access to the application should work.

While studying Microsoft Defender for Cloud Apps and shadow IT, I came across another part of this process that I had not fully understood before. Users do not necessarily need permission to register applications before they can start using third-party applications with their organizational identities.

The setting that allows users to register applications controls whether users are allowed to create new app registrations inside the organization’s own tenant. This is different from a user signing in to an existing third-party application through Microsoft Entra ID.

For example, a user might visit a cloud application such as Dropbox and select Sign in with Microsoft. The application has already been registered by its publisher. It then redirects the user to Microsoft Entra ID and requests permission to access certain information. If the user is allowed to consent to the requested permissions and accepts the consent prompt, a service principal representing the third-party application is created automatically inside the organization’s tenant.

The user has therefore not registered a new application. The user has consented to an application that already exists. Microsoft Entra then creates the local enterprise application required to represent the trust relationship between the tenant and the third-party application.

This is important because many people confuse application registration with user consent. An organization might prevent ordinary users from registering applications while still allowing them to consent to third-party applications. In a large organization, this could result in many enterprise applications appearing over time as employees sign in to different cloud services with their work accounts.

This is also related to shadow IT, although the two concepts are not exactly the same. Shadow IT includes applications used without the organization’s approval, including applications accessed through personal accounts. In those cases, no enterprise application or consent grant necessarily exists inside Microsoft Entra. Defender for Cloud Apps might still detect the application through network traffic or connected security products.

This lab focuses on the scenario where users access third-party applications through their organizational identities. I will demonstrate what happens when a user gives consent, how the enterprise application is created, where the granted permissions are stored and how administrators can control whether users are allowed to provide consent.

I will also explore the available user consent settings, including blocking user consent, limiting consent to applications from verified publishers and allowing Microsoft to manage user consent settings. Finally, I will review how an administrator can investigate the application through enterprise applications, sign-in logs, audit logs and permission grants.

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
