# Assign licenses using group-based licensing

## Overview
In a previous lab we created a dynamic security group named SG-HR-Staff. I'm going to reuse the dynamic group to automatically assign licenses to users. Group-based licensing lets you assign a license to a group, and everyone who becomes a member of that group will have have the license automaticallly assign. This also works the other way around, meaning if a user gets removed from the group the license will then automatically be removed as well.

This is an important feature in my opinion because just like with dynamic groups this also automates an important process, in this scenario assigning licenses to users. Not only does it automate the process, it also reduces mistakes, and therefore this approach is considered more secure. It is also important to mention that group-based licensing requires the tenant to have a P1 license as a minimum.

## Objectives
- Reuse the SG-HR-Staff security group for group-based licensing
- Apply the E5 license to the security group
- Verify that members of the security group automatically gets the E5 license assigned
- Verify that the license gets removed if a user no longer is a member of the group the license is assigned to

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

