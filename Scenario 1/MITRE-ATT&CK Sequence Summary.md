  # MITRE ATT&CK Sequence Summary for SOE Phishing Attack

1. **Initial Access (T1566 – Phishing)**  
   - Attackers send phishing emails to SOE users, tricking them into:
     - Clicking on malicious links leading to credential harvesting pages.
     - Downloading attachments containing malware payloads.

2. **Execution (T1204 – User Execution)**  
   - Users unknowingly execute malicious attachments, allowing the attacker to:
     - Install malware on their local desktops.
     - Exploit the SOE application environment.

3. **Persistence (T1078 – Valid Accounts)**  
   - Stolen credentials from phishing emails are used to establish persistent access to the SOE application and its backend systems.

4. **Credential Access (T1555 – Credentials from Password Stores)**  
   - Malware extracts locally stored credentials from the compromised desktop, including:
     - Passwords saved in browsers or SOE sessions.

5. **Discovery (T1083 – File and Directory Discovery)**  
   - Malware and attackers enumerate files, directories, and connected systems within the SOE environment to locate patient data.

6. **Collection (T1005 – Data from Local System)**  
   - Sensitive data, such as patient information (PII, medical records), is collected from:
     - SOE application directories.
     - The local database on the compromised backend.

7. **Command and Control (T1071 – Application Layer Protocol)**  
   - Malware communicates with the attacker's Command and Control (C&C) server using:
     - HTTP/HTTPS or other protocols for exfiltration and command execution.

8. **Exfiltration (T1041 – Exfiltration Over C2 Channel)**  
   - Collected data is exfiltrated to the attacker’s server via encrypted channels to avoid detection.

9. **Impact (T1486 – Data Encrypted for Impact)**  
   - If the attacker chooses, ransomware may encrypt local or backend data to disrupt operations, demanding payment for decryption keys.

---

```mermaid
flowchart TD
    A["Initial Access (T1566)\Phishing Email"] --> B["Execution (T1204)\User Executes Malware"]
    B --> C["Persistence (T1078)\Valid Accounts Created"]
    C --> D["Credential Access (T1555)\Credentials Stolen"]
    D --> E["Discovery (T1083)\Files and Directories Identified"]
    E --> F["Collection (T1005)\Sensitive Data Gathered"]
    F --> G["Command and Control (T1071)\Communication Established"]
    G --> H["Exfiltration (T1041)\Data Exfiltrated"]
    G --> I["Impact (T1486)\Ransomware Deployed"]