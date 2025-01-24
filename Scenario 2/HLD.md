```mermaid
flowchart TD
    Attacker -->|Launch brute force or credential stuffing| LoginInterface
    LoginInterface -->|Valid credentials| SOEApp
    SOEApp -->|Request patient data| BackendServer
    BackendServer -->|Retrieve data| Database
    Database -->|Send sensitive data| BackendServer
    BackendServer -->|Provide data to attacker| SOEApp
    SOEApp -->|Exfiltrate data| CnCServer
    SOEApp -->|Create admin accounts| AdminPanel