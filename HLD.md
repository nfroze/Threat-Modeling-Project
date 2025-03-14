```mermaid
graph TD;
    %% Users & External Entities
    Patients["👤 Patients"] -->|Web Portal, Mobile App| Frontend["🌐 Frontend (React.js)"]
    HealthcareProviders["🏥 Healthcare Providers"] -->|Web Portal| Frontend
    ThirdPartyServices["🔗 Third-Party Services"] -->|APIs| Backend["⚙️ Backend (Node.js & Express)"]

    %% Frontend Layer
    Frontend -->|RESTful API Calls| Backend
    Frontend -->|WebRTC Video Calls| Telehealth["📹 Telehealth Module (WebRTC, Socket.IO)"]

    %% Backend Layer
    Backend -->|JWT Authentication, SSO| Auth["🔐 Authentication (Cognito, SSO)"]
    Backend -->|CRUD Operations| Database["🗄️ MariaDB"]
    Backend -->|API Calls| ThirdPartyServices
    Backend -->|Medication Data| MedicationMgmt["💊 MedTrack Pro Integration"]

    %% Data Storage & Security
    Database -->|Encrypted PII Data| AWS_S3["☁️ AWS S3 Storage"]
    Database -->|Healthcare Analytics| Analytics["📊 HealthInsight Portal"]
    Backend -->|Logs & Monitoring| Monitoring["📡 ELK Stack & Prometheus"]

    %% Security & Compliance
    Auth -.->|OAuth2, JWT| Backend
    Backend -.->|TLS/SSL Encryption| Database
    Backend -.->|HIPAA Compliance| Security["🛡️ Security Controls"]

    %% CI/CD & Deployment
    Backend -->|Deployments| DevOps["🚀 CI/CD (GitHub Actions)"]
    Frontend -->|Builds & Deployments| DevOps
    DevOps -->|AWS EC2, Lambda, S3| CloudInfra["☁️ AWS Infrastructure"]