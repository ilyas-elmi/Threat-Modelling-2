# MITRE ATT&CK Sequence Summary for SQL Injection Attack

1. **Initial Access (T1190 – Exploit Public-Facing Application)**  
   - Attackers identify input fields in the SOE desktop application vulnerable to SQL injection. These input fields are exploited to send unauthorized SQL queries to the backend database.

2. **Execution (T1203 – Exploitation for Client Execution)**  
   - Malicious SQL payloads are crafted to manipulate the SOE application’s queries. Examples include:
     - `OR 1=1` for authentication bypass.
     - `UNION SELECT` for extracting sensitive data.

3. **Persistence (T1078 – Valid Accounts)**  
   - Attackers may create new admin accounts within the database or application for long-term access.

4. **Privilege Escalation (T1068 – Exploitation for Privilege Escalation)**  
   - Attackers use SQL injection to escalate privileges in the database, gaining admin-level access.

5. **Credential Access (T1555 – Credentials from Password Stores)**  
   - SQL injection is used to extract login credentials stored in plaintext or poorly encrypted fields within the database.

6. **Discovery (T1083 – File and Directory Discovery)**  
   - Attackers enumerate database structures (e.g., tables, columns) to locate sensitive data like patient records and credentials.

7. **Collection (T1005 – Data from Local System)**  
   - Sensitive patient data, including PII and medical records, is retrieved from the database using unauthorized queries.

8. **Command and Control (T1071 – Application Layer Protocol)**  
   - Exfiltrated data is sent to an external Command and Control (C&C) server via encrypted or application-layer protocols.

9. **Exfiltration (T1041 – Exfiltration Over C2 Channel)**  
   - Data extracted from the SOE database is transferred to an attacker-controlled server for misuse.

10. **Impact (T1486 – Data Encrypted for Impact)**  
    - If attackers deploy ransomware through SQL injection, patient data or database tables may be encrypted or deleted, disrupting operations.

---

```mermaid
flowchart TD
    A["Initial Access (T1190)Exploit Public-Facing Application"] --> B["Execution (T1203)Inject Malicious SQL"]
    B --> C["Persistence (T1078)Create Admin Accounts"]
    C --> D["Privilege Escalation (T1068)Gain Admin Access"]
    D --> E["Credential Access (T1555)Extract Login Credentials"]
    D --> F["Discovery (T1083)Enumerate Tables and Fields"]
    F --> G["Collection (T1005)Retrieve Patient Data"]
    G --> H["Command and Control (T1071)Send Data to C&C"]
    H --> I["Exfiltration (T1041)Transfer Data to Attacker"]
    H --> J["Impact (T1486)Deploy Ransomware"]