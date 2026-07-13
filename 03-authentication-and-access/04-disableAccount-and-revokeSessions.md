# Disable user accounts & revoke all active user sessions

## Overview
Knowing how to disable a user account is crucial when an account is suspected to be compromised. Disabling the account isn't always enough because an attacker might still have a valid access token and refresh token. Revoking the user's active sessions invalidates the refresh tokens, preventing the attacker from obtaining new access tokens after the current access token expires. The user must authenticate again before accessing the organizations resources.

In a hybrid environment such as mine, the account should also be disabled in Active Directory because it remains the authoriative identity source for synchronized users. This prevents access to on-premise resources and ensures the disabled state/account is synchronized to Entra ID.

The user's password should also be reset as part of the incident response process. This complements the previous lab, which showed how self-service password reset enables users to regain access to their account.


## Objectives
- Show how to disable an user account in Entra ID
- Reset the users password
- Revoke active tokens
- Show how to disable the users account on-premise
- Verify the user no longer has access
- Verify that the tokens no longer are active

## Environment
- Identity Provider: Entra ID
- Licenses: Microsoft 365 E5
- Tenant: KlarStroem
- Role used: Global Administrator
- License requirements
  - For this lab so for none  

## Implementatio
Before disabling the account in Active Directory, the account is first disabled in ENtra ID and all active sessions are revoked. This immediately blocks access to cloud resources without having to wait for directory synchronization. The account is then disabled in Active Directory, which remains the authoritative identity source in this hybrid environment. This ensures that bouth cloud an on-premise access is blocked.

#### Step 1: Disable the suspected account in Entra ID
For this lab,' I'm going to focus on one of my hybird users. Let's pretend that Mark Nielsen account is suspected to be compromised, and therefore we need to follow the primary steps to ensure to stop an potential attack. 

First, in the screenshot below I have highlighted the user Mark Nielsen, and as you can see the user is an on-premise user that has been synchronized to Entra ID:

![Hybrid user Mark](screenshots/marknielsen.png)

#### Step 1: Disable Mark's user account
Before we disable Marks user account, lets then first verify that the account at this point is enabled. From the User's overview, I simply click on Mark Nielsen to get to Marks user page. From the overview, we can see some of Marks details. If we take a closer look, we can then under *Account status* see that marks account at this point is enabled. For us to disable Marks account, we need to click on the edit option right below the account enabled status:

![Marks account is enabled](screenshots/accountenabled.png)

From here, I'm simply going to uncheck the Account enabled box, and right after click on save:

![Disableing Marks account](screenshots/disableaccount.png)

Right after I click on save, it then automatically took me back to Marks user's overview, can I could immediately see that the status had now changed from enabled to disabled:

![Account disabled](screenshots/accountdisabled.png)

We also have the option to disable an account using PowerShell , we can simply use the following command:
- **Set-AzureADUser -ObjectId mark.nielsen@klarstroem.onmicrosoft.com -AccountEnabled $false**

## Verification

## Results  

## Lessons Learned  

