```mermaid
graph TD
    %% Entities
    Attacker["Attacker (External)"] -->|Sends phishing email| User["SOE User"]
    
    %% User Interaction
    User -->|Clicks link / Downloads attachment| UserSystem["User's Desktop"]
    UserSystem -->|Provides credentials| FakeLoginPage["Fake Login Page"]
    UserSystem -->|Executes malware| Malware["Malicious Payload"]

    %% Credential Harvesting
    FakeLoginPage -->|Stores credentials| Attacker["Attacker (External)"]

    %% Malware Execution
    Malware -->|Steals local SOE credentials| Attacker
    Malware -->|Connects to| BackendServer["SOE Backend Server"]
    BackendServer -->|Accesses sensitive data| Database["SOE Database"]

    %% Data Exfiltration
    BackendServer -->|Sends sensitive data| CnCServer["Command & Control Server"]
    CnCServer -->|Transfers data to| AttackerStorage["Attacker's Storage"]