## Attacker Flow for Insider Attack

```mermaid
sequenceDiagram
    participant Insider
    participant SOEApp
    participant BackendServer
    participant SOEDatabase
    participant ExternalDevice

    activate Insider
    Insider->>SOEApp: Logs in with valid credentials
    SOEApp->>BackendServer: Requests access to patient data
    BackendServer->>SOEDatabase: Queries sensitive patient records
    SOEDatabase->>BackendServer: Returns patient data
    BackendServer->>SOEApp: Displays data to insider
    deactivate Insider

    activate Insider
    Insider->>SOEApp: Exports sensitive data
    SOEApp->>ExternalDevice: Transfers data to external storage (USB/email)
    deactivate Insider

    activate Insider
    Insider->>SOEDatabase: Modifies or deletes patient records
    SOEDatabase->>BackendServer: Reflects tampered records
    BackendServer->>SOEApp: Displays manipulated data
    deactivate Insider