| Risk ID | Description                                          | Severity | Likelihood | Impact | Controls Required                                      |
|---------|------------------------------------------------------|----------|------------|--------|--------------------------------------------------------|
| R1      | Excessive user privileges                           | High     | High       | Critical | Implement Role-Based Access Control (RBAC) and Least Privilege Access |
| R2      | Lack of user activity monitoring                    | High     | Medium     | High    | Deploy User and Entity Behavior Analytics (UEBA) to detect anomalies |
| R3      | No Data Loss Prevention (DLP) controls              | High     | High       | High    | Implement DLP solutions to monitor and restrict data exfiltration |
| R4      | Weak authentication and session management          | High     | High       | High    | Enforce Multi-Factor Authentication (MFA) and session timeouts |
| R5      | Lack of insider threat awareness and training       | Medium   | High       | High    | Conduct regular security training and phishing simulations |
| R6      | No restrictions on external storage and USB devices | Medium   | High       | High    | Disable USB access and enforce endpoint protection policies |
| R7      | Poor audit logging and log retention                | High     | Medium     | High    | Implement centralized logging with SIEM integration for real-time alerts |
| R8      | No restrictions on third-party cloud applications   | High     | Medium     | High    | Restrict unauthorized cloud file-sharing and monitor SaaS activity |
| R9      | Inadequate background checks for employees          | Medium   | Medium     | Medium  | Strengthen hiring process with comprehensive background screening |
| R10     | No clear incident response plan for insider threats | High     | Medium     | High    | Develop and test an Insider Threat Response Plan with predefined actions |