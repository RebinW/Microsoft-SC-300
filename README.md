# Microsoft Entra ID Enterprise Identity Lab

## About this project

This project documents the Microsoft Entra ID environment I have built to develop
practical experience with cloud and hybrid Identity and Access Management.

What originally started as hands-on preparation for the SC-300 certification gradually
developed into a much broader identity project. Rather than treating each Entra feature
as an isolated lab, I wanted to understand how the different parts of an enterprise
identity environment connect and depend on each other.

Throughout the project, I have therefore focused not only on how individual features
are configured, but also why they are used, what they depend on, and how they affect
security, governance, user experience, and the wider identity environment.

The environment is continuously expanded as I work through new areas of IAM.

## Environment

The environment combines Microsoft Entra ID with an on-premises Active Directory
environment to create a hybrid identity architecture.

The environment currently includes:

- Microsoft Entra ID tenant
- Microsoft 365 E5
- Microsoft Entra ID P2
- On-premises Active Directory Domain Services
- Microsoft Entra Connect
- Password Hash Synchronization
- Hybrid Microsoft Entra joined devices
- Microsoft Intune
- Microsoft Graph
- Enterprise Applications and App Registrations

[ARCHITECTURE DIAGRAM]

## What this project covers

### Tenant & Identity Foundation
- Tenant configuration
- Emergency access accounts
- User and group management
- Dynamic groups
- Role-assignable groups
- Group-based licensing
- Administrative Units

### Authentication & Access
- Authentication methods
- Multi-Factor Authentication
- Self-Service Password Reset
- Windows Hello for Business
- Temporary Access Pass
- Conditional Access
- Authentication strengths
- Session controls

### Hybrid Identity
- Microsoft Entra Connect
- Password Hash Synchronization
- Password writeback
- Hybrid Microsoft Entra Join
- Primary Refresh Token (PRT)
- Cloud Kerberos Trust
- Automatic Intune enrollment

### Applications & Modern Authentication
- Enterprise Applications
- App Registrations
- OAuth 2.0
- OpenID Connect
- Delegated permissions
- Application permissions
- Admin and user consent
- Microsoft Graph

### Identity Governance
- Privileged Identity Management
- Administrative Units
- Access Reviews
- Entitlement Management
- Catalogs and Access Packages
- Lifecycle Workflows

### External Identities
- B2B collaboration
- Guest users
- External collaboration settings
- Cross-tenant access settings

### Device Identity & Management
- Microsoft Entra registered devices
- Microsoft Entra joined devices
- Hybrid Microsoft Entra joined devices
- Microsoft Intune enrollment

## Project Documentation

The repository contains individual implementation sections documenting the
configuration, testing, validation, and security considerations for each area.

**Learning and lab resources**
- [Microsoft Learn SC300 Learning Path](https://learn.microsoft.com/en-us/training/courses/sc-300t00)
- [Microsoft SC300 official labs](https://microsoftlearning.github.io/SC-300-Identity-and-Access-Administrator/)
- [Microsoft Entra ID documentation](https://learn.microsoft.com/en-us/entra/identity/)
- [Microsoft Learn official SC300 YouTube course](https://www.youtube.com/playlist?list=PLahhVEj9XNTf6lWUbZLBNULQ7uVqM5Sad)

**Related ISO 27001 project**
- [ISO 27001 implementation project]()
