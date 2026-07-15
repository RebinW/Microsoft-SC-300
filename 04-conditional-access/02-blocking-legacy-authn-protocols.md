# Blocking legacy authentication protocols

## Overview
Legacy protocols refers to older authentication protocols that rely on a username and password to authenticate a user. Some examples of legacy protocols include IMAP, POP3, SMTP and older Exchange ActiveSync clients. These protocols were designed before modern authentication methods supported by Entra ID and therefore do not support security features such as MFA, CA policies, authentication strenghts, or sign-in risks.

A common misunderstanding is that applications such as Outlook are either *modern* or *legacy*. In reality, the important factor is the authentication protocol being used. For example, a modern version of Outlook authenticates using modern authentication protocols, allowing Entra ID to evaluate CA policies before giving access. An older email client, or even an attacker using a script, might instead connect to the same Exchange online mailbox using IMAP or POP3. If those legacy protocols are still allowed, the connection relies only on a username and a password, bypassing the additional security controls by modern authentication.

Because of this, legacy authentication is a common target for password spraying and credential theft attacks. Even if an organization requires MFA for sign-ins, an attacker may try to authenticate through legacy protocols if they are still enabled.

**Note:** Not every service still supports legacy authentication. Over time, these services such as Micrsoft has removed these support for these protocols, meaning some applications only accept modern authentication. Even if a particular service no longer supports legacy authentication, blocking it with CA is still the best approch. This ensures that any remaining services or applications that still allow legacy authentication connot be used to bypass the security controls.

In this lab, a CA policy is created to block legacy authentication for all users while excluding emergency accounts. By preventing legacy authentication, only modern authentication methods are allowed, ensuring that CA polies and other MS Entra security features are enforced.

## Objectives
- 

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

