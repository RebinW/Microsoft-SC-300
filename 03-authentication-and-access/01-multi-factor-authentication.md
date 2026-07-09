# The basics behind MFA in Entra ID

## Overview
In the past we used to rely on simply 1 factor when authentication ourselves to a system/application. It started out with passwords, later passwords could esily be cracked using attacks such as password sprays, brute force attacks and many more. We then through policies required users to create more complex password with a minimum amount of characters, upper and lower characters, numbers included and special characters, still attackers got more sophisticated tools to work with.

The solution to this problem is Multi Factor Authentication (MFA). Instead of relying on 1 factor, users now must provide a minimum of 2 factors (2FA) or more when authenticating to a system. These factors are typically devided into 3 categories:
1. Something you know:
- Password
- PIN
- Secret
2. Something you have:
- Mobile device
- Smart card
- certificate
- USB Stick
3. Something that you are:
- Typically biometric data such as:
  - Fingerprint
  - Facial regonition
  - Voice regonition

Now, when authentication ourselves, we simply provide 2 or more factors from above in the authentication process. Once again this means that we do not rely on a single factor, so if an attacker forexample cracks our password he wouldn't be able to gain access because the system still requires the other factor.


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


Sign-in logs  
Audit logs  
Provisioning logs  
PIM audit history  
Diagnostic settings  
Workbooks 

