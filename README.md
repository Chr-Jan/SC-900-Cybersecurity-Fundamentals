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

What is common between all Microsoft Entra choices is:
- Establish Zero Trust access controls
- Secure access for employees
- Secure access for customers and partners
- Secure access in any cloud
- Secure access for AI agents

### Entra Models

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
| **Microsoft Entra Agent ID** | Identity and security framework for nonhuman AI agent identities |

### Microsoft Entra Licensing

| License Tier | What it includes |
| :--- | :--- |
| **Microsoft Entra ID Free** | Included with Microsoft cloud subscriptions (Azure, M365). Provides core identity capabilities: user/group management, basic reporting, and Self-Service Password Reset (SSPR). |
| **Microsoft Entra ID P1** | Adds Conditional Access, hybrid identity synchronization (Entra Connect/Cloud Sync), and advanced group management. Included in M365 E3 / Business Premium. |
| **Microsoft Entra ID P2** | Adds risk-based Conditional Access, Entra ID Protection, and Privileged Identity Management (PIM). Included in M365 E5. |
| **Microsoft Entra Suite** | A bundled license combining comprehensive identity and network access protection (requires Entra ID P1). Includes Private Access, Internet Access, ID Governance, ID Protection, and advanced Verified ID features. |

### Microsoft Entra Admin Center

Administrators configure and manage all Microsoft Entra products from a web-based portal called the Microsoft Entra admin center.

### Microsoft Entra External ID & Tenant Types

| Tenant Configuration / Feature | What it does |
| :--- | :--- |
| **Workforce Tenant** | Configured for employees, internal apps, and resources. Allows inviting external business partners and guests. |
| **External Tenant** | Configured exclusively for publishing apps to consumers and business customers (CIAM). |
| **External ID B2B Collaboration** | Allows workforce to share apps/services with external partners/guests using their own home credentials (no local guest passwords). |
| **External ID CIAM (Consumer)** | Adds customer identity and access management, self-service registration, and social logins (Google, Facebook) to consumer apps. |
| **B2B Direct Connect** | Creates a mutual trust relationship between two Entra organizations (enables Teams Connect shared channels without adding users as guests). |

### Hybrid Identity & Synchronization

| Concept / Tool | Short Description |
| :--- | :--- |
| **Hybrid Identity** | Common user identity across on-premises and cloud apps. |
| **Inter-directory Provisioning** | Copying/provisioning identities between two directory systems (e.g., Local AD to Entra ID). |
| **Synchronization** | Keeping local and cloud user/group data matching. |
| **Microsoft Entra Cloud Sync** | Microsoft's recommended tool, uses lightweight local agent, managed in the cloud. |
| **Microsoft Entra Connect Sync** | Older synchronization tool being replaced by Cloud Sync. |
| | **SCIM (System for Cross-domain Identity Management)** | Open standard used by Cloud Sync to automate user provisioning. |
