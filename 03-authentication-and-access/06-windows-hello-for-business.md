# Enable Windows Hello for Business and use TAP to register WHfB for the user

## Overview

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
#### Step 1: Configure Windows Hello for Business in Intune
The first step in the process is to enable Windows Hello for Business on the devices managed by Intune. There are two ways of enabling WHfB in Intune:
1. Method: Enables tenant-wide enrollment policy. It applies to every enrolled Windows device in the tenant and is mainly for provisioning Windows Hello during enrollment.

![Windows Hello for Business](screenshots/whfb.png)

2. Method: A more controlled deployment, this is the recommended approach because we're able to control the scope instead of applying the policy/enrollment to the whole tenant at once. **We're going to choose this deployment method in this lab**

![Windows Hello for Business](screenshots/whfb1.png)

I choose to go with the second option, and therefore click on *Create* it then took me to the configuration wiindow, and the firste step was to name the policy and give it a short description and click on *next*

![Name the whfb policy](screenshots/namepolicy)

Under the *Create Policy* window, I'm going to configure the WHfB policy that will later be assigned to the pilot group. This is where I define how I want WHfB to be configured on managed devices.

One thing worth pointing out is that Intune lets be configure WHfB either at the device level or at a user level. A device-scoped policy follows the device and applies to anyone who signs in to that device. A user-scope policy, on the other hand, follows the user regardless of which managed device they use.

Since the purpose of this lab is to configure Windows Hello on managed devices, I chose to configure only the device-scope settings. I therefore left all user-scope settings to **Not configured**, allowing the device policy to control the WHfB configuration.

I also left **Credential Guard** as **Not configured**. this is a seperate Windows security feature that protects credentials such as NTLM password hashes and Kerberos tickets from being stolen. Even though it is a recommended feature, it is not required for Windows Hello, so i'm leaving it out from this lab and policy.

I also left **Facial Features Use Enhanced Anti-Spoofing** as **Not configured**. This setting is used together with facial recognition to help *supported* cameras distinguish a real user from spoofing attempts, such as pictures. Since this lab is running on a VM  without biometric hardware, this setting then isn't relevant.

![WHfB device-scoped config](screenshots/whfbconfiguration.png)

I'd also like to explain some of the configured options that seem less obivious than others:

**Require Security Device (TPM):** I chose to require a security device, meaning that WHfB must use a Trusted Platform Module if one is available. The TPM is a hardware chip designed to securely protect cryptographic keys. Instead of storing the private key in the Windows software-based key store, the private key is protected by the Trusted Platform Module (TPM). The TPM performs the cryptographic operations internally, meaning the private key never leaves the hardware.

**Use Certificate for On-prem Auth:** I left this setting disabled because this lab uses the modern Windows Hello for Business deployment model. Enabling this option is intended for environments using the older Certificate Trust model, where user certificates issued by an on-premises Certificate Authority are used for authentication to Active Directory. Since my environment doesn't use certificate-based authentication, this setting isn't required.

Lastly, I chose to block uppercase letters, lowercase letters, and special characters. This limits the Windows Hello credential to a numeric PIN. Since the PIN only unlocks the private key stored on the device and is tied to that specific device, I'm comfortable using a numeric PIN instead of a more complex password.

## Verification

## Results  

## Lessons Learned  
