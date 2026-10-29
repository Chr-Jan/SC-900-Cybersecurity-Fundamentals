# SC-900-Cybersecurity-Fundamentals
Structured study notes, definitions, and exam prep for the Microsoft SC-900 Security, Compliance, and Identity Fundamentals certification.

## Basic Terminology & Core Concepts

| Concept | Short Description |
| :--- | :--- |
| **Tenant** | An instance of Microsoft Entra ID holding organizational objects (users, groups, devices, apps) and policies; serves as a security and administrative boundary. |
| **Directory** | A logical container within a tenant that holds and organizes identities and resources (one tenant consists of one directory). |
| **Multi-tenant** | An organization that has more than one instance of Microsoft Entra ID (e.g., due to mergers, subsidiaries, or compliance). |
| **Identity Secure Score** | A percentage indicating how closely your configuration aligns with Microsoft's security best practice recommendations. |

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

### Common Objectives
What is common between all Microsoft Entra choices is:
- Establish Zero Trust access controls
- Secure access for employees
- Secure access for customers and partners
- Secure access in any cloud
- Secure access for AI agents

### Entra Models

| Product / Feature | What it does |
| :--- | :--- |
| **Microsoft Entra ID** | Cloud-based IAM service that authenticates users and secures access to cloud/on-prem apps |
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

| Tool / Portal | Purpose |
| :--- | :--- |
| **Microsoft Entra Admin Center** | Centralized web-based portal where administrators configure and manage all Microsoft Entra products. |

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
| **SCIM** | Open standard used by Cloud Sync to automate user provisioning. |

## Identities

### Identity Types

| Category | Description |
| :--- | :--- |
| **Users** | Human identities representing employees, partners, and customers. |
| **Devices** | Hardware assets like mobile devices, laptops, servers, or printers. |
| **Workload Identities** | Software objects like applications, virtual machines, services, and containers. |

### User Types & Membership

| User Property / Classification | Description |
| :--- | :--- |
| **Internal Member** | Employees of the organization who authenticate internally via Entra ID (UserType: Member). |
| **External Guest** | External partners, vendors, or consultants using external credentials (UserType: Guest). |
| **External Member** | Users from a partner tenant given member-level access in another tenant. |
| **Internal Guest** | Legacy scenario where external users are given internal accounts designated as guests. |

### Workload & Managed Identities

| Concept | Description |
| :--- | :--- |
| **Workload Identity** | Assigned to software workloads to authenticate and access resources securely. |
| **Managed Identities** | Service principals where Azure automatically manages credentials, removing developer overhead. |
| **System-assigned Managed Identity** | Enabled directly on an Azure resource; lifecycle is tied to the resource (deleted automatically if resource is deleted). |
| **User-assigned Managed Identity** | Created as a standalone Azure resource that can be assigned to one or more services; must be deleted manually. |

### Device Identities

| Device Join Type | Description |
| :--- | :--- |
| **Microsoft Entra Registered** | Designed for Bring Your Own Device (BYOD) or mobile device scenarios using personal devices. |
| **Microsoft Entra Joined** | Devices joined to Entra ID through an organizational account, generally owned by the company. |
| **Microsoft Entra Hybrid Joined** | Devices joined to both on-premises Active Directory and Microsoft Entra ID. |

### Groups

| Group Type | Purpose |
| :--- | :--- |
| **Security Groups** | Used to manage user and device access to shared resources (can include users, devices, groups, service principals, and agent identities). |
| **Microsoft 365 Groups** | Used for grouping users according to collaboration needs (shared mailboxes, SharePoint, calendars). |

## Authentication Methods

### Core Authentication Concepts

| Concept | Description |
| :--- | :--- |
| **Authentication** | The process of verifying a person's or object's identity before granting access to resources. |
| **Passwords** | The most common authentication method, but vulnerable to compromises; should be replaced or supplemented. |
| **Phishing-Resistant Authentication** | Highly secure methods (using public key cryptography) bound to a specific domain, making them immune to AI-driven phishing sites. Includes Windows Hello, FIDO2, and Certificate-Based Auth. |

### Traditional & Secondary Methods

| Method | Description |
| :--- | :--- |
| **SMS-Based Sign-in** | Uses text messages with verification codes (not recommended by Microsoft for MFA due to security risks). |
| **Voice Call Verification** | Automated phone call where the user presses `#` on their keypad (secondary factor for MFA/SSPR). |
| **OATH Tokens** | Open standard for Time-based One-Time Password (TOTP) codes. Available as software apps or hardware key fobs. |
| **Temporary Access Pass (TAP)** | A time-limited passcode issued by admins to onboard new users or recover lost credentials. |
| **QR Code Authentication** | Allows frontline workers on shared devices to sign in by scanning a badge QR code and entering a PIN. |

### Passwordless Authentication Options

| Passwordless Method | Description |
| :--- | :--- |
| **Windows Hello for Business** | Replaces passwords on devices using a key/certificate tied to hardware, combined with a PIN or biometrics. |
| **Passkeys (FIDO2)** | Phishing-resistant method using public-key cryptography. Available as **Device-bound** (stored locally on a secure key/device) or **Synced** (synced across devices via a cloud provider). |
| **Microsoft Authenticator** | Versatile app supporting number-matching push notifications, passwordless sign-in, and generated OATH codes. |
| **Certificate-Based Auth (CBA)** | Allows users to authenticate directly with X.509 certificates, eliminating the need for federated infrastructure like AD FS. |

## Multifactor Authentication (MFA)

### MFA Core Factors & Principles

| Factor / Concept | Description |
| :--- | :--- |
| **Multifactor Authentication (MFA)** | Requires two or more verification methods from separate categories to confirm identity, stopping >99.9% of common identity-related attacks. |
| **Something You Know** | Typically a password or PIN. |
| **Something You Have** | A trusted device that is not easily duplicated, such as a phone, hardware key, or token. |
| **Something You Are** | Biometrics, such as a fingerprint scan or facial recognition. |

### Supported MFA Verification Methods

| Verification Method | Description / Usage |
| :--- | :--- |
| **Microsoft Authenticator** | App-based push notifications (with number matching), OATH codes, and passkeys. |
| **Authenticator Lite (in Outlook)** | Built-in MFA capability directly inside the Outlook mobile app. |
| **Windows Hello for Business** | Strong biometric/PIN authentication bound to the device hardware. |
| **Passkeys (FIDO2) & Authenticator Passkeys** | Phishing-resistant hardware or app-bound keys using public-key cryptography. |
| **Certificate-based Authentication** | X.509 certificates used directly for authentication and MFA. |
| **External Authentication Methods** | Integration with third-party MFA providers (like Duo or RSA). |
| **Temporary Access Pass (TAP)** | Time-limited passcode for onboarding or account recovery. |
| **OATH Tokens (Software & Hardware)** | Time-based one-time password (TOTP) tokens via apps or dedicated hardware key fobs. |
| **SMS & Voice Call** | Text messages or automated voice calls (discouraged by Microsoft due to security vulnerabilities). |

### MFA Enforcement & Policies

| Policy / Mechanism | Description |
| :--- | :--- |
| **Security Defaults** | Pre-configured baseline security settings **enabled by default on new tenants**. Automatically enforces MFA registration/prompts, blocks legacy authentication, and protects privileged access at no extra cost. |
| **Conditional Access** | Advanced, granular policies (**requires Entra ID P1 or P2 licenses**) that allow administrators to define rules requiring MFA based on specific conditions like user location, device state, risk level, or application sensitivity. |
