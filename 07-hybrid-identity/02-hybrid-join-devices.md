# Hybrid-join a device from on-prem to Entra ID

## Overview
In a previous lab, I joined a Windows Client to my on-premise Active Directory domain. Thiis allowed users to sign in using their domain account instead of a local account and made the device a trusted part of the on-premise environment.

The users in my environment are already synchronized to Entra ID using Password Hash Synchronization, and Seamless Single Sign-On has also been enabled. This means users are able to access Entra ID protected resources without entering their password again, as Windows uses Kerberos to help establish the first cloud authentication.

Although this provides a SSO experience, the device itself is still only trusted by Active Directory. It has no identity in Entra ID and therefore connot take advantage of features such as Primary Refresh Tokens, device-based Conditional Access, Windows Hello for Business, Intune enrollment, or compliance policies.

In this lab, I will join the existing domain-joined Windows client to Entra ID, creating a hybrid Microsoft Entra joined device. After the device is joined, Windows is able to obtain a Primary Refresh Token, this allows users to authenticate *silently* to Microsoft Entra protected applications across both browsers and supported desktop applications. This creates a more seamless SSO experience while also enabling additional security and device management capabilities that we can implement in future labs.

## Objectives
- Explain the difference between a domain joined device and a Hybrid Microsoft Entra joined device
- Compare the authentication flow before and after Hybrid Microsoft Entra join
- Configure Hybrid Microsoft Entra join using Microsoft Entra Connect Sync
- Synchronize and register the Windows client with Entra ID
- Verify that the device successfully becomes hybrid-joined
- Verify that Windows obtains a Primary Refresh Token
- Demonstrate how the PRT enables seamless SSO to Microsoft Entra protected applications
- Validate that Conditional Access policies are still enforced when a PRT is used

## Environment
- Identity Provider: AD DS + Entra ID
- Licenses: Microsoft 365 E5
- Tenant: KlarStroem
- Role used: Local Administrator account and Global Administrator in Entra ID
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
