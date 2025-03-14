graph TD;
    %% External Entities
    Patients[Patients] -->|Login, Schedule, View Records| UserAuth[User Authentication]
    HealthcareProviders[Healthcare Providers] -->|Login, Manage Records| UserAuth
    ThirdParty[Third-Party Services] -->|API Requests| MedicationMgmt[Medication Management]

    %% Processes
    UserAuth -->|JWT, Cognito, SSO| MariaDB[MariaDB (Patient Records)]
    Patients -->|Submit, Update Info| PatientMgmt[Patient Data Management]
    HealthcareProviders -->|Manage Patient Data| PatientMgmt
    PatientMgmt -->|Store, Retrieve Data| MariaDB

    Patients -->|Send Messages| SecureMessaging[Secure Messaging]
    HealthcareProviders -->|Send Messages| SecureMessaging
    SecureMessaging -->|Real-time Communication| HealthcareProviders

    Patients -->|Schedule Appointments| AppointmentScheduling[Appointment Scheduling]
    HealthcareProviders -->|Manage Appointments| AppointmentScheduling
    AppointmentScheduling -->|Store Appointments| MariaDB
    AppointmentScheduling -->|Send Reminders| Patients

    Patients -->|Start Telehealth Session| Telehealth[Telehealth Integration]
    HealthcareProviders -->|Join Telehealth Session| Telehealth
    Telehealth -->|WebRTC, Video Calls| Patients

    MedicationMgmt -->|Fetch Medication Data| MariaDB
    MedicationMgmt -->|Send Alerts| Patients

    %% Data Stores
    MariaDB -->|Store & Retrieve Data| Analytics[Analytics & Monitoring]
    Analytics -->|Insights, Reports| HealthcareProviders
    Analytics -->|Log Data| Logs[Log Management (ELK)]
    Analytics -->|Monitor System| Monitoring[Prometheus]

    %% Data Encryption & Security
    UserAuth -.->|TLS/SSL Encryption| MariaDB
    SecureMessaging -.->|End-to-End Encryption| HealthcareProviders
    MariaDB -.->|Encrypted Data| AWS_S3[AWS S3 Storage]