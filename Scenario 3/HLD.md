
```mermaid
flowchart TD
    Attacker -->|Injects SQL payload| SOEApp[SOE Desktop Application]
    SOEApp -->|Sends query| BackendServer[SOE Backend Server]
    BackendServer -->|Queries database| Database[SOE Database]
    Database -->|Sends sensitive data| BackendServer
    BackendServer -->|Data sent to attacker| Attacker
    BackendServer -->|Logs suspicious activity| LoggingSystem[Monitoring and Logging System]