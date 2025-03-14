# **Threat Modeling Workshop Summary**

## **Introduction**
A **3-hour threat modelling workshop** was conducted to analyze **potential AI-driven cyber attacks** against the **web-facing healthcare application** **Solaris Care Connect 360**.

## **Attendees**
The workshop was attended by representatives from:  
- **CareConnect Engineering Team**  
- **Product Managers**  
- **DevEx Engineers**  
- **DevSecOps Team**  

## **Scope**
The workshop covered **four key attack scenarios**:  
1. **Phishing Attack**  
2. **Ransomware Attack**  
3. **Insider Threat**  
4. **SQL Injection Attack**  

## **Methodology**
The threat modelling workshop utilized:  
- **Cyber Kill Chain** → To analyze each attack’s **lifecycle** 
- **MITRE ATT&CK Framework** → To identify **tactics, techniques, and procedures (TTPs)** for each attack
- **STRIDE Threat Model** → To **assess control gaps** and prioritize mitigations for Care Connect 360 as a whole  

The result was a **comprehensive risk assessment** of the Solaris Care Connect 360 Patient Management System.

```mermaid
flowchart TD;
    %% Define Colors for Better Readability
    style Workshop fill:#F4D03F,stroke:#000,stroke-width:2px
    style Attendees fill:#F5B041,stroke:#000,stroke-width:2px
    style Scope fill:#EB984E,stroke:#000,stroke-width:2px
    style Methodology fill:#E59866,stroke:#000,stroke-width:2px
    style Findings fill:#DC7633,stroke:#000,stroke-width:2px

    %% Main Flowchart Structure
    Workshop["🎯 Threat Modelling Workshop"] --> Attendees["👥 Attendees"]
    Workshop --> Scope["📌 Scope"]
    Workshop --> Methodology["🔬 Methodology"]
    Workshop --> Findings["⚠️ Risk Assessment Findings"]

    %% Attendees Breakdown
    Attendees --> EngTeam["🛠️ CareConnect Engineering Team"]
    Attendees --> ProductManagers["📊 Product Managers"]
    Attendees --> DevEx["⚡ DevEx Engineers"]
    Attendees --> DevSecOps["🔐 DevSecOps Team"]

    %% Scope Breakdown
    Scope --> Phishing["🎣 Phishing Attack"]
    Scope --> Ransomware["🛑 Ransomware Attack"]
    Scope --> Insider["🕵️ Insider Threat"]
    Scope --> SQLi["💻 SQL Injection Attack"]

    %% Methodology Breakdown
    Methodology --> KillChain["⚔️ Cyber Kill Chain"]
    Methodology --> MITRE["📌 MITRE ATT&CK"]
    Methodology --> STRIDE["🛡️ STRIDE Threat Model"]

    %% Findings Breakdown
    Findings --> Risks["🚨 4 High-Risk & 3 Medium-Risk Threats Identified"]
    Findings --> Mitigations["✅ Security Controls & Mitigation Plan"]
yaml
Copy
Edit
