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
