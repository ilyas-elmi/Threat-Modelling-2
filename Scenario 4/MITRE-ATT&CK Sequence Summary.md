# MITRE ATT&CK Sequence Summary for Insider Attack

1. **Initial Access (T1078 – Valid Accounts)**  
   - The insider uses legitimate credentials to access the SOE application. This is a trusted user with authorized access to sensitive data.

2. **Execution (T1059 – Command and Scripting Interpreter)**  
   - The insider may use scripts or commands to query the SOE database, extract data, or automate malicious activities.

3. **Persistence (T1547 – Boot or Logon Autostart Execution)**  
   - Insiders may install scripts or software on the workstation to maintain unauthorized access to SOE resources.

4. **Privilege Escalation (T1068 – Exploitation for Privilege Escalation)**  
   - Insiders could leverage their access to gain elevated privileges by creating unauthorized admin accounts.

5. **Credential Access (T1555 – Credentials from Password Stores)**  
   - Insiders extract stored credentials or session tokens within the SOE environment for further exploitation.

6. **Discovery (T1083 – File and Directory Discovery)**  
   - The insider explores the database structure and directory contents to locate sensitive patient records or operational data.

7. **Collection (T1005 – Data from Local System)**  
   - Patient data (e.g., PII, medical records) is extracted using SOE features like export tools or direct database queries.

8. **Command and Control (T1071 – Application Layer Protocol)**  
   - Data is transferred to external devices or shared via application-layer protocols like email or cloud storage.

9. **Exfiltration (T1041 – Exfiltration Over C2 Channel)**  
   - The insider sends sensitive data to external locations (e.g., USB devices, personal email accounts).

10. **Impact (T1485 – Data Destruction)**  
    - The insider modifies or deletes patient records to disrupt operations, sabotage workflows, or hide malicious actions.

---

```mermaid
flowchart TD
    A["Initial Access (T1078)Valid Accounts"] --> B["Execution (T1059)Query Database/Run Scripts"]
    B --> C["Privilege Escalation (T1068)Create Admin Accounts"]
    B --> D["Credential Access (T1555)Extract Stored Credentials"]
    C --> E["Discovery (T1083)Explore Database Structure"]
    E --> F["Collection (T1005)Extract Patient Data"]
    F --> G["Command and Control (T1071)Transfer Data to External Device"]
    G --> H["Exfiltration (T1041)Send Data to External Locations"]
    G --> I["Impact (T1485)Modify or Delete Records"]