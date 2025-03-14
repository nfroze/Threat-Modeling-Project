```mermaid
graph TD;
    %% External Entities
    Patients["👤 Patients"] -->|Login, Schedule, View Records| UserAuth["🔐 UserAuth"]
    HealthcareProviders["🏥 HealthcareProviders"] -->|Login, Manage Records| UserAuth
    ThirdParty["🔗 ThirdPartyServices"] -->|API Requests| MedicationManagement["💊 MedicationManagement"]

    %% Processes
    UserAuth -->|JWT, Cognito, SSO| MariaDB["🗄️ MariaDB"]
    Patients -->|Submit, Update Info| PatientManagement["📋 PatientManagement"]
    HealthcareProviders -->|Manage Patient Data| PatientManagement
    PatientManagement -->|Store, Retrieve Data| MariaDB

    Patients -->|Send Messages| SecureMessaging["💬 SecureMessaging"]
    HealthcareProviders -->|Send Messages| SecureMessaging
    SecureMessaging -->|Real-time Communication| HealthcareProviders

    Patients -->|Schedule Appointments| AppointmentScheduling["📅 AppointmentScheduling"]
    HealthcareProviders -->|Manage Appointments| AppointmentScheduling
    AppointmentScheduling -->|Store Appointments| MariaDB
    AppointmentScheduling -->|Send Reminders| Patients

    Patients -->|Start Telehealth Session| Telehealth["📹 Telehealth"]
    HealthcareProviders -->|Join Telehealth Session| Telehealth
    Telehealth -->|WebRTC, Video Calls| Patients

    MedicationManagement -->|Fetch Medication Data| MariaDB
    MedicationManagement -->|Send Alerts| Patients

    %% Data Stores
    MariaDB -->|Store & Retrieve Data| Analytics["📊 Analytics"]
    Analytics -->|Insights, Reports| HealthcareProviders
    Analytics -->|Log Data| Logs["📝 LogManagement_ELK"]
    Analytics -->|Monitor System| Monitoring["📡 Prometheus"]

    %% Data Encryption & Security
    UserAuth -.->|TLS/SSL Encryption| MariaDB
    SecureMessaging -.->|End-to-End Encryption| HealthcareProviders
    MariaDB -.->|Encrypted Data| AWS_S3["☁️ AWS_S3_Storage"]