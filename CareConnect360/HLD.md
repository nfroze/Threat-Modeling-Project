```mermaid
flowchart TD;
    %% External Entities
    Patients["👤 Patients"] -->|Web & Mobile Access| Frontend["🌐 Web App"]
    HealthcareProviders["🏥 Providers"] -->|Manage Patients| Frontend
    ThirdParty["🔗 Third-Party Services"] -->|API Integration| Backend["⚙️ Backend System"]

    %% System Architecture
    Frontend -->|API Calls| Backend
    Backend -->|Authenticate Users| Auth["🔐 Authentication"]
    Backend -->|Store & Retrieve Data| Database["🗄️ Patient Database"]

    %% Security & Compliance
    Auth -.->|MFA, Secure Login| Frontend
    Backend -.->|Access Controls, Logging| Security["🛡️ Security Layer"]