## Attacker Flow for Scenario 2

```mermaid
sequenceDiagram
    participant Attacker
    participant LoginInterface
    participant SOEApp
    participant BackendServer
    participant SOEDatabase
    participant CnCServer

    activate Attacker
    Attacker->>LoginInterface: Initiates brute force or credential stuffing attack
    LoginInterface->>Attacker: Valid credentials identified (successful login)
    deactivate Attacker
    activate Attacker
    Attacker->>SOEApp: Logs into the SOE application with stolen credentials
    SOEApp->>BackendServer: Requests access to patient data
    BackendServer->>SOEDatabase: Retrieves sensitive patient records
    SOEDatabase->>BackendServer: Returns patient data
    BackendServer->>SOEApp: Provides access to sensitive records
    SOEApp->>Attacker: Displays patient data in compromised account
    deactivate Attacker
    activate Attacker
    Attacker->>BackendServer: Creates backdoor admin accounts
    BackendServer->>CnCServer: Establishes communication with Command & Control
    CnCServer->>BackendServer: Issues commands for data exfiltration
    BackendServer->>CnCServer: Transfers sensitive patient data
    deactivate Attacker