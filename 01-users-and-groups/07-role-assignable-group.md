# Create and administrate Entra role assignable groups

## Overview
Role-assignable groups are special security groups in Entra ID that are designed to simplify the management of administrative roles. Instead of assigning a privieged role directly to each administrator, the role is just assigned to the group, and every member of the group will automatically have the role assigned and get the same permissions. This makes it easier to onboard new administrators, remove access when someone changes roles, and manage privileged access in the organization.

Role-assignable groups must use assigned membership. Dynamic membership is not supported because administrative roles should always be granted manually to prevent mistakes from happening.

For this lab i'm simply going to create a role-assignable group to group all KlarStroems user administators. I will therefore assign the role directly to the group instead of the users, and if configured correctly the members of the group should automatically get the role assigned, and if removed from the group, then the role should also automatically be unassigned.

## Objectives
- Create a role-assignable group in Entra ID
- Add and manage members of the group
- Assign the user administrator role to the group
- Verify that group members automatically gets the role assigned
- Verify that removing a user from the group also removes the administrative role
- Understand how role-assignable groups simplify the management of privileged access

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
