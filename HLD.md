```mermaid
flowchart TD
    subgraph User_Interface
        UI[User Interface]
    end
    subgraph Frontend_EC2
        FE[Frontend Server]
    end
    subgraph Backend
        BE[Backend Server]
    end
    subgraph Database
        DB[Database Server]
    end
    subgraph External_Services
        CnC[Command and Control Server]
    end
    UI --> FE
    FE --> BE
    BE --> DB
    BE --> CnC