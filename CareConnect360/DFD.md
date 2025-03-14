```mermaid
flowchart TD;
    %% External Entities
    Patients["👤 Patients"] -->|Login, Schedule, View Records| Frontend["🌐 CareConnect360 Web App"]
    HealthcareProviders["🏥 Providers"] -->|Manage Patients, Appointments| Frontend
    ThirdParty["🔗 Third-Party Services"] -->|API Requests| Backend["⚙️ Backend System"]

    %% Main System Components
    Frontend -->|REST API Calls| Backend
    Backend -->|Authenticate Users| Auth["🔐 Authentication System"]
    Backend -->|Store, Retrieve Patient Data| Database["🗄️ Patient Database"]
    
    %% External Interactions
    Backend -->|Sync Data, Integrate Services| ThirdParty

    %% Security Measures
    Auth -.->|TLS/SSL Encryption| Database
    Frontend -.->|MFA, Secure Login| Auth
    Backend -.->|Access Controls, Logging| Security["🛡️ Security & Compliance"]