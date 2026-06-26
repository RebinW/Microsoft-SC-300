# Licenses

## Identify and resolve license assignment problems for groups

**Not enough licenses**
- Problem: Not enough available licenses
- PowerShell cmdlets report *CountViolation*

**Service plans that conflict**
- Problem: A products service plan conflicts with another serviceplan
- Example: SharePoint Online (Plan 2) conflicts with SharePoint Online (Plan 1)
- PowerShell Cmdlets report: *MutuallyExclusiveViolation*

**Other Products depend on this license**
- Problem: One of the products that's specified in the group contains a service plan that must be enabled for another service plan, in another product, to function.
- Example: Teams depends on ExchangeOnline, Teams stores calendars, meeting data and contratcs in Exchange.
- PowerShell cmdlets report: *DependencyViolation*

**Usage location isn't allowed**
- Problem: Some MS services aren't available in certain locations because of laws and regulations.
- Example: MS Entra tries to assign a group license to a user whose usage location isn't supported, it will fail
- PowerShell cmdlets report: *ProhibitedInUsageLocationViolation*
- NOTE: If a user is created and the location of that user isn't specified and a group license gets assigned to that user, the user will then inherit the location of the tenant.

**Duplicate proxy addresses**
- Problem: Two users share the same email alias

**MS Entra and ProxyAddresses attribute change**
- Updating license assignment on a user or group can change email and proxy addresses attributes on some users.
- Example: Something always triggers email provisioning, common triggers:
  - Assigning Exchange license for the first time: mailbox gets created and email attributes gets generated
  - Remove and reassign Exchange license: mailbox provisioning runs again and attributes can recalculate
  - Group-based licensing changes: User added or removed: provisioning runs again
  - domain changes, UPN changes triggers provisioning
- During provisioning process it checks:
  - Naming policy
  - Default domain
  - uniqueness
  - Existing aliases

**LicenseAssignmentAttributeConcurrencyException in Auditlogs**
- Problem: Entra tried to assign the same license to the same user at the same time from multiple sources
  - User belongs to several groups and each group has the same license assigned
- Example: Entra processes licensing in parallel, meaning there is a collision because Entra tries to assign same licenses to a user at the same time and therefore the systems detects the collision and logs it.
- Its a time problem not a failure Entra will:
  - Stop one process and retry automatically
 
**More than one product license assigned to a group**
- When a group has multiple licenses, Entra treats them as one package during assignment.
- Example: Group has both   MS 365 E3 and Enterprise mobility + security E3
  - User joins group and Entra tries to assign both licenses together if one fails then the other is also blocked
  - This prevents a user from ending up in a half-configured state
- Typical failure cases:
  - Not enough licenses
  - Service conflict
  - Dependency issues
  - Location restriction

**When a license group is deleted**
- Problem: Some add-ons licenses require a base license, if the base license disappears the add on would stop working.
- Example: Group has MS 365 E3 assigned, and E3 includes skype for business. Lets say some users have audio conferencing assigned directly to those users.
  - Audio conferencing depends on skype for business it cannot exist alone
- Because those those users have add-ons that are dependent on other services Entra will before de3letion:
  - Apply E3 directly to those effected users automatically, meaning if another license is dependent on it, Entra keeps it as a direct assignment.
 
**Manage licenses for products with prerequisites**
- Problem: Some add-on services requiere a base license = prerequisites to work, this means we cannot assign add-ons to a group without including the prerequisites necessary for the add-on to work.
- Example: MS workspace analytics is an add-on product, we can only assign the service to a user or group if Exchange online is assigned.
- Solution: We assign Office 365 E3 with only Exchange Online service to the group and MS Workplace analytics to the group.
  - If the user has the full MS Office E3 license assigned directly or through another group, the license is still only consumed once


**Force the group license process to resolve errors**
- Depending on what steps you've taken to resolve the errors, it might be necessary to manually trigger the processing of a group to update the user state.

**Force the user license process to resolve errors**
- Depending on what steps you've taken to resolve the errors, it might be necessary to manually trigger the processing of a user to update the user's state.
  
**How to migrate users with individual licenses to group licenses**
- [Take a look at the example here](https://learn.microsoft.com/en-us/training/modules/create-configure-manage-identities/9-exercise-change-group-license-assignments)

**Change license assignments for a user or group in MS Entra ID**






