# MITRE ATT&CK Sequence Summary for SOE Credential Theft Scenario

1. **Initial Access (T1110 – Brute Force)**  
   - Attackers attempt to gain access to the SOE system by:
     - Launching brute force attacks to guess weak passwords.
     - Using stolen credentials in credential stuffing attacks.

2. **Execution (T1204 – User Execution)**  
   - If stolen credentials are successfully used, attackers gain access to the SOE desktop application.

3. **Persistence (T1078 – Valid Accounts)**  
   - After gaining access, attackers maintain persistence by:
     - Creating unauthorized admin accounts.
     - Using compromised credentials repeatedly.

4. **Credential Access (T1555 – Credentials from Password Stores)**  
   - Attackers extract additional credentials stored on compromised desktops or within the SOE application.

5. **Discovery (T1083 – File and Directory Discovery)**  
   - Attackers explore the SOE environment to identify files, directories, and databases containing sensitive patient data.

6. **Collection (T1005 – Data from Local System)**  
   - Patient data (e.g., PII, medical records) is collected from the SOE application and associated databases.

7. **Command and Control (T1071 – Application Layer Protocol)**  
   - Attackers establish communication with a Command and Control (C&C) server to exfiltrate data.

8. **Exfiltration (T1041 – Exfiltration Over C2 Channel)**  
   - Sensitive data is transferred from the SOE system to the attacker’s external storage via the C&C channel.

9. **Impact (T1486 – Data Encrypted for Impact)**  
   - Attackers may deploy ransomware to encrypt patient data, halting SOE operations and demanding payment.

---

```mermaid
flowchart TD
    A["Initial Access (T1110)Brute Force/Credential Stuffing"] --> B["Execution (T1204)User Logs In with Stolen Credentials"]
    B --> C["Persistence (T1078)Create Admin Accounts"]
    C --> D["Credential Access (T1555)Extract Additional Credentials"]
    D --> E["Discovery (T1083)Identify Files and Databases"]
    E --> F["Collection (T1005)nGather Patient Data"]
    F --> G["Command and Control (T1071)Establish Communication"]
    G --> H["Exfiltration (T1041)Transfer Data to Attacker"]
    G --> I["Impact (T1486)Deploy Ransomware"]