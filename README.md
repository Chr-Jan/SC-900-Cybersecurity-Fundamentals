# SC-900-Cybersecurity-Fundamentals
Structured study notes, definitions, and exam prep for the Microsoft SC-900 Security, Compliance, and Identity Fundamentals certification.

## Security and Compliance Concepts

### Shared Responsibility Model

| Service | Me (Customer Responsibility) | Cloud Provider (CSP Responsibility) |
| :--- | :--- | :--- |
| **On-Prem** | **Everything** (Physical datacenter, hardware, OS, apps, data) | **None** |
| **IaaS** | Operating Systems, Network Controls, Applications, **Data** | Physical Datacenter, Physical Network, Host Infrastructure |
| **PaaS** | Application Code, Configurations, Access Control, **Data** | Infrastructure, OS, Runtime Environment |
| **SaaS** | Identity & Access Management (IAM), Tenant Configurations, **Data** | Entire Application Stack & Infrastructure |


### Responsibilities You Always Retain

| Always Your Responsibility | What it includes |
| :--- | :--- |
| **Data** | Classification, sensitivity, encryption decisions, and governance |
| **Identities and Access** | User accounts, MFA, and least-privilege access control |
| **Endpoints** | Laptops, mobile devices, and desktops connecting to your cloud services |
| **Configuration** | Tenant settings, resource permissions, and security policies |

## Microsoft Entra

What is common between all Microsoft Entra chocies is

- Establish Zero Trust access controls
- Secure access for employees
- Secure access for customers and partners
- Secure access in any cloud
- Secure access for AI agents

### Entra models

| Product / Feature | What it does |
| :--- | :--- |
| **Microsoft Entra ID** | Authenticates employees, sign-on to corporate apps, cloud-based |
| **Microsoft Entra Domain Services** | Domain services for old applications, cloud-based, Windows Server Active Directory |
| **Microsoft Entra Verified ID** | Credential verification service based on decentralized standards |
| **Microsoft Entra ID Governance** | Automatically provisions access based on the employee's role and lifecycle |
| **Microsoft Entra ID Protection** | Evaluates sign-in for risk and triggers stronger authentication when needed |
| **Microsoft Entra Internet Access** | Secures connection to cloud and internet resources |
| **Microsoft Entra Private Access** | Secure access to on-premises apps without a VPN |
| **Microsoft Entra External ID** | External identities access business resources and consumer apps (B2B/CIAM) |
| **Microsoft Entra Workload ID** | Identity and access management solution for workload identities (apps/containers) |
| **Microsoft Entra Agent ID** | Identity and security framework for nonhuman AI agent identities. |

### Microsoft Entra licensing

| License Tier | What it includes |
| :--- | :--- |
| **Microsoft Entra ID Free** | Included with Microsoft cloud subscriptions (Azure, M365). Provides core identity capabilities: user/group management, basic reporting, and Self-Service Password Reset (SSPR). |
| **Microsoft Entra ID P1** | Adds Conditional Access, hybrid identity synchronization (Entra Connect/Cloud Sync), and advanced group management. Included in M365 E3 / Business Premium. |
| **Microsoft Entra ID P2** | Adds risk-based Conditional Access, Entra ID Protection, and Privileged Identity Management (PIM). Included in M365 E5. |
| **Microsoft Entra Suite** | A bundled license combining comprehensive identity and network access protection (requires Entra ID P1). Includes Private Access, Internet Access, ID Governance, ID Protection, and advanced Verified ID features. |

### Microsoft Entra admin center

Administrators configure and manage all Microsoft Entra products from web-based portal called Microsoft Entra admin center.
