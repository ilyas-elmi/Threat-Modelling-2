```mermaid
graph TD
    A[Attacker] -->|Phishing Email| B[SOE User]
    B -->|Clicks Link / Downloads Attachment| C[SOE Application]
    C -->|Validates Credentials| D[SOE Database]
    C -->|Executes Malicious Code| E[Backend Server]
    E -->|Connects to| F[Command and Control Server]
    F -->|Issues Commands| E
    E -->|Exfiltrates Sensitive Data| G[Attacker's Storage]
    D -->|Patient Data Accessed| E