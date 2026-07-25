# Configure Cloud Kerberos Trust for Windows Hello for Business

## Overview
Windows Hello for Business had already been deployed successfully on the client device, and the user was able to create a PIN. The problem was that the PIN could not be used to sign in to the hybrid Microsoft Entra joined device.

The reason is that the device is still joined to the on-premises Active Directory domain. Active Directory normally issues a Kerberos Ticket Granting Ticket after validating the user's password. With Windows Hello for Business, the user does not enter the Active Directory password. The PIN only unlocks the private key stored on the device, so Active Directory needs another way to trust the authentication.

Cloud Kerberos Trust solves this problem by connecting the Windows Hello authentication in Microsoft Entra ID with the Kerberos authentication used by on-premises Active Directory. After Microsoft Entra ID validates the Windows Hello credential, the device is able to obtain the Kerberos tickets needed to sign in and access on-premises resources.

In this lab, I configure Microsoft Entra Kerberos in the hybrid environment and enable Cloud Kerberos Trust for the pilot device through Microsoft Intune. I then verify that the required Kerberos objects have been created, that the client has received the Cloud Trust policy, and that the user can successfully sign in with the Windows Hello for Business PIN.

## Objectives
- Understand why Cloud Kerberos Trust is required when deploying Windows Hello for Business in a hybrid identity environment
- Configure Microsoft Entra Kerberos to establish trust between Microsoft Entra ID and the on-premises Active Directory domain
- Create and deploy an Intune configuration policy that enables Cloud Kerberos Trust for Windows Hello for Business
- Configure the Microsoft Entra Kerberos Server by using the AzureADHybridAuthenticationManagement PowerShell module
- Verify that the Microsoft Entra Kerberos Server object has been created successfully in Active Directory
- Confirm that the client device has received the Cloud Kerberos Trust policy and is able to obtain Kerberos tickets for on-premises authentication
- Validate that Windows Hello for Business PIN sign-in works successfully after Cloud Kerberos Trust has been configured

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
