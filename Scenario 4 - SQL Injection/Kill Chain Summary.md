## Kill Chain Attack Description: CareConnect360 SQL Injection Attack Scenario

## Stages of the Attack

### Origins
The attacker identifies CareConnect360 as a target due to its sensitive patient records and public-facing web application. The motivation could be: Financial gain (stealing patient data for resale). Espionage (accessing proprietary medical research). Destruction (manipulating or deleting medical records).

### Reconnaissance
The attacker gathers information on CareConnect360’s: Web application and API structure. Login forms, search fields, and input validation mechanisms. Database type (MariaDB, PostgreSQL, etc.) through error messages or responses.

### Weaponization
The attacker crafts SQL injection payloads based on the database type, including: Authentication Bypass → Injecting OR '1'='1' to bypass login security. Data Extraction → Using UNION-based SQL injection to dump patient records. Data Manipulation → Executing UPDATE and DELETE statements to modify or erase data. Privilege Escalation → Gaining admin-level access by modifying credentials.

### Delivery
The attacker injects SQL payloads into: Login fields to bypass authentication. Search bars or report queries to extract data. User input forms to manipulate or delete records.

### Exploitation
The SQL payload is executed, allowing the attacker to: Steal patient records, admin credentials, or financial data. Modify or delete medical information, disrupting healthcare services. Create new admin users to gain persistent access.

### Persistence
The attacker ensures continued access by: Creating hidden admin accounts. Deploying malware or backdoors via SQL commands. Disabling logging to evade detection.

### Actions on Objectives
After executing the attack, the attacker: Sells or leaks stolen data on the dark web. Modifies healthcare records to cause misdiagnoses. Deletes critical patient data, causing system downtime.

```mermaid
flowchart TD
    %% Define colors for different attack stages
    style Origins fill:#F4D03F,stroke:#000,stroke-width:2px
    style Reconnaissance fill:#F5B041,stroke:#000,stroke-width:2px
    style Weaponization fill:#EB984E,stroke:#000,stroke-width:2px
    style Delivery fill:#E59866,stroke:#000,stroke-width:2px
    style Exploitation fill:#DC7633,stroke:#000,stroke-width:2px
    style Persistence fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    %% Attack Sequence
    Origins[Origins] -->|Identify CareConnect360 as a target due to its sensitive data| Reconnaissance[Reconnaissance]
    Reconnaissance -->|Scan CareConnect360 for SQL Injection vulnerabilities| Weaponization[Weaponization]
    Weaponization -->|Craft SQL payloads to exploit input fields & API endpoints| Delivery[Delivery]
    Delivery -->|Inject malicious SQL queries in login forms, search fields, APIs| Exploitation[Exploitation]
    Exploitation -->|Execute SQL commands to extract, modify, or delete data| Persistence[Persistence]
    Persistence -->|Create hidden admin accounts, disable logs, or deploy malware| Actions_Objectives[Actions on Objectives]
    Actions_Objectives -->|Steal, manipulate, or destroy patient data| Actions_Objectives

    %% MITRE ATT&CK Techniques
    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    Reconnaissance -->|T1595 - Active Scanning| MITRE
    Weaponization -->|T1190 - Exploit Public-Facing Application| MITRE
    Delivery -->|T1059.003 - Command and Scripting Interpreter| MITRE
    Exploitation -->|T1041 - Exfiltration Over C2 Channel| MITRE
    Exploitation -->|T1565.001 - Data Manipulation| MITRE
    Persistence -->|T1136 - Create Account| MITRE
    Persistence -->|T1098 - Account Manipulation| MITRE
    Persistence -->|T1070 - Indicator Removal on Host| MITRE
    end