## Tenant overview

Tenant Name: KlarStroem  
Tenant ID: 51fc7846-429d-4406-84e7-cfd3c0c3b3ec  
Region: Denmark  
Primary domain: klarstroem.onmicrosoft.com  
First global admin account: admin@klarstroem.onmicrosoft.com "Signup account becomes the first global admin"

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

*Tenant properties in Entra admin center*  
![Tenant properties in Entra admin center](screenshots/tenant-properties.png)


## Licensing

License type purchased:
- Microsoft 365 E5 trial license
  - Includes 25 licenses to assign to users

 Reason for choosing it:
 - The reason I chosee to sign up for Microsoft E5 is mainly because Entra ID P2 is included
  - Entra ID P2: Comes with all the advanced IAM capabilities that are nessesary for the upcoming labs

Capabilities unlocked:

Entra ID P2 capabilities:
- Identity protection
- Privileged Identity Management
- Access Reviews
- Entitlement Management

For my project I am mainly interested in understanding the difference between Entra ID Free, Entra ID P1 and Entra ID P2 licenses. I found this official Microsoft 365 plan comparison that gives an good overview of the differenct products and the capabilities included en each:  
[Microsoft 365 Enterprise plan comparison](https://www.microsoft.com/content/dam/microsoft/final/en-us/microsoft-brand/documents/Modern-Work-Plan-Comparison-ENT-1-16-2024.pdf)

## External collaboration baseline


## Emergency/ Break-glass accounts

