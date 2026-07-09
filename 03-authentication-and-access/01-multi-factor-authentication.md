# Configure MFA Registration

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

In this lab, i'm going to cover the basics of MFA in Entra ID and how to implement it. Please notice that I stille have security defauls enabled for my tenant, this means that our tenant automatically has MFA enabled for all users and therefore requires users to register for MFA using the Microsoft Authenticator App when they are logging in for the first time. I'll cover some of the most important and widely used authentication methods in the next lab and how to enable them, but for this lab I'm specifically going to take a closer look how to set up MFA for our tenant with specific requirements.


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
#### Step 1: Disable security defaults
As mentioned in the overview my tenant has the security defaults enabled this means that by default when a new user tries to log in for the first time, that user will be required to set up MFA. Since this lab focuses on setting up the **Registration campaign**, and applying the policy to the users, I would then have to disable security defaults for me to show how this work and prove the difference.

Lets first go ahaed and disable the security defaults and then quickly verify that a newly created user and log in without registering for MFA. To disable security defaults: 
1. In Entra ID Admin Center -> Navigation Menu to the left -> Entra ID
2. Click on the *Overview* option
3. Then click on *Properties*
4. At the bottom of the page click on *Manage Security Defaults*
5. Set security defaults to *Disable* and provide justification
6. Press *Save*

![Disable Security defaults](screenshots/securitydefaultsdisabled.png)

#### Step 2: Create new cloud user and test log in
I'm quickly just going to create a new user to be sure this user hasn't already registered for MFA previously, then I'm going to try to log in with tha user and see if MFA registration will be required.

User created  
![Test user created](screenshots/testuser1.png)

After I had created the test user, I then opned a in private browser and tried to log in with the newly created user to ensure that MFA registration wasn't required. I tried to do exactly that, and the only requirement it had was to create a new password since it was my first time logging in, and right after that I was successfully logged in.

![Require password update](screenshots/passwordupdate.png)

#### Step 3: Configure the registration campaigh and enabled to for all users
Now, I'm finally ready to actually implement the registration campaign, and to do this we have to native to:
1. Entra ID Admin Center
2. Authentication methods
3. Registration campaign

![Registration campaign](screenshots/registrationcampaign.png)

Now that we are in the registration campaign wiondow, we're finally ready to configure it and apply it to our tenant. The *State* option highlighted in the screenshot below has three possible states:
1. Microsoft Managed: This means that Microsoft manages the registration campaign. In other word Microsoft decides the authentication method and the snooze behaviour.
2. Enabled: This means that our organization manages the registration campaign. Now we can decide the authentication method ourselves, how many days the user can snooze/ postpone the registration campaign, whether the number of snoozes is limited, and still choose whether to include all users or a specific set of users.
3. Disabled: This basically means there is no registration campaign enforced.

For this lab I chose the *Microsoft managed* state, and therefore the user should be enforced to setup MFA using the Microsoft authenticator application. Also notice that I'm still able to specify the users that will be affected, I chose to include all users in the tenant. 

![Configure registration](screenshots/configureregistration.png)

## Verification

## Results  

## Lessons Learned  


Sign-in logs  
Audit logs  
Provisioning logs  
PIM audit history  
Diagnostic settings  
Workbooks 

