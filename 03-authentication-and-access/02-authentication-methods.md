# Authentication methods in Entra ID

## Overview
Authentication Methods in ENtra ID define how users prove their identity when signing in. Entra ID supports multiple authentication methods, each provinding a different level of security and usability. Through authentication method policies, adninistrators decide which methods users are allowed to register and use when authenticating.

Not every authentication method provides same level of security. While some methods are mainly designed to improve usability, others are considered phishing resistant and are better for forexample privileged accounts or higher risk scenarios. Authentication methods by themselves don't decide when a user must use a specific method. Instead, they make the method available. Conditional Access policies can later then be used to require a particular method or authentication strength depending on the sign-in scenario.

In this lab, I'll configure authentication method policies in Entra ID and explain some of the most commoonly used methods, how they work, and when they are typically used. I'll also verify how users can register the methods that have been made available to them through the My Sign-in portal.

Understanding authentication methods is important before working with Conditional Access policies and Privileged Identity Management, since both features rely on the method that have been made available for the user.

## Objectives
- Explain the most common authentication methods
- Configure authentication methods policies
- Enable selected methods for users
- Verify that user can register the enebaled methods
- Explain where users manage their authentication methods
- Explain primary and secondary authentication methods

## Environment
- Identity Provider: Entra ID
- Licenses: Microsoft 365 E5
- Tenant: KlarStroem
- Role used: Global Administrator
- License requirements
  - For this lab so for none  

## Theory on Authentication Methods
Before I configure the authentication method policies, I think it's important to first understand some of the authentication methods available in Entra ID. Each method has different characteristics, provides a different level of security, and is used for different scenarios. Understanding these differences makes it much easier to decide which methods should be enabled and later required through Conditional Access policies.

### Microsoft Authenticator authentication method
This is Microsoft's recommended authentication method for Entra ID. It is available as a mobile application and supports multiple ways of verifying the user's identity, this makes it suitable for both MFA and passwordless authentication.

The application supports different authentication experiences, including:
- **Push notifications:** The user recieves a notification on their mobile phone and approves the sign-in.
- **Number matching:** The user must enter or confirm a number shown during the sign-in process. This helps protect against MFA fatigue attacks.
- **Passwordless sign-in:** The user signs in using the authenticator app instead of a password by verifying their identity with biometrics or the device pin.

**Typical use case:**  
Used as the primary authentication method for users signing in to applæications protected by Entra ID.

### Passkeys authentication method
Passkeys are a passwordless authentication method that uses public key cryptography instead of passwords. When a passkey is created, a public and private key pair is generated. The publicket is registered with the identity provider (Entra ID), while the private key is used to prove the user's identity.

A passkey isn't tied to one specific technology or device. It can be stored in Window Hello for Business, on a FIDO2 security key, or on a supported mobile device. Regardless of where it's stored, the authentication process follows the same principle. 

**NOTE:** In Microsoft Entra ID, the authentication method policy is called *Passkey(FIDO2)*. Even though FIDO2 security keys are a common way of using passkeys, they are not the only option. Passkeys can also be stored on supported devices, such as Windows Hello for Business or Microsoft Authenticator, this allows users to authenticate without a physical security key (USB).

**Typical use Case:**  
Used for passwordless and phisning-resistant authentication to applications/resources protected by Entra ID. 

### SMS authentication method
SMS is an authentication method where a one-time passcode is sent to the user's registered mobile phone number. The user must enter the code recieved during the sign-in process to verify their identity.

Although SMS is supported and easy to use, it provides a lower level of security than modern authentication methods and therefore more vulnerable to attacks such as SIM swapping and phishing.

**Typical use case:** Used as a simple MFA method when more modern authentication methods are not available.

### Temporary Access Pass (TAP)
TAP is a time limited passcode that admins can issue to a user. It is typically used during onboarding, account recovery, or when a user needs to register for a new authentication method.

TAP isn't ment for everyday sign-ins. TAP acts as a temporary credential that helps users gain access to their account so they can register stronger authentication methods, such as Microsoft Authenticator or Passkeys.

**Typical use case:** Used to onboard new users or help existing users recover access to their account without requiring a permenant password. A temporary Access Pass is a bootstrap credential, not a long-term solution.

### Software OATH authentication method
Software OATH (Open Authentication) is an authentication method based on time-based one-time passcodes (TOTP). Instead of recieving a code by SMS, the code is generated locally by an authenticator application, such as MS authenticatopr, Google authenticator, or another authenticator application. The generated code changes every 30 seconds and is entered during the sign-in process to verify the user's identity.

During registration, a shared secret is created between ENtra ID and the authenticator application. Both sides use this shared secret together with the current time to generated the same six-digit code independently. When the user enters the code, Entra then compares it with the one it has generated. If the two match, the user's identity is then verified.

**Typical use case:** Used as an MFA method for users who prefer one-tiime passcodes over other methods


## Implementation
#### Step 22: User Registration
Once an authentication metho is enabled and the user is within scope for the policy/method, the user can then register it by going to My Sign-Ins. From here, the user can add, remove, or update their authentication method depending on what the administrator has allowed and what the user is in scope for.




#### Step 1: 

## Verification

## Results  

## Lessons Learned  

