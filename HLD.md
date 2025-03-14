```mermaid
flowchart TD;
    %% Users & External Entities
    subgraph Users["👥 Users & External Systems"]
        Patients["👤 Patients"]
        HealthcareProviders["🏥 Providers"]
        ThirdParty["🔗 3rd-Party APIs"]
    end

    %% Frontend Layer
    subgraph FrontendLayer["🌐 Frontend (React.js)"]
        Frontend["💻 Web App"]
    end
    
    Patients -->|Login, Schedule| Frontend
    HealthcareProviders -->|Manage Patients| Frontend
    
    %% Backend Layer
    subgraph BackendLayer["⚙️ Backend (Node.js & Express)"]
        Backend["🔄 API Gateway"]
        Auth["🔐 Auth (JWT, SSO)"]
        Telehealth["📹 Telehealth (WebRTC)"]
        MedMgmt["💊 MedTrack API"]
    end
    
    Frontend -->|API Calls| Backend
    Backend -->|OAuth2, JWT| Auth
    Backend -->|Video Calls| Telehealth
    Backend -->|Sync Med Data| MedMgmt
    ThirdParty -->|API Requests| MedMgmt

    %% Database & Storage
    subgraph DataStorage["🗄️ Data & Analytics"]
        Database["📄 MariaDB"]
        AWS_S3["☁️ AWS S3 (Encrypted)"]
        Analytics["📊 Health Insights"]
    end
    
    Backend -->|Store/Retrieve Data| Database
    Database -->|Encrypted Data| AWS_S3
    Database -->|Analytics Data| Analytics

    %% Security & Compliance
    subgraph SecurityLayer["🛡️ Security & Logging"]
        Security["🔏 HIPAA Compliance"]
        Logs["📜 ELK & Prometheus"]
    end
    
    Backend -.->|TLS/SSL Encryption| Database
    Backend -.->|Log Data| Logs
    Backend -.->|HIPAA Compliance| Security

    %% Deployment & Infrastructure
    subgraph CloudInfra["☁️ Cloud & CI/CD"]
        DevOps["🚀 CI/CD Pipeline"]
        AWS_Infra["☁️ AWS Infra"]
    end
    
    DevOps -->|Deployments| AWS_Infra
    Backend -->|Cloud Hosting| AWS_Infra
    Frontend -->|Builds & Deployments| DevOps