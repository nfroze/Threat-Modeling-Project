```mermaid
flowchart TD;
    %% Users & External Entities
    subgraph "Users & External Systems"
        Patients["👤 Patients"]
        HealthcareProviders["🏥 Healthcare Providers"]
        ThirdPartyServices["🔗 Third-Party Services"]
    end

    %% Frontend Layer
    subgraph "🌐 Frontend Layer (React.js)"
        Frontend["💻 Web App (React.js)"]
    end
    
    Patients -->|Login, Schedule, View Records| Frontend
    HealthcareProviders -->|Manage Patients, Appointments| Frontend
    
    %% Backend Layer
    subgraph "⚙️ Backend Layer (Node.js & Express)"
        Backend["🔄 API Gateway (Node.js & Express)"]
        Auth["🔐 Authentication (JWT, SSO, Cognito)"]
        Telehealth["📹 Telehealth Module (WebRTC, Socket.IO)"]
        MedicationMgmt["💊 MedTrack Pro API Integration"]
    end
    
    Frontend -->|RESTful API Calls| Backend
    Backend -->|OAuth2, JWT| Auth
    Backend -->|WebRTC Video Calls| Telehealth
    Backend -->|Medication Data Sync| MedicationMgmt

    %% Database & Storage
    subgraph "🗄️ Data Storage & Analytics"
        Database["📄 MariaDB (Patient Records)"]
        AWS_S3["☁️ AWS S3 (Encrypted Data Storage)"]
        Analytics["📊 HealthInsight Analytics"]
    end
    
    Backend -->|Store, Retrieve Patient Data| Database
    Database -->|Encrypted PII Data| AWS_S3
    Database -->|Healthcare Insights| Analytics

    %% Security & Compliance
    subgraph "🛡️ Security & Compliance"
        Security["🔏 HIPAA Compliance & Access Controls"]
        Logs["📜 Logging & Monitoring (ELK Stack, Prometheus)"]
    end
    
    Backend -.->|TLS/SSL Encryption| Database
    Backend -.->|Log Data| Logs
    Backend -.->|HIPAA Compliance| Security

    %% Deployment & Infrastructure
    subgraph "☁️ Cloud Infrastructure & CI/CD"
        DevOps["🚀 CI/CD Pipeline (GitHub Actions)"]
        AWS_Infra["☁️ AWS (EC2, Lambda, S3)"]
    end
    
    DevOps -->|Deployments| AWS_Infra
    Backend -->|Cloud Hosting| AWS_Infra
    Frontend -->|Builds & Deployments| DevOps