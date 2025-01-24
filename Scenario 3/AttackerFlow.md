## Attacker Flow for SQL Injection Attack

```mermaid
sequenceDiagram
    participant Attacker
    participant SOEApp
    participant BackendServer
    participant SOEDatabase
    participant CnCServer

    activate Attacker
    Attacker->>SOEApp: Probes input fields for vulnerabilities
    SOEApp->>Attacker: Returns responses indicating potential SQL vulnerabilities
    deactivate Attacker

    activate Attacker
    Attacker->>SOEApp: Injects malicious SQL payload (e.g., '1'='1')
    SOEApp->>BackendServer: Forwards malicious query to backend
    BackendServer->>SOEDatabase: Executes malicious query
    SOEDatabase->>BackendServer: Returns unauthorized data (e.g., patient records)
    BackendServer->>SOEApp: Displays sensitive data to attacker
    deactivate Attacker

    activate Attacker
    Attacker->>SOEDatabase: Sends destructive queries (e.g., DROP TABLE)
    SOEDatabase->>BackendServer: Alters or deletes records
    BackendServer->>CnCServer: Communicates extracted data
    CnCServer->>Attacker: Confirms exfiltration
    deactivate Attacker