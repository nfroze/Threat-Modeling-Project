# **Threat Modelling Workshop Summary**

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
- **MITRE ATT&CK Framework** → To identify **tactics, techniques, and procedures (TTPs)**  
- **STRIDE Threat Model** → To **assess control gaps** and prioritize mitigations  

The result was a **comprehensive risk assessment** of Solaris Care Connect 360.

## **Findings**
The workshop identified:  
- **4 High-Risk Threats**  
- **3 Medium-Risk Threats**  

## **Controls Required**
To mitigate the identified risks, the following security controls were recommended:  

### **Security Best Practices**
✔ **Regular Security Audits** → Routine **penetration testing and vulnerability scans** targeting Solaris CareConnect360.  
✔ **Patch Management** → Ensure timely updates of **underlying frameworks, dependencies, and OS security patches**.  
✔ **Comprehensive Employee Training** → Strengthen **phishing awareness** and **security best practices** among staff.  
✔ **Multi-Factor Authentication (MFA)** → Enforce **MFA for all user accounts**, reducing the risk of credential-based attacks.  

### **Technical Controls**
✔ **Web Application Firewall (WAF)** → Deploy a **WAF to detect and filter malicious requests**.  
✔ **Network Traffic Monitoring** → Implement **AI-driven anomaly detection** to monitor **suspicious behavior**.  
✔ **Role-Based Access Control (RBAC)** → Restrict **access to sensitive health data** based on user roles.  

---

# **Threat Modelling Process Summary**
```mermaid
mindmap
  root((Threat Modelling Process))
    Methodology
      STRIDE Analysis
      MITRE ATT&CK Framework
      Cyber Kill Chain
    Risk Assessment
      Inherent Risk Evaluation
      Critical Asset List
      Workshop Scheduling
    Controls Required
      Security Audits
      Patch Management
      Web Application Firewall (WAF)
      Network Monitoring
      Role-Based Access Control (RBAC)
      Employee Training (Phishing Awareness)
    Risk Summary
      Identified Risks<br/>(4 High, 3 Medium)
      Mitigation Plans
        Remediation Workflow
          Slack
          JIRA
    Attack Scenarios
      Phishing Attack
      Ransomware Attack
      Insider Threat
      SQL Injection