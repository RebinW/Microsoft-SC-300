# Create and manage cloud users

## Overview
Creating user accounts is one of the first steps in the identity lifecycle. Before a user can sign in. Before a user can sign in, recieve licenses, become member of a group, or access applications, the user first needs an identity. In lange organizations this process is often automated through user provisioning, but in this lab i'll create the account manually to show how it is done in Entra ID.

In my lab environment, I'm running a hybrid identity setup where Active Directory is the source of authority. This means that any user acoount that needs to exist both on-premise and in Entra ID should always be created in Active Directory first and then synchronized to the cloud using Microsoft Entra Connect.

Because synchronization only works one way, user acoounts created directly in Entra ID are not synchronized back to Active Directory. Those users remain cloud-only identities. I've already covered the process of creating hybrid user accounts in my Active Directory project, so I won't repeat it here. Instead, this lab focuses on creating and managing cloud-only user accounts directly in Entra ID.

Instead of creating a rondom account, I'll create a dedicated cloud-only administrator account. The account that created the Microsoft Entra tenant automatically became the first Global Administrator in the tenant, but following the principle of least privilege, that account shouldn't be used for everyday tasks. I'll use this new account throughout the rest of the project as I implement and test different administrator roles, but for now i'm just going to create the identity.


## Objectives
- Create cloud-only user account "cloud identities"
- Configure basic user properties
- Configure required user properties
- Assign a role to the user account
- Verify successful user creation
- Understand the characteristics of cloud-only users

## Environment
- Identity Provider: Entra ID
- Tenant subscription: Microsoft 365 E5
- Tenant: KlarStroem
- Role used: Global Administrator
- License requirements
  - For this lab so far none  

## Implementation
#### Step 1: Start creating the user
Lets start creating our new user. As I mentioned previously this user is going to serve as my go-to user throughout the entire project. 

To start creating a new user in Entra ID, we simply navigate to:
1. Open Microsoft Entra Admin Center
2. In the navigation menu to the left we clik on **Entra ID** and then **Users**
3. Click on the **New User** Option and then **Create new user**

![Create new user](screenshots/createnewuser.png)

#### Step 2: Provide the basic user information
In the *Basics* window we basically need to fill out:
1. **User principal name:** this is basically the login name. I chose to write rebin.wasi because my fictional company policy says UPN names should follow this structure: firstname.lastname@domain
2. **Mail nickname:** This will automatically be filled out since we checked the *Derive from user principle name* option, meaning it will automatically create the *Mail nickname* from the information in User principle name.
3. **Display name:** This is going to be the name that will be displayed
4. **Password:** We can choose to uncheck the *Auto-generate password option* and instead fill out a password manually. Regardless of how we choose to create the password it has to be sent/given to the user, who will then be forced to create a new one, first time logging in.
5. **Account enabled:** I chose to check this option to ensure the account will be active right after user creation.

![Provide basic information](screenshots/basicinformation.png)

#### Step 3. Fill out the optional properties
In this window all properties are optional, meaning we can actually create the user without providing any additional properties to the user. Still, it is important to mention that real organizations would specify in their user creation policy what exactly has be filled out. Since These user properties often are used by applications, conditional access polies, dynamic group creation and much more, it is then highly recommended that we fill out as much as possible because these features rely on exactly these attributes. Also another important thing to mentioned is that we cannot assign licenses to users if we havent specified **USAGE LOCATION**.

For this user i'm not going to fill out all the properties only the following:
![User Properties](screenshots/userproperties.png)

#### Step 4: Assigning the security administrator role
In the *Assignments* window, we can directly add the user to a *administrative unit*, a group or directly assign a role to the user. 

I'm going to cover Administrative units in a seperate lab and different group types in another aswell. For now I will simply mqanually assign the user the Security Admistrator role.

I'm also going to document roles and role assignment in depth in a seperate lab later in the project.

![Role assignment](screenshots/roleassignment.png)

#### Step 4: Review user properties and create the user
In this last step we're simply given an overview of user and the properties we chose to provide. Since I agree with the following shown in the picture below, i'm then going to press create.

![User overview](screenshots/useroverview.png)

## Verification
#### Test 1: Verify the user has been successfully created
For us to verify that the user account has been created, we can go to the *Users overview* in Microsoft Entra admin center.
- **User type:** says *member*, this means the user we created is an internal employee, the other option is guest users and these are used for external identities.
- **On-premise sync:** this is the important one. As we see it says *no* where as on all other identities it says *yes*. This confirms that the account is a cloud-only user and that it has been created directly in Entra ID and not synchronized from Active Directory.

![User created](screenshots/usercreated.png)

#### Test 2: Test the user account can authenticate
At this point I want to ensure that the account can authenticate to Entra ID and also that the account is enabled and already active.
- I opened a *new InPrivate wiondow* in my browser and typed portal.office.com
- From here I typed in the upn name of the newly created user account
- It recognized my domain, and showed me my custom default login screen
- then typed the password that was automatically created when we were creating the account "I copied the password and saved it"

![Type temp password](screenshots/temppassword.png)

- After I type the temporary password, it then forced me to change password

![Change password](screenshots/changepassword.png)

- After I changed the password, the *Security defaults* kicked in. We configued and enabled this feature when setting up the tenant. This enforces MFA on all accounts, and therefore requires all user accounts to register/set up MFA when logging in for the first time. Later in this project I'm going to replace *security defaults* with *conditional access policies*.

![MFA registration](screenshots/mfaregistration.png)

- I then followed the instructions setting up MFA using the Microsoft Authenticor application. Once done it confirmed that the authentication method had been added.

![MFA registered](screenshots/mfaregistered.png)

- At this final stage we can see that it succesfully logged the newly created user in. This means we can now use the account and that the account is enabled.

![User logged in](screenshots/userloggedin.png)

## Results  
We have succesfully created a cloud identity "cloud-only user account", and have verified that the account at this point works and that it is enabled. Additionally we could confirm that the system required us to change password and set up MFA because of the security defaults that was enabled in a previous lab.

We have not tested that we can assign licenses and that the actual *Security Administrator* role has been applied, but I'd want to cover role assignments and licenses in two seperate labs.

## Lessons Learned  


