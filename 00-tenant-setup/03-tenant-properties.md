## Tenant properties

*Technical contact*
- Technical contact is assigned to someone responsible for Entra administration and coordination with Microsoft support. In a mature environment "depending on the policy" this would normally be a shared mailbox or IAM operations role

*Global privacy contact*
- Placeholder used to represent the person or the department responsible for privary
- This person/ department is also who Microsoft will contact in case of a data breach.
  - If there is no contact registered, then Microsoft will contact global admin accounts

*Privacy statement URL*
- This represents the organization's privacy notice/ policy describing how identity data is handled for internal users and external guest users "B2B" accessing the tenant.

*Access management for Azure resources*
- I left this disabled to follow the principle of least privilege and avoid automatic access to all Azure subscriptions aswell.

*Security defauls*
- Enabled this because it enforces MFA registration on all users, this works as best practice during the initial tenant setup. Later I will replace the baseline security with my own conditional access policies.

**Tenant properties in Entra admin center**  
![Tenant properties in Entra admin center](screenshots/tenant-properties.png)
