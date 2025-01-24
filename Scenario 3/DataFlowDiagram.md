```mermaid
graph TD
    %% Entities
    Attacker["Attacker (External)"] -->|Probes for SQL vulnerabilities| SOEApp["SOE Desktop Application"]
    
    %% Malicious Query Flow
    SOEApp -->|Executes malicious SQL query| BackendServer["SOE Backend Server"]
    BackendServer -->|Processes query| Database["SOE Database"]
    Database -->|Returns unauthorized data| BackendServer
    BackendServer -->|Sends data to attacker| SOEApp
    SOEApp -->|Displays data| Attacker
    
    %% Data Exfiltration
    Database -->|Exfiltrates patient records| CnCServer["Command & Control Server"]
    CnCServer -->|Sends data to attacker| Attacker
    
    %% Destructive Actions
    Attacker -->|Issues DROP TABLE or ALTER commands| Database
    Database -->|Alters or deletes records| Database