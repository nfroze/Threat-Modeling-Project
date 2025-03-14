# Kill Chain Attack Description: CareConnect360 Insider Attack Scenario

## Stages of the Attack

### Origins
The attack originates from a disgruntled employee, compromised staff member, or malicious insider with legitimate credentials and access to CareConnect360 systems. The motive could be: Financial gain (selling patient data on the dark web). Corporate espionage (leaking medical research to competitors). Personal revenge (sabotaging systems or deleting records) Collusion with external attackers (aiding ransomware or data theft operations).

### Reconnaissance
Since the insider already has access, they conduct passive reconnaissance by: Reviewing security policies to identify gaps.
Identifying unmonitored data repositories (medical records, financial info, admin tools).
Understanding logging & auditing processes to plan ways to evade detection.

### Weaponization
The insider prepares for the attack by: Identifying sensitive data (patient records, billing info, research data).
Creating or exploiting backdoors (modifying access permissions or creating unauthorized accounts).
Establishing exfiltration channels (USB drives, cloud storage, encrypted emails, personal email accounts).

### Delivery
Since the insider already has authorized system access, there’s no need to deliver malware externally. Instead, they: Download large datasets from internal servers onto personal devices. Modify or delete medical records to disrupt healthcare services. Install unauthorized software or scripts for long-term access.

### Exploitation
Exports patient records & financial data from CareConnect360 databases. Escalates privileges to access admin tools, deactivate logging, or disable alerts. Sabotages critical infrastructure (e.g., deleting research data or encrypting files).

### Installation (Persistence)
Creates new admin accounts to maintain access even after leaving the organization. Modifies system configurations to bypass security controls. Uses stolen credentials to access systems remotely from personal devices.

### Actions on Objectives
Once the attack is complete, the insider: Sells or leaks stolen data on the dark web. Destroys or alters patient records to disrupt operations. Covers their tracks by deleting logs & audit trails.

```mermaid
flowchart TD
    %% Define colors for different attack stages
    style Origins fill:#F4D03F,stroke:#000,stroke-width:2px
    style Reconnaissance fill:#F5B041,stroke:#000,stroke-width:2px
    style Weaponization fill:#EB984E,stroke:#000,stroke-width:2px
    style Delivery fill:#E59866,stroke:#000,stroke-width:2px
    style Exploitation fill:#DC7633,stroke:#000,stroke-width:2px
    style Persistence fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Impact fill:#BA4A00,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    %% Attack Sequence
    Origins[Origins] -->|Disgruntled employee or compromised insider targets CareConnect360| Reconnaissance[Reconnaissance]
    Reconnaissance -->|Gather intelligence on security policies, logging, and data access controls| Weaponization[Weaponization]
    Weaponization -->|Identify high-value patient data, research records, or financial info| Delivery[Delivery]
    Delivery -->|Use legitimate credentials to access and exfiltrate or manipulate data| Exploitation[Exploitation]
    Exploitation -->|Escalate privileges, disable logging, modify records, or steal sensitive data| Persistence[Persistence]
    Persistence -->|Create backdoor admin accounts, transfer data to external storage| Impact[Impact]
    Impact -->|Sell stolen data, delete records, disrupt healthcare services| Impact

    %% MITRE ATT&CK Techniques
    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    Reconnaissance -->|T1591 - Gather Victim Organization Information| MITRE
    Weaponization -->|T1078 - Valid Accounts| MITRE
    Delivery -->|T1078.003 - Local Accounts| MITRE
    Exploitation -->|T1134 - Access Token Manipulation| MITRE
    Persistence -->|T1136 - Create Account| MITRE
    Persistence -->|T1578 - Modify Cloud Compute Infrastructure| MITRE
    Impact -->|T1485 - Data Destruction| MITRE
    Impact -->|T1565.001 - Data Manipulation| MITRE
    Impact -->|T1048 - Exfiltration Over Alternative Protocol| MITRE
    end