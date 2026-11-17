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

### Zero Trust & Defense in Depth

| Framework / Concept | Core Principles & Layers |
| :--- | :--- |
| **Zero Trust Strategy** | Security model based on three guiding principles:<br>• **Verify explicitly:** Always authenticate and authorize based on all available data points (identity, location, device health, service/workload, data classification, anomalies).<br>• **Use least privilege access:** Limit user access with Just-In-Time and Just-Enough-Access (JIT/JEA), risk-based adaptive policies, and data protection.<br>• **Assume breach:** Minimize blast radius and segment access; verify end-to-end encryption and use analytics to get visibility and drive threat detection. |
| **Defense in Depth** | Layered security approach designed to slow down an attack by placing multiple independent security controls across seven concentric layers:<br>1. **Physical Security** (datacenter access)<br>2. **Identity & Access** (authentication, MFA, RBAC)<br>3. **Perimeter** (DDoS protection, firewalls)<br>4. **Network** (segmentation, NSGs, private endpoints)<br>5. **Compute** (VM hardening, EDR, patching)<br>6. **Application** (secure coding, WAF, Key Vault)<br>7. **Data** (encryption at rest/in transit, sensitivity labels, access controls) |

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
| **Microsoft Entra Cloud Sync** | Microsoft's recommended tool; uses lightweight local agents managed in the cloud, utilizing SCIM for automated provisioning. |
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
| **Security Defaults** | **Free and enabled by default on new tenants.** Pre-configured baseline security settings that automatically enforce MFA, block legacy authentication, and protect privileged access. However, they are **all-or-nothing (inflexible)** and allow no custom exceptions. |
| **Conditional Access** | Advanced, granular policies (**requires Entra ID P1 or P2 licenses**) that allow administrators to define rules requiring MFA based on specific conditions like user location, device state, risk level, or application sensitivity. |

## Self-Service Password Reset (SSPR)

### SSPR Core Concepts & Requirements

| Concept / Requirement | Description |
| :--- | :--- |
| **Self-Service Password Reset (SSPR)** | Allows users to change or reset their password without administrator or help desk involvement, reducing help desk calls. |
| **License Requirement** | Users must be assigned a Microsoft Entra ID license. |
| **Admin Configuration** | Users must be explicitly enabled for SSPR by an administrator. |
| **Registration Requirement** | Users must register required authentication methods beforehand (two or more methods are recommended). |

### Supported SSPR Authentication Methods

| Authentication Method | Description / Notes |
| :--- | :--- |
| **Microsoft Authenticator Push** | Push notifications for verification. |
| **Software OATH Tokens** | App-generated TOTP codes. |
| **Hardware OATH Tokens** | Hardware-based TOTP tokens (preview). |
| **SMS & Voice Call** | Text messages or automated phone calls with codes. |
| **Email OTP** | One-time passcode sent to an external/secondary email address. |
| **Security Questions** | **Retiring in March 2027** (organizations should migrate users away from this method). |

### SSPR Administration, Hybrid Integration & Recovery

| Feature / Concept | Description |
| :--- | :--- |
| **Registration & Reconfirmation** | Admins can force users to register for SSPR upon sign-in and require users to reconfirm their authentication info periodically (0 to 730 days). |
| **Notifications** | Automated email alerts sent to users when their password is changed, and to global admins when another admin resets their password. |
| **Password Writeback (Hybrid)** | Allows password changes/resets made in the cloud (Entra ID) to be instantly written back to an on-premises Active Directory via Entra Cloud Sync. |
| **Account Recovery** | For **total lockouts** where users lost access to all MFA methods. Uses an Identity Verification (IDV) provider (like Entra Verified ID with Face Check) to match a real-time selfie against a government-issued ID without human intervention. |

## Microsoft Entra Agent ID

### Core Concepts & Challenges for AI Agents

| Concept / Challenge | Description |
| :--- | :--- |
| **Microsoft Entra Agent ID** | An identity and security framework designed specifically for AI agents to authenticate, authorize, govern, and protect them at enterprise scale. |
| **Expanded Attack Surface** | AI agents interact with external systems and are vulnerable to attacks like prompt injection. |
| **Permission Risks** | Agents are often provisioned with broad permissions, risking excessive data access. |
| **Agent Sprawl** | Uncontrolled expansion of agents without visibility, management, or lifecycle controls. |

### Blueprint-to-Identity Model

| Component | Description |
| :--- | :--- |
| **Agent Identity Blueprints** | Reusable templates defining a class of agent, holding credentials and allowing admins to apply policies to all agents of that type. |
| **Agent Identities** | Individual instances created from a blueprint (with a unique ID, display name, and a human sponsor/owner). They rely on blueprints for tokens. |
| **Platform-Agnostic** | Integrates with both Microsoft and non-Microsoft agent platforms (e.g., AWS Bedrock, n8n) using the Auth SDK or workload identity federation. |

### Authentication Scenarios

| Authentication Pattern | Description |
| :--- | :--- |
| **Attended (On-behalf-of)** | The agent operates on behalf of a human user, using delegated user permissions and acting under their authority. |
| **Unattended** | The agent acts autonomously under its own identity, using its own assigned roles and permissions without a user present. |

### Governance, Security & Least Privilege

| Feature / Security Rule | Description |
| :--- | :--- |
| **Conditional Access & Risk Detection** | Applies policy-based access controls, risk evaluation, and real-time threat detection specifically for agents. |
| **Identity Governance & Registry** | Provides lifecycle management, compliance reporting, centralized metadata management, and secure agent discovery via human sponsors. |
| **Principle of Least Privilege** | Agents are strictly blocked from high-privilege roles, and users/admins can't consent to powerful permissions, minimizing escalation risks. |

## Identity as the Primary Security Perimeter

### Network Perimeter vs. Identity Perimeter
- **Traditional Perimeter:** Enforced by firewalls and VPNs; trusted traffic based on network location (inside vs. outside).
- **Identity Perimeter:** Enforces access based on verified identity (user, device, workload, AI agent) regardless of network location. Core to the **Zero Trust** strategy.

### The 4 Modern Identity Types
| Identity Type | Scope & Description |
| :--- | :--- |
| **Human Identities** | Employees, contractors, partners, and customers signing in to access resources. |
| **Device Identities** | Laptops, mobile devices, IoT hardware enrolled and checked for management and compliance. |
| **Workload Identities** | Non-human software processes, containers, services, and applications accessing APIs and data. |
| **Agent Identities** | Autonomous and assistive AI agents interacting with systems on behalf of users or processes. |

### The 4 Pillars of Identity Infrastructure
| Pillar | Purpose | Key Capabilities |
| :--- | :--- | :--- |
| **Administration** | Identity lifecycle and governance | Provisioning, role updates, deprovisioning, policy definition. |
| **Authentication** | Identity verification | Passwords, MFA, Passkeys (FIDO2), Certificate-Based Auth. |
| **Authorization** | Granular access control | Role-Based Access Control (RBAC), Conditional Access, Principle of Least Privilege. |
| **Auditing** | Tracking and accountability | Sign-in logs, audit logs, anomaly detection, forensic reporting. |

## Modern Authentication & The Identity Provider (IdP)

### Core Role of an IdP
- **Definition:** A centralized service that creates, stores, and manages identity data, providing authentication, authorization, and auditing to relying applications.
- **Delegation:** Applications offload credential validation and security policies to the IdP, eliminating local user databases and fragmented password policies.

### Security Tokens & Claims
- **Claims:** Statements made about an entity inside a token (e.g., `user_id`, `email`, `role`, `exp`).
- **ID Token:** Serves as proof of **authentication**; tells the application *who* signed in.
- **Access Token:** Serves as proof of **authorization**; permits access to specific APIs/resources on the user's behalf.
- **Lifespan:** Tokens are strictly time-limited to mitigate the blast radius of token theft.

### Authentication & Authorization Protocols
| Protocol | Purpose | Key Mechanism |
| :--- | :--- | :--- |
| **OAuth 2.0** | **Authorization** | Issues access tokens to call protected APIs |
| **OpenID Connect (OIDC)** | **Authentication** | Built on OAuth 2.0; issues ID tokens containing user profile claims |
| **SAML** | Enterprise Auth & SSO | XML-based token exchange; standard for legacy/on-premises federation |

### Single Sign-On (SSO) Benefits
- **Frictionless Access:** Sign in once, access all relying applications without repeated prompts.
- **Attack Surface Reduction:** Minimizes credential prompts, combating password fatigue and credential phishing.
- **Centralized Revocation:** Disabling an account in the IdP immediately revokes access across all integrated enterprise applications.

## Directory Services & Active Directory

### Directory vs. Directory Service
- **Directory:** A structured hierarchical database storing metadata about network objects (users, devices, groups, resources).
- **Directory Service:** The software platform that stores directory data and makes it accessible for authentication and authorization.

### Active Directory Domain Services (AD DS)
- **Role:** Centralized on-premises directory service for Windows Server domain environments.
- **Domain Controller (DC):** The server running the AD DS role that authenticates users and enforces security policies.
- **Core Mechanisms:**
  - **Kerberos & NTLM:** Native protocols for user and service authentication.
  - **LDAP / LDAPS:** Protocol used to query and modify directory objects.
  - **Group Policy (GPO):** Centralized policy framework to enforce device and user configurations.
  - **Organizational Units (OUs):** Hierarchical containers used to organize objects and apply GPOs.

### Why AD DS Falls Short for Cloud Environments
- **Protocol Incompatibility:** Relies on Kerberos/NTLM/LDAP rather than modern web protocols (OAuth 2.0, OIDC, SAML).
- **Network Boundary:** Requires direct line-of-sight or VPN to a Domain Controller to authenticate.
- **Device Limitations:** Designed primarily for Windows-joined domain machines, lacking native mobile (iOS/Android) management.
- **Cloud Workloads:** Cannot natively authenticate SaaS or third-party cloud apps without federation or sync tooling.

### AD DS vs. Microsoft Entra ID
| Feature | Active Directory (AD DS) | Microsoft Entra ID |
| :--- | :--- | :--- |
| **Architecture** | On-premises (Domain Controllers) | Multi-tenant cloud IDaaS |
| **Protocols** | Kerberos, NTLM, LDAP | OAuth 2.0, OpenID Connect, SAML, Graph API |
| **Connection** | Corporate LAN or VPN | Internet-accessible (HTTPS) |
| **Device Model** | AD Domain Join | Entra Registered, Joined, Hybrid Joined |
| **Hierarchy** | Forests, Domains, OUs | Flat structure within a Tenant |
| **Hybrid Sync** | Master identity source in hybrid setups | Synchronized via Entra Cloud Sync / Connect |

## Identity Federation

### Definition & Purpose
- **Federation:** Establishing a trust relationship between separate Identity Providers (IdPs) to enable cross-domain access without creating separate user accounts.
- **Core Value:** Users authenticate once at their home IdP; external resource IdPs accept the home IdP's security tokens.

### Key Characteristics
- **One-Way vs. Two-Way:** Trust relationships are **not automatically bidirectional**. If Org A trusts Org B, Org B does not automatically trust Org A unless explicitly configured.
- **Standardized Protocols:** Built on open standards like SAML, WS-Federation, and OpenID Connect to guarantee cross-vendor interoperability.

### Primary Federation Scenarios
| Scenario | Implementation & Benefit |
| :--- | :--- |
| **B2B Collaboration** | Two organizations establish IdP trust so partners use native corporate credentials to access shared internal resources. |
| **Consumer / Social Logins** | External apps trust social providers (Google, GitHub, Microsoft) to streamline onboarding without local account creation. |
| **On-Premises Hybrid (AD FS)** | Active Directory Federation Services projects on-prem AD DS identities to cloud services using secure token exchanges. |

## Azure Infrastructure Security Services

### Azure Firewall

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Azure Firewall?** | A managed, cloud-based network security service that protects Azure cloud workloads and resources with stateful inspection. |
| **Deployment Architecture** | Typically deployed on a centralized virtual network (Hub VNet) through which all other VNets and local networks route traffic. |
| **Core Capabilities** | Stateful firewall, built-in High Availability across Availability Zones, Network & Application level filtering (FQDN), Source/Destination NAT (SNAT/DNAT), and Threat Intelligence integration. |
| **Firewall Tiers** | **Basic** (for SMBs, ~250 Mbps, threat intel alert-only), **Standard** (Layers 3-7 filtering, real-time threat intel, enterprise production standard), **Premium** (adds IDPS with over 67,000 signatures for advanced malware/phishing protection). |
| **Azure Firewall Manager** | Centralized management tool to define and apply common network/app firewall policies across multiple subscriptions and VNets/Virtual WANs. |
| **Security Copilot Integration** | Allows security analysts to use natural language prompts to investigate malicious traffic, IDPS logs, and threat intelligence (requires structured logging to a Log Analytics workspace and proper RBAC permissions). |

### Web Application Firewall (WAF)

| Feature / Aspect | Description |
| :--- | :--- |
| **What is WAF?** | A centralized Web Application Firewall that protects web apps against common web exploits and vulnerabilities (based on OWASP core rule sets), simplifying security management. |
| **Layer 7 DDoS Protection** | Defends web applications against application-layer DDoS attacks like HTTP Floods, which traditional network/transport layer DDoS protections don't cover. |
| **Protected Vulnerabilities** | Defends against OWASP top threats including **SQL Injection** (malicious database queries), **Cross-Site Scripting (XSS)** (malicious scripts injected into pages), **HTTP Floods**, and **Remote File Inclusion**. |
| **Deployment Options** | Can be integrated with **Azure Application Gateway** (regional), **Application Gateway for Containers** (modern container workloads), **Azure Front Door** (global CDN and app delivery), or **Azure CDN** (static/dynamic content). |
| **Security Copilot Integration** | Integrates with Microsoft Security Copilot to let analysts investigate WAF logs and attack vectors using natural language prompts. |

### Azure Network Segmentation & Virtual Networks

| Concept / Element | Description |
| :--- | :--- |
| **Network Segmentation Principles** | Dividing networks into smaller segments to group related assets, isolate resources, and enforce governance. Aligns with Zero Trust (**Assume Breach**) and Defense in Depth to contain attackers and prevent lateral movement. |
| **Azure Virtual Network (VNet)** | Fundamental building block for private networks in Azure providing scale, availability, and isolation. **No traffic is allowed across VNets or inbound by default** (explicit provisioning required). |
| **VNet Core Capabilities** | Supports outbound internet communication, secure inter-resource communication, hybrid connectivity (VPN/ExpressRoute), traffic filtering (NSGs/Firewall), and custom routing. |
| **Subnets** | Smaller network segments created *within* a VNet to isolate workloads by security requirements or function (e.g., placing web servers and database servers on separate subnets). |
| **VNet Peering** | Connects two VNets together (supports **global peering** across regions) over the private, low-latency Microsoft backbone network rather than the public internet. |

### Azure Bastion

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Azure Bastion?** | A fully managed PaaS service deployed in your VNet that provides secure, seamless RDP and SSH connectivity to VMs directly through the Azure Portal via TLS (port 443). |
| **Key Benefits** | No public IP required on the target VMs, no need to manage NSGs for Bastion subnet, protects VMs from port scanning, and eliminates the risk of exposing administration ports (RDP/SSH) directly to the internet. |
| **Bastion Tiers** | **Developer** (free, shared infrastructure, 1 concurrent VM connection, dev/test only), **Basic** (dedicated capacity, moderate production use), **Standard** (adds native client support, shareable links, custom ports, file transfer, and host scaling), **Premium** (adds session recording and private deployment without public IP). |
| **Connection Methods** | **Browser-based** (HTML5 via Azure Portal, all tiers), **Native client** (local SSH/RDP clients, Standard/Premium), **Shareable links** (access without Azure Portal login, Standard/Premium). |

### Azure Key Vault

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Azure Key Vault?** | A cloud service for securely storing and tightly controlling access to application secrets (API keys, passwords, certificates, and cryptographic keys). |
| **Core Functions** | **Secrets Management** (passwords, connection strings), **Key Management** (encryption keys), and **Certificate Management** (provisioning, deployment, and auto-renewal of TLS/SSL certs). |
| **Why Use Key Vault?** | Centralizes secrets so developers don't hardcode them in application code; prevents accidental leaks; backed by robust authentication (Entra ID) and authorization (Azure RBAC or Access Policies); isolates applications into separate vaults. |
| **Zero Trust Alignment** | Supports the **least privilege** principle by granting apps/users access *only* to the specific secrets they need, limiting the blast radius if compromised. Microsoft cannot see or extract your data. |
| **Azure Service Integration** | Integrates natively with **Azure Disk Encryption** (disk keys), **Azure SQL Database** (data protection keys), and **App Service** (runtime configuration retrieval without code exposure). |
| **Service Tiers** | **Standard** (software-based key protection for typical business scenarios) and **Premium** (Hardware Security Module [HSM]-protected keys where keys never leave the tamper-resistant hardware boundary, designed for strict regulatory/compliance requirements). |

### Microsoft Defender for Cloud

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Defender for Cloud?** | A cloud-native application protection platform (CNAPP) that protects workloads across Azure, AWS, GCP, and on-premises by combining posture management, workload protection, and DevSecOps. |
| **Three Core Pillars** | **DevSecOps** (shift-left security, unifying vulnerability management across code and pipelines like GitHub/Azure DevOps), **CSPM** (Cloud Security Posture Management, tracking misconfigurations and generating a secure score), and **CWPP** (Cloud Workload Protection Platform, providing resource-specific protection plans like Defender for Servers/Storage/Databases). |
| **AI Security & Threat Protection** | Features **AI Security Posture Management (AI SPM)** to maintain an AI Bill of Materials (AI BOM) and **AI Threat Protection** to detect real-time risks like prompt injection, data leakage, and data poisoning using Threat Intelligence and Azure AI Content Safety. |
| **Security Copilot Integration** | Embeds AI assistance to let security professionals use natural language prompts to analyze recommendations, summarize findings, and receive remediation guidance. |
| **Portal Integration** | Deeply integrated into the Microsoft Defender portal, unifying posture management and threat protection into a single experience across cloud, hybrid, and code environments. |

### Security Policies, Standards & Recommendations

| Concept / Element | Description & Role in Cloud Security Posture |
| :--- | :--- |
| **Security Policies & Initiatives** | Backed by **Azure Policy**. A *policy definition* specifies a distinct security condition, a *security initiative* groups related policies together toward a common goal, and *assignments* apply them to resource scopes (subscriptions, resource groups, etc.). When resources fail to comply with a policy, a recommendation is generated. |
| **Security Standards & MCSB** | The built-in default standard is the **Microsoft Cloud Security Benchmark (MCSB)**, which provides cloud-centric best practices built on CIS and NIST frameworks for Azure, AWS, and GCP. It directly maps recommendations to industry frameworks (ISO, NIST, PCI DSS). |
| **Security Recommendations** | Actionable guidance generated when resources fail compliance checks against active policies. Prioritized by severity (High, Medium, Low) and—in Defender CSPM—enriched with risk factors such as internet exposure and data sensitivity. |
| **Regulatory Compliance Standards** | Allows organizations to add external standards (e.g., ISO 27001, SOC 2, PCI DSS) to the compliance dashboard. **Key benefit:** Addressing a single security recommendation can automatically improve compliance status across multiple standards simultaneously. |

### Cloud Security Posture Management (CSPM)

| Feature / Aspect | Description |
| :--- | :--- |
| **What is CSPM?** | A core pillar of Microsoft Defender for Cloud providing hardening guidance, security posture visibility, and misconfiguration tracking across multicloud environments (Azure, AWS, GCP). |
| **Secure Score** | The central metric aggregating continuous cross-cloud findings into a single percentage based on the **Microsoft Cloud Security Benchmark (MCSB)**. A higher score indicates a lower identified risk level. |
| **Hardening Recommendations** | Actionable advice grouped into security controls. Remediation improves the score only when all recommendations for a single resource within a control are resolved. |
| **Advanced Defender CSPM Features** | • **Attack Path Analysis:** AI-powered modeling of vulnerability chains to prioritize critical risks.<br>• **Cloud Security Explorer:** Graph-based query tool to proactively uncover and investigate cloud risks.<br>• **Governance:** Tools to assign remediation tasks, owners, and due dates to drive accountability.<br>• **Data Security Posture Management (DSPM):** Automatically discovers datastores with sensitive data and assesses their security posture.<br>• **AI Security Posture Management (AI SPM):** Maintains an AI Bill of Materials (AI BOM) and secures generative AI workloads against chained risks. |
| **Security Copilot Integration** | Embeds AI assistance on recommendations pages to explain context, evaluate implementation effects, provide step-by-step remediation guidance, and remediate misconfigurations directly in code. |
| **Foundational vs. Advanced Plan** | • **Foundational CSPM (Free):** Asset discovery, continuous assessment, MCSB compliance, and secure score.<br>• **Defender CSPM Plan (Paid):** Adds advanced capabilities like attack path analysis, cloud security explorer, governance, DSPM, and AI SPM. |

### Enhanced Security & Workload Protection (CWPP)

| Feature / Aspect | Description |
| :--- | :--- |
| **What is CWPP?** | The pillar of Microsoft Defender for Cloud dedicated to detecting and resolving threats to resources, workloads, and services through specific **Microsoft Defender Plans**. |
| **Key Microsoft Defender Plans** | • **Defender for servers:** Adds threat detection, advanced defenses, and EDR via Defender for Endpoint.<br>• **Defender for App Service:** Identifies attacks targeting web applications.<br>• **Defender for Storage:** Detects harmful activity on Azure Storage accounts.<br>• **Defender for Databases:** Protects Azure SQL, open-source databases, and Cosmos DB.<br>• **Defender for Containers:** Cloud-native security for Kubernetes, hardening, and runtime threat detection.<br>• **Defender for Key Vault:** Advanced threat protection for secrets and keys.<br>• **Defender for Resource Manager:** Monitors resource management operations.<br>• **Defender for AI Services:** Protects AI workloads against prompt injection, data leakage, poisoning, and credential theft.<br>• **Defender for APIs:** Secures business-critical APIs and prioritizes vulnerability fixes. |
| **Enhanced Security Features** | • **Comprehensive EDR:** Integrated endpoint detection and response via Defender for Endpoint.<br>• **Vulnerability Scanning:** Built-in scanning for VMs, container registries, and SQL resources.<br>• **Multicloud & Hybrid Security:** Extends protection to AWS, GCP, and on-premises hybrid workloads with unified policy enforcement.<br>• **Threat Protection Alerts:** Monitors networks, machines, and cloud services for incoming and post-breach attacks.<br>• **Access & Application Controls:** Includes Just-In-Time (JIT) VM access and adaptive application controls to block unwanted apps and reduce brute-force exposure. |
| **Protecting AI Workloads** | Leverages Microsoft Threat Intelligence and Azure AI Content Safety Prompt Shields to monitor generative AI services in real time, detecting prompt injection, data leakage, data poisoning, and credential theft. Alerts integrate directly with Microsoft Defender XDR. |

### DevOps Security Management (Defender for DevOps)

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Defender for DevOps?** | A service in Microsoft Defender for Cloud that empowers security teams to manage and secure DevOps environments across multi-pipeline platforms (GitHub, Azure DevOps, GitLab) from code to cloud. |
| **Core Capabilities** | • **Unified Visibility:** Centralized view of pre-production code posture, inventories, code scanning findings, exposed secrets, and open-source software (OSS) dependencies.<br>• **IaC Template Hardening:** Assesses Infrastructure as Code (IaC) templates to minimize cloud misconfigurations before resources ever reach production.<br>• **Prioritized Remediation:** Leverages pull request annotations and custom workflows to assign developer ownership and fix issues directly in code. |
| **Security Overview Metrics** | Surfaces high-level metrics across key risk dimensions: **Code scanning vulnerabilities**, **Exposed secrets** (API keys/credentials), **Open-source software (OSS) vulnerabilities**, and **Environment recommendations**. |
| **AI Development Pipelines** | Protects AI application workflows by catching exposed AI service API keys and insecure infrastructure templates during development before they reach production. |
| **Code-to-Cloud Integration** | Integrates DevOps findings into the broader Defender for Cloud platform (CSPM). Allows security teams to trace production risks back to their exact source in code and incorporate code vulnerabilities into **Attack Path Analysis**. |

### SIEM & SOAR Concepts

| Concept / Technology | Description |
| :--- | :--- |
| **SIEM (Security Information and Event Management)** | Collects log data and security events across the entire digital estate (cloud, on-prem, apps). Aggregates, correlates events to spot anomalies, alerts analysts, groups alerts into incidents, and provides centralized visibility. |
| **SOAR (Security Orchestration, Automation, and Response)** | Takes alerts from a SIEM and other tools to execute action-driven automated workflows. **Orchestration** connects disparate security tools; **automation** executes repetitive tasks using **playbooks** (automated workflows built on Azure Logic Apps) to speed up threat containment. |
| **SIEM + SOAR Synergy** | SIEM provides the *visibility* to detect threats, while SOAR provides the *speed* to respond automatically, reducing alert fatigue, human error, and manual swivel-chair investigations. |
| **AI & Machine Learning in SIEM/SOAR** | Enhances detection via **anomaly detection**, **alert correlation/prioritization**, **false positive reduction**, **multi-stage attack tracking**, and **natural language assistance** (e.g., Security Copilot). |

### Microsoft Sentinel

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Microsoft Sentinel?** | A scalable, cloud-native SIEM and SOAR solution delivering AI-powered security analytics and threat intelligence across multicloud and multiplatform environments. |
| **Core Capabilities as a SIEM** | **Collects** data at cloud scale (350+ built-in connectors with normalization), **Detects** threats using analytics rules and AI, **Investigates** via AI-assisted tools, and **Responds** rapidly using built-in automation. |
| **Platform Components** | **Data Lake Tier** (cost-effective, long-term storage for up to 12 years alongside real-time analytics workspace), **Microsoft Sentinel Graph** (models complex asset/identity relationships), and **MCP Server** (natural language interface for AI agents and teams). |
| **Threat Detection Approaches** | **Rule-based detection** (pattern matching against signatures via Content hub templates), **AI & Machine Learning** (behavioral baselines and **Fusion** correlation engine for multistage attacks), and **Threat Intelligence matching** (indicators mapped to the **MITRE ATT&CK framework**). |
| **Investigation & Hunting** | Groups related alerts into **incidents** for triage/investigation. Supports proactive **threat hunting** with custom queries that can be promoted into analytics rules. |
| **Response & Mitigation** | **Automation rules** centrally manage incident handling under specific conditions, triggering **Playbooks** (automated workflows built on Azure Logic Apps) to execute remediation actions like disabling compromised accounts. |

### Microsoft Sentinel & Security Copilot Integration

| Feature / Aspect | Description |
| :--- | :--- |
| **Integration Overview** | Brings AI-assisted capabilities into security operations via two experiences: the **embedded experience in the Microsoft Defender portal** (unified with Defender XDR) and the **standalone Security Copilot experience** (chat-based via plugins). |
| **Portal Capabilities** | **Incident summarization** (auto-generated narrative of timeline, entities, IoCs), **Guided responses** (triage, containment, investigation, remediation suggestions), **Script & File analysis** (plain-language explanation of obfuscated scripts and file attributes), **Identity & Device summaries** (quick posture and risk checks), and **Incident report generation** (structured export). |
| **Natural Language to KQL** | Allows analysts to describe what they are looking for in plain language, and Security Copilot automatically generates a ready-to-run KQL query for threat hunting. |
| **Threat Intelligence & AI Agents** | Consolidates threat intelligence based on organization exposure; includes autonomous agents like the **Security Alert Triage Agent** (verdicts for false positives/real attacks) and the **Dynamic Threat Detection Agent** (identifies gaps in rule-based detection). |

### Conditional Access

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Conditional Access?** | Microsoft's Zero Trust policy engine built into Microsoft Entra ID. Evaluates conditions (**if-then statements**) *after* first-factor authentication to grant, block, or limit access. |
| **Assignments (The "Who, What, Where, When")** | **Users** (all, specific, roles, guests, workload/agent identities), **Target resources** (cloud apps, user actions, Global Secure Access), **Network** (trusted locations, IP ranges, compliant networks), and **Conditions** (sign-in/user/insider risk, device platforms, client apps, device filters). |
| **Access Controls (The "Then")** | **Block access** or **Grant access** (require MFA, authentication strength, compliant device, hybrid join, approved client app, password change, terms of use) alongside **Session controls** (sign-in frequency, Defender for Cloud Apps integration). |
| **Authentication Strengths** | Specifies allowed method combinations: **Multifactor authentication strength** (all MFA methods), **Passwordless MFA strength** (authenticator, FIDO2, Windows Hello), and **Phishing-resistant MFA strength** (FIDO2, CBA, Windows Hello). |
| **Licensing** | Requires **Microsoft Entra ID P1 or P2** licenses (free tenants must use Security Defaults instead). |

### Global Secure Access (Security Service Edge - SSE)

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Global Secure Access?** | Microsoft's Cloud-native Security Service Edge (SSE) solution combining network, identity, and endpoint access controls to secure access to any app or resource, replacing legacy VPNs with Zero Trust principles. |
| **Core Components** | **Microsoft Entra Internet Access** (Secure Web Gateway for SaaS/web traffic), **Internet Access for Microsoft Services** (optimized connectivity and source IP restoration for M365), and **Microsoft Entra Private Access** (ZTNA providing per-app access to private corporate resources). |
| **Internet Access Features** | Web content filtering, Universal Conditional Access, TLS inspection, threat intelligence, prompt injection protection, and Universal Continuous Access Evaluation (CAE). |
| **Private Access Features** | Replaces legacy VPNs with granular access via **Quick Access** (FQDN/IP groups) or **Per-app Access** (individual enterprise apps), supported by **App Discovery** to find unmanaged private resources. |
| **AI Workload Security** | Extends network controls to AI services via prompt injection protection, shadow AI discovery, and traffic policies applied to AI agent workloads. |

### Microsoft Entra Roles & Role-Based Access Control (RBAC)

| Concept / Role Type | Description |
| :--- | :--- |
| **Microsoft Entra RBAC** | Controls permissions to manage Microsoft Entra resources (users, groups, applications) as opposed to *Azure RBAC*, which controls Azure resources (VMs, storage). |
| **Built-in Roles** | Preconfigured, fixed sets of permissions that cannot be modified. Examples include **Global Administrator** (full access), **User Administrator** (manage users/groups/tickets), and **Billing Administrator** (purchases and subscriptions). |
| **Custom Roles** | User-defined collections of permissions created from a preset list and assigned at organization-wide or object scope (**requires Entra ID P1 or P2 licenses**). |
| **Principle of Least Privilege** | Best practice of granting users only the minimum permissions necessary to do their work, limiting the blast radius of compromised human or AI accounts. |
| **Categories of Roles** | **Entra-specific** (manage Entra resources only), **Service-specific** (manage M365 services like Exchange, Intune, SharePoint, Teams), and **Cross-service** (span multiple services, like Security Administrator or Compliance Administrator). |

### Microsoft Entra ID Governance

| Feature / Aspect | Description |
| :--- | :--- |
| **What is ID Governance?** | An identity governance solution that improves productivity, strengthens security, and meets compliance by ensuring the right people have the right access through automation, delegation, and visibility. |
| **Identity Lifecycle Management** | Governs the "join, move, and leave" process. Automates identity creation and maintenance via **inbound provisioning from HR sources**, **lifecycle workflows**, **automatic assignment policies**, and **user provisioning** to cloud/on-prem apps. |
| **Access Lifecycle Management** | Manages ongoing access needs using **dynamic groups** (attribute-based rules) and **entitlement management** (access packages, request workflows, and recurring **access reviews** with AI-powered suggestions). |
| **Privileged Access Lifecycle** | Uses **Microsoft Entra Privileged Identity Management (PIM)** to minimize and control administrative rights, providing time-bound, approval-based Just-In-Time access. |
| **Identity Governance for AI Agents** | Extends governance controls to AI agent identities (**Microsoft Entra Agent ID**), requiring an accountable **human sponsor** whose oversight automatically transfers to their manager if they leave. |

### Microsoft Entra Access Reviews

| Feature / Aspect | Description |
| :--- | :--- |
| **What are Access Reviews?** | Tools to efficiently manage group memberships, enterprise app access, and role assignments, ensuring that only the right people maintain access and mitigating excessive privilege risks. |
| **Key Use Cases** | Auditing privileged roles (recertifying admin users/guests), securing business-critical data access, maintaining policy exception lists, having group owners recertify guest access, and setting up **recurring reviews** (weekly, monthly, quarterly, annually). |
| **Workflow & Application** | Reviewers (users or decision-makers) approve or deny access based on Microsoft Entra ID suggestions. Changes can be **manually or auto-applied** when the review finishes (except for dynamic or on-premises groups). |
| **Multi-stage Access Reviews** | Supports up to three review stages to handle complex workflows requiring multiple reviewers to attest to access in a specific sequence. |
| **AI-Powered Recommendations** | Uses contextual data, sign-in activity, and peer affiliation to suggest approvals or denials, while flagging **peer outliers** whose access patterns differ from others. |

### Microsoft Entra Entitlement Management & Terms of Use

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Entitlement Management?** | An identity governance feature that automates access request workflows, assignments, reviews, and expiration to manage identity and access lifecycle at scale. |
| **Core Capabilities & Challenges Addressed** | Helps solve issues where users don't know who to ask for access, retain access too long, or struggle to manage complex external user access. Allows delegation of access package creation to non-administrators. |
| **External Users & AI Governance** | Automatically invites external users into the directory upon approval and removes their B2B account when access expires without other assignments. Also governs access for both **human and AI agent identities** via human sponsors. |
| **Access Packages** | Bundles of resources (security groups, M365 groups, enterprise apps, SharePoint sites) that users need for a project, managed through policies defining who can request them, who approves them, and expiration rules. |
| **Microsoft Entra Terms of Use** | Presents legal/compliance disclaimers (in PDF format) to users before they access sensitive data or apps. Enforced using **Conditional Access policies** to ensure users agree before entry, allowing admins to track acceptances and declines. |

### Microsoft Entra Privileged Identity Management (PIM)

| Feature / Aspect | Description |
| :--- | :--- |
| **What is PIM?** | A service in Microsoft Entra ID used to manage, control, and monitor access to critical resources across Entra ID, Azure, and M365 services, mitigating risks of excessive or misused permissions. |
| **Core Principles** | **Just-in-time** (access only when needed), **Time-bound** (start/end dates), **Approval-based** (requires specific approvals), **Visible** (notifications on activation), and **Auditable** (full access history download). |
| **Supported Scope / Targets** | **Microsoft Entra roles** (directory/M365 roles), **Azure roles** (management groups, subscriptions, resource groups), and **PIM for Groups** (just-in-time membership/ownership for groups controlling app, SQL, or Key Vault access). |
| **Basic Workflow** | **Assign** (eligible vs. active assignments, scope, duration), **Activate** (users request activation with a duration and reason), **Approve/Deny** (delegated approvers review requests), and **Extend/Renew** (request extensions or renewals for expiring/expired assignments). |
| **Audit Capabilities** | Allows administrators to view all role assignments and activations from the past 30 days for all privileged roles. |

### Microsoft Entra ID Protection

| Feature / Aspect | Description |
| :--- | :--- |
| **What is ID Protection?** | A tool that helps organizations detect, investigate, and remediate identity-based risks for both user identities and workload identities using trillions of daily signals. |
| **Risk Types & Detections** | Evaluates **sign-in risk** (probability that an auth request isn't authorized, e.g., anonymous IPs or atypical travel) and **user risk** (probability that an account is compromised, e.g., leaked credentials). Detections only trigger when *correct* credentials are used. |
| **Investigation Reports** | Provides three key reports for admins: **Risk detections** (individual detected risks), **Risky sign-ins** (sign-ins tied to risk detections), and **Risky users** (users flagged by risky sign-ins or risk detections). |
| **Remediation** | Can be automated via **risk-based Conditional Access policies** (requiring MFA or secure password resets, which auto-remediate the risk upon success) or handled manually by admins (dismissing, confirming safe, or confirming compromise). |
| **Export Capabilities** | Data can be exported via Microsoft Graph APIs to SIEM tools, sent to Log Analytics workspaces, archived to storage accounts, or streamed to Event Hubs. |

### Microsoft Defender XDR Services

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Microsoft Defender XDR?** | A unified pre- and post-breach enterprise defense suite that natively coordinates detection, prevention, investigation, and response across endpoints, identities, email, and applications. |
| **Included Solutions** | **Defender for Endpoint** (device protection/EDR), **Defender Vulnerability Management** (continuous asset visibility/risk assessment), **Defender for Office 365** (email/collaboration threat protection), **Defender for Identity** (hybrid identity monitoring), **Entra ID Protection** (cloud identity risk protection), **Defender for Cloud Apps** (CASB / shadow IT control), **Defender Threat Intelligence (Defender TI)**, and **Security Exposure Management** (unified posture/attack surface view). |
| **Cross-Product Capabilities** | **Combined incidents queue** (automatically groups related alerts into a single incident), **Automatic response** (shares threat info across products instantly), **Self-healing** (AI-powered remediation for compromised assets), **Automatic attack disruption** (contains active attacks in real time), and **Cross-product threat hunting** (30 days of raw historical data across products). |
| **Microsoft Defender Portal** | Centralized platform combining data from the XDR suite, Microsoft Sentinel, and Defender for Cloud into a single operations experience. |
| **Security Copilot Integration** | Provides natural language incident summaries, AI-guided responses, script/file analysis, and automated threat-hunting queries, available both standalone and embedded. |

### Microsoft Defender for Office 365

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Defender for Office 365?** | A cloud-based email and collaboration security service providing protection against phishing, malware, and threats arriving via email links, attachments, or collaboration tools (SharePoint, Teams, Outlook). Available in **Plan 1 and Plan 2**. |
| **Prevent and Detect** | Features include anti-malware, anti-spam, anti-phishing (spoofing), connection filtering, quarantine policies, **Safe Attachments** (detonation in a virtual environment), **Safe Links** (blocking malicious URLs), and **Attack simulation training** for user resilience. |
| **Investigate** | Includes **Message trace** (tracking message flow), **Explorer / Real-time detections** (near real-time SecOps investigation), **URL trace**, **Threat trackers**, and the **Campaigns** feature to identify coordinated email attacks. |
| **Respond** | Includes **Zero-hour auto purge (ZAP)** to retroactively neutralize delivered malicious mail, and **Automated investigation and response (AIR)** capabilities. |
| **Microsoft Defender Portal Integration** | Managed via the Microsoft Defender portal under the *Email & collaboration* node (covering investigations, review/quarantine, campaigns, trace, and policies). |
| **Security Copilot Integration** | Integrates with Microsoft Security Copilot for incident summarization, guided responses, and features the autonomous **Phishing Triage Agent** (requires Plan 2 and Security Copilot) to automatically classify user-reported phishing submissions. |

### Microsoft Defender for Endpoint

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Defender for Endpoint?** | A platform designed to help enterprise networks protect endpoints (laptops, phones, tablets, PCs, access points, routers, and firewalls) by preventing, detecting, investigating, and responding to advanced threats. |
| **Core Technologies** | Uses **endpoint behavioral sensors** embedded in the OS, **cloud security analytics** to translate signals into insights, and **threat intelligence** to identify attacker tools and techniques. |
| **Key Capabilities** | Includes **Core Vulnerability Management**, **Attack surface reduction** (network and web protection), **Next generation protection** (behavior-based antivirus, cloud-delivered protection), **Endpoint detection and response (EDR)**, **Automated investigation and remediation (AIR)**, **Microsoft Secure Score for Devices**, and **Microsoft Defender Experts for Hunting**. |
| **Management & Portal Integration** | Available in **Plan 1 and Plan 2**. Managed through the **Microsoft Defender portal** under the *Endpoints* node, covering vulnerability management, partners/APIs (Connected apps and API Explorer), and configuration management. |
| **Security Copilot Integration** | Integrates with Microsoft Security Copilot to summarize device security posture, investigate alerts faster, and generate threat-hunting queries using natural language. |

### Microsoft Defender for Cloud Apps

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Defender for Cloud Apps?** | A comprehensive cross-SaaS solution and Cloud Access Security Broker (CASB) that delivers full protection for SaaS applications, monitoring and protecting cloud app data across discovery, SSPM, advanced threat protection, and app-to-app protection. |
| **Discover SaaS Applications** | Identifies SaaS apps used across the organization using network traffic assessment and an app catalog. Evaluates apps against 90+ risk indicators (Assess) and monitors usage with automated alert policies (Manage). |
| **Information Protection** | Connects to SaaS apps to scan files containing sensitive data. Integrates with Microsoft Purview for data classification and data loss prevention (DLP) features, allowing actions like applying sensitivity labels, blocking downloads to unmanaged devices, or removing external collaborators. |
| **SaaS Security Posture Management (SSPM)** | Surfaces misconfigurations and recommends specific actions to strengthen security posture based on industry standards (like CIS) and provider best practices, automatically feeding data into Microsoft Secure Score. |
| **Advanced Threat Protection** | Offers adaptive access control (AAC), user and entity behavior analysis (UEBA), and integrates directly into Microsoft Defender XDR to provide full kill chain visibility and response capabilities. |
| **App-to-App Protection (App Governance)** | Protects inter-app data exchange for OAuth-enabled apps. Closes security gaps by monitoring unused apps, credentials, and permissions, preventing misuse of third-party service access. |
| **AI Agent Protection** | Monitors custom AI agents built with Microsoft Copilot Studio for risks like prompt injection or unauthorized tool execution, collecting audit logs, providing real-time protection, and integrating alerts into Microsoft Defender XDR. |
| **Portal Integration** | Managed via the **Microsoft Defender portal** under the *Cloud apps* node, featuring tools like Cloud discovery, Cloud app catalog, App governance, Activity logs, Governance logs, and Policies. |

### Microsoft Defender for Identity

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Defender for Identity?** | A cloud-based security solution that uses signals from identity infrastructure to detect threats (like privilege escalation or lateral movement) and report on easily exploited identity issues in hybrid environments. |
| **How it Works** | Uses software-based sensors installed on on-premises identity infrastructure servers (domain controllers, AD FS, AD CS). Sensors parse event logs and network traffic and send them to the Defender for Identity cloud service to deliver an ITDR solution. |
| **Core Capabilities** | **Prevent breaches** (proactively assessing posture via Secure Score), **Detect threats** (real-time analytics across the kill-chain: reconnaissance, compromised credentials, lateral movements, domain dominance), **Investigate** (attack timeline view reducing noise), and **Respond** (remediation actions like disabling users or resetting passwords on-prem). |
| **Portal Integration** | Managed via the **Microsoft Defender portal** under the *Identities* node, providing a Dashboard with critical insights, a Health issues page for sensors/deployment monitoring, and a Tools page with deployment scripts and PowerShell modules. |

### Microsoft Defender Vulnerability Management

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Defender Vulnerability Management?** | A comprehensive, risk-based solution that provides continuous asset visibility, intelligent assessments, and built-in remediation tools to identify, assess, remediate, and track vulnerabilities across critical assets (Windows, macOS, Linux, Android, iOS, and network devices). |
| **Core Capabilities** | **Continuous asset discovery and monitoring** (agentless scanners, inventories for software, certificates, hardware/firmware, and browser extensions; baseline assessments against CIS/STIG benchmarks), **Risk-based intelligent prioritization** (focuses on emerging threats, active breaches via EDR correlation, and high-value assets), and **Remediation and tracking** (Intune task creation, blocking vulnerable applications, alternate mitigations, and real-time tracking). |
| **Portal Integration** | Accessed through the **Microsoft Defender portal** under *Exposure management > Vulnerability management*. Features include **Overview** (exposure score and Secure Score for Devices), **Vulnerabilities** (CVE lists and CVSS ratings), **Inventories**, **Remediation**, and **Baseline assessments**. |
| **Security Copilot Integration** | Provides AI-powered assistance for vulnerability management workflows, including AI-generated summaries of recommendations, risk context explanations, step-by-step remediation guidance, and task delegation. |

### Microsoft Defender Threat Intelligence

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Defender TI?** | A threat analysis and intelligence platform designed to help security analysts streamline triage, incident response, threat hunting, vulnerability management, and threat infrastructure analysis by aggregating and enriching critical data sources into a single interface. *Note: The standalone product is retiring August 1, 2026, with capabilities converging into Microsoft Defender XDR and Microsoft Sentinel.* |
| **Core Threat Intelligence Capabilities** | Includes **Threat analytics** (reports categorized by latest threats, high-impact threats, and highest exposure), **Intel profiles** (Microsoft's curated repository on threat actors, tools, and vulnerabilities), **Intel explorer** (allows searching articles, keywords, and CVE IDs with priority scores), and **Projects** (organizes indicators of interest and IOCs from investigations). |
| **Portal Integration** | Accessed through the *Threat intelligence* node on the navigation panel of the **Microsoft Defender portal**. |
| **Security Copilot Integration** | Integrates via the Defender TI plugin to deliver info on threat activity groups, IOCs, and tools using prompts and built-in promptbooks (*Vulnerability impact assessment* and *Threat actor profile*). Also features the autonomous **Threat Intelligence Briefing Agent** to deliver regular, customized threat briefings. |

### Microsoft Security Exposure Management

| Feature / Aspect | Description |
| :--- | :--- |
| **What is Security Exposure Management?** | A security solution in the Microsoft Defender portal providing a unified view of security posture across organization assets and workloads by aggregating signals from Microsoft Defender tools, Entra ID, and non-Microsoft solutions. |
| **Attack Surface Management** | Built around the **enterprise exposure graph** (mapping assets, users, and workloads across on-prem, hybrid, and multicloud environments) and the **attack surface map** (visualizing risks and cross-environment connections). |
| **Attack Paths & Choke Points** | Automatically generates multi-step **attack paths** showing how attackers can chain vulnerabilities from an entry point to a critical asset. Highlights **choke points** (nodes where multiple attack paths converge) to disrupt multiple routes at once. |
| **Critical Asset Management** | Identifies, classifies, and prioritizes high-value targets (such as domain controllers, sensitive databases, or power user roles) using predefined or custom classifications based on criteria like resource tags or naming conventions. |
| **Exposure Insights & Initiatives** | Groups related metrics and recommendations into **security initiatives** (workload initiatives, horizontal threat initiatives, threat analytics initiatives, and Zero Trust initiatives) to track security posture and score changes over time. |
| **Integration with Secure Score & Data Connectors** | Consolidates Microsoft Secure Score and Cloud Secure Score data side by side. Integrates external data sources via **data connectors** (such as ServiceNow CMDB, Tenable, Qualys, and Rapid7). |

### Microsoft Defender portal

| Feature / Aspect | Description |
| :--- | :--- |
| **What is the Defender portal?** | A unified security operations platform that combines protection, detection, investigation, and response across the entire organization into a central place, integrating SIEM, XDR, posture management, and threat intelligence. |
| **Access & Customization** | Requires appropriate roles assigned in Microsoft Entra ID (such as Security Administrator/Reader or Global Administrator/Reader). The left navigation pane and home page cards can be customized per user based on operational preferences and roles. |
| **Key Navigation Nodes & Capabilities** | • **Defender Experts:** Managed XDR service overview and response messages.<br>• **Exposure management:** Unified posture, initiatives, attack surface maps, secure score, vulnerability management, and data connectors.<br>• **Investigation & response:** Combined incidents and alerts queue, advanced hunting (KQL/natural language via 30 days of raw data), Action center, submissions, and partner catalog.<br>• **Threat intelligence:** Access to Defender Threat Intelligence insights.<br>• **Assets:** Inventory for devices, identities, applications, cloud, and AI agents.<br>• **Workload Nodes:** Dedicated views for **Microsoft Sentinel**, **Identities** (Defender for Identity), **Endpoints** (Defender for Endpoint), **Email and collaboration** (Defender for Office 365), **Cloud apps** (Defender for Cloud Apps), and **Cloud security** (Defender for Cloud).<br>• **Security Copilot & SOC Optimization:** Management of AI agents, Security Store, and optimization recommendations.<br>• **Reports, Learning hub & System:** Dynamic security reports, Microsoft Learn links, and portal administration settings. |

### Microsoft Security Copilot & Defender XDR Integration

| Feature / Aspect | Description |
| :--- | :--- |
| **Integration Overview** | Combines generative AI with human expertise through both a **standalone experience** (via the Copilot portal using plugins) and an **embedded experience** (directly inside the Microsoft Defender XDR portal). |
| **Standalone Experience & Plugins** | Accessed via `securitycopilot.microsoft.com` using the **Microsoft Defender XDR plugin** (for file analysis, incident reports, guided responses, and summaries) and the **Natural language to KQL plugin** (converting plain-language questions into ready-to-run threat hunting queries). Includes a built-in **promptbook** for incident investigations. |
| **Embedded Experience Capabilities** | Built directly into the Defender XDR portal to support **Summarize incidents** (auto-generating attack overviews up to 100 alerts), **Guided responses** (AI-driven triage, containment, investigation, and remediation recommendations), **Script analysis** (inspecting code/PowerShell scripts safely), **Natural language to KQL**, **Create incident reports**, **Analyze files**, and **Summarize devices and identities**. Allows seamless pivoting to the standalone portal. |
| **Autonomous AI Agents** | Includes specialized agents that operate within the portal:<br>• **Phishing Triage Agent:** Automatically reviews and classifies user-submitted phishing emails (requires Office 365 Plan 2).<br>• **Threat Intelligence Briefing Agent:** Gathers and delivers customized, actionable threat briefings.<br>• **Threat Hunting Assistant:** Guides analysts through end-to-end hunting sessions using natural language to build KQL queries and interpret results.<br>• **Dynamic Threat Detection Agent:** Always-on backend service using AI to uncover hidden threats and reduce false negatives without requiring setup. |

## Microsoft Purview & Compliance Solutions

### Microsoft Service Trust Portal (STP)

| Concept / Area | Description |
| :--- | :--- |
| **What is the Service Trust Portal?** | Microsoft's public website for publishing audit reports, independent third-party audit reports, and whitepapers showing how Microsoft cloud services protect data and meet compliance standards. |
| **Access** | Requires logging in as an authenticated user with a Microsoft cloud services account (Entra organizational account) to access certain resources. |
| **1. Certifications, Regulations, and Standards** | Contains security implementation and design information designed to make it easier to meet regulatory compliance goals (e.g., ISO/IEC reports). |
| **2. Reports, Whitepapers, and Artifacts** | General documents categorized into: **BCP & DR** (Business Continuity and Disaster Recovery), **Penetration Tests and Security Assessments**, **Privacy and Data Protection**, and **FAQs & Whitepapers**. |
| **3. Industry and Regional Resources** | Tailored to specific sectors and regions: **Financial Services (FSI)**, **Healthcare and Life Sciences**, **Media and Entertainment**, **US Government**, and **Regional Resources** (compliance with local policies and regulations). |
| **4. Resources for Your Organization** | Displays documents specific to your organization based on your tenant, subscriptions, and permissions. |
| **My Library & Notifications** | Allows you to save relevant documents in one place by clicking the ellipsis menu (`...`). Can be configured to send **email notifications** whenever Microsoft updates your saved documents or series. |

### Microsoft Data Protection & Privacy Principles

| Area / Principle | Description |
| :--- | :--- |
| **1. You Control Your Data (Data Control)** | • Your data belongs to you; you can access, modify, or delete it at any time.<br>• Microsoft does **not** use your data for advertising, market research, or anything other than providing your chosen services without your explicit consent.<br>• Subprocessors and vendors are bound by the same strict contractual privacy obligations and are pre-audited.<br>• Complies with standards like **ISO/IEC 27018** (the world's first international code of practice for cloud privacy). |
| **2. Know Where Your Data Is Located (Data Location)** | • Enables you to select services and geographical data residency across Azure, Dynamics 365, and Microsoft 365.<br>• Meets local data residency and compliance requirements within specific geographic boundaries, backed by contractual guarantees. |
| **3. Your Data Is Secured at Rest and in Transit (Data Security)** | • **Data at Rest:** Protected using advanced encryption options up to **AES-256**.<br>• **Data in Transit:** Uses industry-standard secure transport protocols such as **TLS** and **IPsec** with two or more independent encryption layers.<br>• **Key Management:** Microsoft-managed keys are properly secured, and customers retain control over keys and secrets using **Azure Key Vault**. |
| **4. Microsoft Defends Your Data (Data Protection)** | • Government and law enforcement requests for customer data must generally be directed to the customer—Microsoft **never** provides governments with direct or unvetted access.<br>• Microsoft reviews all requests for legal validity, notifies the customer (where legally permitted), and will, when necessary, **challenge unlawful government demands in court**. |

### Microsoft Purview Data Security Solutions — Overview

| Concept / Element | Description |
| :--- | :--- |
| **What is Microsoft Purview?** | A comprehensive set of integrated data security, data governance, and data compliance solutions that help organizations secure and govern their entire data estate while meeting compliance requirements. |
| **Core Data Security Pillars** | • **Information Protection:** Data classification and sensitivity labeling.<br>• **Data Loss Prevention (DLP):** Prevents the inappropriate sharing of sensitive data.<br>• **Insider Risk Management:** Minimizes internal risks and threats. |
| **Adaptive Protection** | Brings these solutions together to automatically apply the right level of controls based on each user's current risk level. |
| **Data Security Posture Management (DSPM)** | Provides a unified view of the organization's data security landscape across Microsoft and non-Microsoft environments, including visibility into AI interactions. |
| **Data Security Investigations** | Generative AI-powered tools for security teams to quickly investigate data breaches and insider leaks and take action to mitigate damage. |

### Microsoft Purview Information Protection — Data Classification

| Concept / Element | Description |
| :--- | :--- |
| **Sensitive Information Types (SITs)** | • **Pattern-based classifiers** that detect sensitive information (such as social security numbers, credit card numbers, or bank account numbers).<br>• Consist of a **Primary element** (the core pattern or regex), **Supporting elements** (corroborating evidence nearby), **Confidence level** (low, medium, high), and **Proximity** (character distance between elements).<br>• **Four categories:** Built-in SITs, Named Entity SITs (names, addresses, medical terms), Custom SITs, and Exact Data Match (EDM) SITs. |
| **Trainable Classifiers (AI / ML)** | • Uses artificial intelligence and machine learning to classify data based on *what the content is* (e.g., specific contracts, invoices) rather than rigid patterns.<br>• **Pre-trained classifiers:** Ready to use out-of-the-box (e.g., behavioral signals like harassment/profanity, financial documents, HR/resumes, legal content).<br>• **Custom trainable classifiers:** Trained by the organization by seeding sample sets and iteratively verifying true/false positives.<br>*(Note: Classifiers only work on unencrypted items).* |
| **Data Classification & AI Interactions** | SITs and trainable classifiers scan user prompts and responses during interactions with AI applications like **Microsoft 365 Copilot**, capturing sensitive data flows within AI chats. |
| **Content Explorer** | Provides administrators with a visual snapshot and drill-down view of where sensitive data is stored across Exchange, SharePoint, and OneDrive, including applied labels or SITs. *(Access is highly restricted due to permission to read file contents).* |
| **Activity Explorer** | Monitors what users actually do with labeled content, tracking document-level activities such as label modifications, downgrades, copying files to removable media, and printing via Endpoint DLP. |

### Microsoft Purview Information Protection — Sensitivity Labels & Policies

| Concept / Element | Description |
| :--- | :--- |
| **Sensitivity Labels** | • **Customizable, clear-text, and persistent** markers applied to content that travel with it wherever it goes (stored in metadata).<br>• Each supported item can only have **one label** applied at a time.<br>• **Capabilities:** Encrypt emails/documents, apply visual markings (watermarks on docs/Loop, headers/footers), trigger auto-labeling/recommendations, protect containers (Teams, SharePoint sites), set default sharing link scopes, and extend labeling via the MIP SDK. |
| **Label Scopes** | Defines what content types a label applies to:<br>• **Files & other data assets:** Word, Excel, PowerPoint, PDF, Fabric, Power BI.<br>• **Emails:** Outlook emails.<br>• **Meetings:** Calendar events, Teams meetings, and chat (requires Files & Emails scopes).<br>• **Groups & sites:** SharePoint sites, Teams, M365 groups (protects the container by controlling access rather than stamping individual files). |
| **Copilot Integration** | **Microsoft 365 Copilot** recognizes and honors sensitivity labels, inheriting the most restrictive label when combining data and verifying user encryption permissions before referencing content in AI responses. |
| **Sensitivity Label Policies** | Used to publish labels to users and groups in Microsoft Entra ID. Enables administrators to:<br>• Target specific users/groups.<br>• Set a **default label** for new documents/emails.<br>• Require **justification** for lowering or removing a label.<br>• Enforce **mandatory labeling** before saving/sending.<br>• Link users to custom organizational help pages. |

### Microsoft Purview Data Loss Prevention (DLP)

| Concept / Element | Description |
| :--- | :--- |
| **What is DLP?** | A solution designed to identify, monitor, and automatically protect sensitive items against accidental sharing and risky behavior across your digital estate. |
| **Coverage & Locations** | Protects data across M365 services (Exchange, SharePoint, OneDrive, Teams), Office apps, **endpoints** (Windows 10/11, macOS), non-Microsoft cloud apps, on-premises file shares, Microsoft Fabric/Power BI, and Microsoft Edge for Business. |
| **Detection Methods** | Uses deep content analysis—combining primary keyword matches, regular expressions, internal function validation, proximity rules, and machine learning—rather than simple text scans. |
| **Protective Actions** | • Display **policy tips** warning the user.<br>• Block sharing with an option for the user to override and enter a business justification.<br>• Block sharing **without** an override option.<br>• Lock and move data at rest to a secure quarantine location.<br>• Hide sensitive information directly within Teams chat messages. |
| **Endpoint DLP** | Audits and manages user actions on physical Windows 10/11 and macOS devices, such as copying files to removable media (USB) or network shares, printing documents, or accessing files with unallowed apps/browsers. |
| **DLP & AI Interactions** | Prevents sensitive data leaks into third-party generative AI apps (e.g., pasting credit card numbers into ChatGPT in a browser) through Endpoint DLP policies that warn or block the action. |
| **Security Copilot Integration** | Supports embedded alert summarization and the autonomous **Alert Triage Agent**, which evaluates, categorizes, and prioritizes DLP alerts based on content, exfiltration, and policy risk. |

### Microsoft Purview Insider Risk Management

| Concept / Element | Description |
| :--- | :--- |
| **What is Insider Risk Management?** | A compliance solution that minimizes internal risks (such as IP theft, data spillage, fraud, insider trading, and confidentiality violations) by detecting, investigating, and acting on risky employee activities while balancing user privacy. |
| **Core Principles** | **Transparency** (privacy-by-design architecture), **Configurable** (tailored by industry, region, and business group), **Integrated** (works across Microsoft Purview solutions), and **Actionable** (supports reviewer notifications and investigations). |
| **Insider Risk Analytics** | Evaluates potential insider risks across the organization *before* configuring any policies, helping admins identify high-risk areas and determine which policy templates to enable. |
| **5-Stage Workflow** | 1. **Policies:** Created from predefined templates defining risk indicators, user scope, and monitoring periods.<br>2. **Alerts:** Automatically generated in the dashboard when activity matches policy conditions.<br>3. **Triage:** Reviewers evaluate "Needs review" alerts to open a new case, add to an existing case, or dismiss.<br>4. **Investigate:** Cases combine an interactive **User activity** chart, **Content explorer** (captured files/emails), **Case notes**, and the Sentinel-powered **Data risk graph** (mapping connections between users, devices, and data flows).<br>5. **Action:** Resolve cases by sending policy reminder notifications, escalating to **Microsoft Purview eDiscovery (Premium)**, or exporting alert data. |
| **Common Risk Scenarios** | • **Data theft by departing users** (HR connector signals combined with large downloads/external emails).<br>• **Intentional/unintentional data leaks** & **Security policy violations** (signals from Defender for Endpoint).<br>• **Risky AI usage & Risky agents** (detecting prompt injection, sensitive data sent to unapproved AI services, or misconfigured/compromised AI agents).<br>• **Priority users** (heightened monitoring for executives/admins), **Healthcare** (patient data misuse), **Risky user behavior** (HR stressor events), and **Forensic evidence** (screen captures). |
| **Security Copilot Integration** | Supports standalone prompts, embedded **alert summarization**, and the autonomous **Triage Agent**, which evaluates alerts based on user, file, and activity risk to categorize and prioritize high-risk queues. |

### Microsoft Purview Adaptive Protection

| Concept / Element | Description |
| :--- | :--- |
| **What is Adaptive Protection?** | Uses machine learning (ML) to dynamically adjust protective controls based on each user's current insider risk level—enforcing strict blocks on risky users while keeping low-risk users productive without manual admin intervention. |
| **Core Mitigation Mechanisms** | • **Context-aware detection:** ML-driven analysis of content and user activities.<br>• **Dynamic controls:** Automatically tightens or relaxes enforcement as user risk shifts.<br>• **Automated mitigation:** Reduces admin overhead and limits incident impact. |
| **Insider Risk Levels** | Calculated continuously by Insider Risk Management:<br>• **Elevated risk level:** High-severity alerts or multiple high-severity activity sequences; triggers the strongest controls.<br>• **Moderate risk level:** Medium-severity alerts or multiple high-severity exfiltration activities; balances security with productivity.<br>• **Minor risk level:** Low-severity alerts or at least one high-severity exfiltration activity; applies light educational reminders. |
| **1. Data Loss Prevention (DLP)** | Dynamically assigns DLP actions based on risk: **Minor** displays educational policy tips, **Moderate** warns and requires justification to share/export, and **Elevated** strictly blocks saving or sharing sensitive data externally. |
| **2. Data Lifecycle Management** | When a user reaches the **Elevated risk level**, a retention label policy automatically preserves any content they delete from SharePoint, OneDrive, or Exchange Online for **120 days** to prevent evidence destruction. |
| **3. Conditional Access** | Integrates with Microsoft Entra Conditional Access to restrict app access by risk level: **Minor** may require accepting Terms of Use, **Moderate** can block high-sensitivity apps, and **Elevated** can completely block organizational app access until resolved. |

### Microsoft Purview Data Security Posture Management (DSPM)

| Concept / Element | Description |
| :--- | :--- |
| **What is DSPM?** | A centralized data-centric security solution in Microsoft Purview that consolidates insights from Information Protection, DLP, Insider Risk Management, and Data Security Investigations into a unified view to discover, protect, and investigate sensitive data risks across your digital estate. |
| **Four Core Questions Answered** | 1. **What** data do we have?<br>2. **Where** is it stored?<br>3. **Who** can access it?<br>4. **How** is it protected? |
| **Data Security Objectives** | Outcome-focused workflows presented as selectable cards (e.g., *Prevent data exposure in Copilot*, *Prevent oversharing*, *Prevent exfiltration to risky locations*, *Discover sensitive data*) featuring prioritized actions, impact prediction visuals, and **one-click policies**. |
| **Multicloud & Non-Microsoft Visibility** | Extends coverage across Microsoft 365, Azure, Fabric, and non-Microsoft SaaS/IaaS platforms (such as GCP, Snowflake, Databricks) via partner integrations (Cyera, BigID, OneTrust) and a Microsoft Sentinel data lake to uncover **shadow data**. |
| **AI Observability** | Monitors generative AI apps and agents (Microsoft 365 Copilot, Copilot Studio, third-party AI) over a 30-day inventory, tracking agent-specific oversharing, exfiltration, and unusual access patterns while recommending governance policies. |
| **AI-Assisted Security & Triage** | Integrates with **Microsoft Security Copilot** and AI triage agents to filter alert noise, analyze sharing behaviors, and execute human-approved automated remediations (such as removing public sharing links or revoking permissions). |
| **Key Portal Pages** | • **Posture:** Main dashboard with Security Copilot prompts, posture metrics, and 30-day trends.<br>• **Objectives:** Actionable remediation plans with one-click policies.<br>• **AI observability:** Inventory, risk ratings, and governing policies for AI apps/agents.<br>• **Asset explorer:** Unified view of labeled/unlabeled data across workloads to detect shadow data.<br>• **Reports:** Customizable dashboards for sensitive data usage, labeling, and risky behavior. |

### Microsoft Purview Governance, Compliance & Investigations

| Solution / Capability | Description & Exam Key Points |
| :--- | :--- |
| **Data Security Investigations** | Generative AI-powered investigation tool that helps security teams rapidly investigate data breaches, data spillage, and insider leaks across Microsoft 365, analyze impacted content, and execute containment/mitigation actions. |
| **Microsoft Purview Compliance Manager** | Translates complex regulatory requirements (GDPR, ISO 27001, NIST, HIPAA) into measurable **improvement actions** and calculates an overall **Compliance Score**—explicitly separating **Microsoft-managed actions** from **your organization's actions**. |
| **Data Lifecycle & Records Management** | • **Retention Policies:** Applied at the container/location level (Exchange, SharePoint, OneDrive, Teams) to keep or delete data after a set period.<br>• **Retention Labels:** Applied at the item level (individual emails/files) and travel with the content; support **disposition reviews** and declaring items as immutable **Records** for regulatory/legal compliance. |
| **Microsoft Purview eDiscovery** | Helps organizations locate, preserve, and export electronic data for legal cases and investigations:<br>• **eDiscovery (Standard):** Basic search, hold (preserving data from deletion), and export capabilities.<br>• **eDiscovery (Premium):** Adds end-to-end case management, custodian workflows, legal hold notifications, advanced indexing, and review sets with predictive coding/analytics. |
| **Microsoft Purview Audit** | Captures and logs thousands of user and admin activities across Microsoft 365 services for forensic and compliance investigations:<br>• **Audit (Standard):** Default logging with **180-day** retention.<br>• **Audit (Premium):** Extends retention up to **1 year** (or **10 years** with an add-on license) and adds high-value forensic events (such as `MailItemsAccessed` and `SearchQueryInitiated`). |
| **Communication Compliance** | Helps minimize communication risks by detecting, capturing, and acting on inappropriate messages across Exchange, Teams, Viva Engage, and third-party channels (e.g., harassment, profanity, threats, or sharing confidential financial/insider info). |
