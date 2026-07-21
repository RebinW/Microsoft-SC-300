# Automatically enroll Entra joined device into Intune

## Overview
In a previous lab, I hybrid Microsoft Entra joined the client device "CLIENT01", allowing Microsoft Entra ID to establish trust with the device and issue a Primary Refresh Token to users after they sign in. While this enables seamless SSO to Entra protected applications, the device itself is not managed.

To manage Windows devices centrally, they must first be enrolled into Microsoft Intune. Intune makes it possible to configure and enforce security settings across managed devices from a central location. This includes deploying Windows Hello for Business, creating device compliance policies, configuring BitLocker, and later using CA policies that require a device to be compliant before access is granted to company resources.

In this lab, I'll configure automatic device enrollment for Hybrid Microsoft Entra joined devices. This requires configuring MDM enrollment in Intune and enabling automatic enrollment through Group Policy in the On-premise Active Directory environment. Once the configuration is complete, the client device will automatically enroll into Intune after the user signs in, allowing the device to be managed from the Intune admin center.

## Objectives
- Explain why Hybrid Entra joined devices must be enrolled into Intune before they can be centrally managed
- Configure automatic MDM enrollment in Intune for users within the enrollment scope
- Create and link a Group Policy that enables automatic MDM enrollment for Hybrid Entra joined devices
- Verify that the client device automatically enrolls into Intune after the user signs in
- Verify that the device is successfully manageged by Microsoft Intune and appears in the Intune admin center
  
## Environment
- Identity Provider: Entra ID
- Licenses: Microsoft 365 E5
- Tenant: KlarStroem
- Role used: Global Administrator
- License requirements
  - Users in scope for automatic Intune enrollment must have a P2 license

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
