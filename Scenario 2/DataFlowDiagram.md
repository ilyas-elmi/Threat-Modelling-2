```mermaid
graph TD
    %% Entities
    A[Attacker] -->|Brute force or credential stuffing attack| B[SOE Login Interface]
    B -->|Valid credentials found| C[SOE Application]
    C -->|Access patient data| D[SOE Backend Server]
    D -->|Retrieve data| E[SOE Database]
    E -->|Send sensitive data| D
    D -->|Provide data to attacker| C
    C -->|Data accessed| F[SOE User Account]

    %% Persistence
    C -->|Create admin accounts| G[SOE Backend Admin Panel]
    G -->|Persist unauthorized access| C

    %% Data Exfiltration
    C -->|Connects to| H[Command and Control Server]
    H -->|Exfiltrate data| A