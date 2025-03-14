# **STRIDE Threat Model - CareConnect360**

The **STRIDE threat model** helps identify potential security threats in **CareConnect360**, categorized into six key areas: **Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privilege**.

## **STRIDE Threat Analysis Table**
| **Threat**                | **Description** | **Potential Impact on CareConnect360** | **Mitigation Strategies** |
|---------------------------|----------------|--------------------------------------|---------------------------|
| **S - Spoofing** | Attacker impersonates a legitimate user or system | Unauthorized access to patient records, identity theft | Multi-Factor Authentication (MFA), strong password policies, OAuth2, JWT, and secure session management |
| **T - Tampering** | Unauthorized modification of data | Medical record manipulation, incorrect diagnoses | Input validation, digital signatures, database integrity checks, logging & monitoring |
| **R - Repudiation** | User denies performing an action, and no evidence exists | Malicious insider deletes logs to cover actions | Audit logging, SIEM (Security Information and Event Management), digital signatures |
| **I - Information Disclosure** | Unauthorized access to sensitive data | Data breaches, leaked patient records, regulatory non-compliance (HIPAA) | Data encryption (TLS, AES), Role-Based Access Control (RBAC), tokenization |
| **D - Denial of Service (DoS)** | Attacker disrupts system availability | Healthcare services unavailable, patient care delays | Rate limiting, Web Application Firewall (WAF), anomaly detection, CDN for traffic filtering |
| **E - Elevation of Privilege** | Attacker gains unauthorized higher privileges | Unauthorized database access, data deletion | Role-Based Access Control (RBAC), least privilege access, secure IAM configurations |

---

## **STRIDE Threat Model Diagram - CareConnect360**
```mermaid
flowchart TD;
    %% External Entities
    Patients["👤 Patients"] -->|Login, Schedule, View Records| Frontend["🌐 Web App"]
    HealthcareProviders["🏥 Providers"] -->|Manage Patients| Frontend
    ThirdParty["🔗 Third-Party APIs"] -->|API Requests| Backend["⚙️ Backend System"]

    %% System Components
    Frontend -->|REST API Calls| Backend
    Backend -->|Authenticate Users| Auth["🔐 Authentication"]
    Backend -->|Query, Store Data| Database["🗄️ Patient Database"]

    %% STRIDE Threat Mapping
    subgraph STRIDE_Threats["⚠️ STRIDE Threat Model"]
        Spoofing["🔓 Spoofing - Unauthorized Access"]
        Tampering["⚠️ Tampering - Data Modification"]
        Repudiation["📜 Repudiation - No Audit Trail"]
        InfoDisclosure["🔍 Information Disclosure - Data Breach"]
        DoS["⛔ Denial of Service - System Disruption"]
        PrivilegeEscalation["🚀 Elevation of Privilege - Unauthorized Admin Access"]
    end

    %% Mapping Threats to Components
    Auth -.->|Spoofing Risk| Spoofing
    Database -.->|Tampering Risk| Tampering
    Backend -.->|Repudiation Risk| Repudiation
    Database -.->|Information Disclosure Risk| InfoDisclosure
    Backend -.->|DoS Risk| DoS
    Auth -.->|Privilege Escalation Risk| PrivilegeEscalation
    M6([Mitigation: Access Controls]) --> T