# Assigning licenses using group membership

[Offial Microsoft link to the lab](https://microsoftlearning.github.io/SC-300-Identity-and-Access-Administrator/Instructions/Labs/Lab_03_AssignLicensesToUsersByGroupMembershipAAD.html)

## Objective

- Implement group based licensing
- Reduce manual license assignment
- Validate access provisioning

## Tools used

- Microsoft Entra admin center
- Microsoft 365 admin center
- Security groups
- Dynamic groups

## Methodology

**Exercise 1: Create a security group and add a user**

**Task 1: Check to see if the user has access to Office 365**

I reviewed the user account in Microsoft Entra and Microsoft 365 admin center to confirm license status and service access. I also checked to ensure that the user isn't a member of any group yet, since the goal of the lab is to assign the license through group based licensing.

**Task 2: Create a security group in Microsoft 365**  
In Microsoft Entra admin center, I created the following group:  
- Group type: Security
- Group name: sg-SC300-O365
- Group description: Test Group for SC300 lab
- MS Entra roles can be assigned to this group: NO
- Membership type: Assigned

I chose my own account as the owner of the group and selected The test user Chris Green to be a member of the group. 

**Task 3: Add an Office license to sg-SC3000-O365**  
For this task i'll assigned the Office 365 license manually, to do this I have to navigate to the MS 365 admin center, path: Billing - Licenses - Office 365 E5 - assign licenses.

I'll then chose to assign the license to the newly created security group *sg-SC300-O365* instead of assigning directly to the user.

Afterwards, I went into Entra admin center and chose the newly created security group just to confirm that the license has been assigned correctly to the group.

**Task 4: Confirm the Office 365 license**  

In task 3 I succesfully assigned the license to the group, so I will now simply test weather the user have been given the license. To test this I go straight into [Office](https://www.office.com.) and login as Chris to see if I have the Office applications available to me:

![Office assigned correctly](chris-office.png)
