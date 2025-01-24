sequenceDiagram
    participant Attacker
    participant SOEApp
    participant User
    participant BackendServer
    participant CnCServer
    activate Attacker
    Attacker->>SOEApp: Identify SOE as a target (e.g., public-facing interfaces)
    SOEApp->>Attacker: Application information gathered (e.g., login portals, email domains)
    deactivate Attacker
    activate Attacker
    Attacker->>SOEApp: Craft phishing campaign impersonating SOE
    SOEApp->>Attacker: Fake emails with malicious links/attachments created
    deactivate Attacker
    activate Attacker
    Attacker->>User: Send phishing email appearing as SOE system notification
    User->>SOEApp: Clicks malicious link or downloads attachment
    SOEApp->>User: Prompts for credentials or executes malware
    deactivate User
    Attacker->>SOEApp: Uses stolen credentials to access patient data
    SOEApp->>BackendServer: Executes commands (e.g., database queries)
    BackendServer->>CnCServer: Establishes communication with Command and Control server
    CnCServer->>BackendServer: Sends commands to exfiltrate data
    BackendServer->>CnCServer: Transfers sensitive patient data (e.g., phone numbers, addresses)
    deactivate Attacker