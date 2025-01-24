```mermaid
graph TD
    Attacker -->|Phishing Email| User
    User -->|Credentials or Malware| SOEApp
    SOEApp -->|Sensitive Data Access| SOEDatabase
    SOEApp -->|Compromised System| BackendServer
    BackendServer -->|Commands and Data Exfiltration| CnCServer
    CnCServer -->|Extracted Data| Attacker