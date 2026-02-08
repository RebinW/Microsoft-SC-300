# External collaboration settings

In this exercise I follow the official Microsoft SC300 lab: Lab 04: Configure external collaboration settings:  

![Microsoft lab](https://microsoftlearning.github.io/SC-300-Identity-and-Access-Administrator/Instructions/Labs/Lab_04_ConfigureExternalCollaborationSettings.html)

## Exercise 1 - Allowing guest users to be invited into the organization.

**Task 1 - Enableing guest users to perform self service sign-up**

Microsoft has changed the location in Entra for this "Official lab not updated" I found the settings by navigating to Entra ID - External Identities - External collaboration settings.  

Here we see the option to **Enable guest self-service sign up via user flow** and the lab tells us to enable this option. In my opinion we need a little more information on what are we exactly enableing 

*What "Enable guest self-service sign up via user flows" means:*
- We build an application that external users need to access
- We configure a user flow for sign up and sign in
- Guest register themselves through that flow instead of being invited manually

This means this feature is tied to applications and not Entra itself.

*What thype of applications are we talking about?:*
- Internal apps the organizations develops
- Third party applications integrated with Entra
- Web apps applications integrated with Entra

This means it refers to applications that rely on our tenant for authentication

Example: Lets say our trading company KlarStroem builds a partner portal  
External users must:
1. create an account
2. submit documents
3. access dashboard

Instead of us inviting them manually this feature supports:
- Portal uses self-service sign up
- supplier registers
- identity is created in Entra
- Access controlled through company policies

When first working with this task I was still left with a couple of questions:
1. Is this tied to mainly B2B collaboration or will this affect B2C in Anyway?
   - This feature only affects B2B collaborations.
2. Will the user after sign up automatically have a guest user created inside our tenant?
    - Yes, The user is created in our tenant and we controlled this through conditional access policies and authorization. Still the user is going to use their own identity provider for the whole authentication process.
3. How do we ensure that anyone can't just register themselves?
   - Domain restrictions, meaning we specify the trusted domains
     - This can be configued in the collaboration settings and in user flow or even app configuration.
   - Application assignment
   - Conditional access
     - MFA Required
     - Compliant device
     - Allowed locations
     - sign in risk policy

  My simple understanding of this feature is that self-service sign up is a controlled onboarding without manual identity creation by IT.

  ISO 27001 relevance:  
  This feature supports identity governance and controlled onboarding of external users.  
  Primary Annex A linkage:
  - A.5.15 Access control
  - A.5.16 Identity management
  - A.5.19 Information security in supplier relationships
  - A.8.5 Secure authentication

