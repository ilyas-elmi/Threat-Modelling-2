# SQL Injection Attack Targeting the SOE Database

## Introduction
This scenario examines the risk of SQL injection (SQLi) attacks targeting the SOE application, installed on dental workstations/desktops, and its backend database. SQL injection occurs when attackers exploit improperly sanitized input fields to execute unauthorized SQL queries. This attack could lead to unauthorized access to sensitive patient data, manipulation of records, or full database compromise.

---

## Stages of the Attack

### Origins
The attack begins with an external attacker identifying SOE as a target due to its storage of sensitive patient data. The attacker focuses on vulnerabilities in input fields or API calls initiated by the SOE desktop application.

### Reconnaissance
The attacker:
- Probes SOE application fields on dental workstations (e.g., patient search fields, scheduling inputs) to identify unsanitized inputs.
- Uses automated tools to map vulnerable input points and backend queries.

### Weaponization
The attacker crafts malicious SQL payloads, such as:
- `OR '1'='1'` to bypass authentication.
- `UNION SELECT` queries to extract sensitive data.
- `DROP TABLE` commands to disrupt operations.

### Delivery
Malicious SQL payloads are injected into input fields within the SOE desktop application. This could occur through:
- Patient search forms.
- Data entry fields.
- Backend API calls initiated by the desktop application.

### Exploitation
The SOE backend database processes the malicious SQL commands, allowing the attacker to:
- Access unauthorized data (e.g., patient records, credentials).
- Manipulate or delete data in the database.
- Execute administrative commands on the database server.

### Installation
The attacker may attempt to:
- Insert malicious triggers or procedures into the database for future exploitation.
- Deploy malware on the dental workstation for persistent access.

### Actions on Objectives
With access to the SOE database, the attacker:
- Exfiltrates sensitive patient data for misuse or sale.
- Disrupts operations by altering or deleting records.
- Escalates access to compromise other systems connected to the SOE application.

---


```mermaid
flowchart TD
    A[Attacker] -->|Probes SOE desktop input fields| B[SOE Application]
    B -->|Executes SQL payload| C[SOE Backend]
    C -->|Processes malicious query| D[SOE Database]
    D -->|Returns sensitive data| C
    D -->|Alters or deletes records| D
    C -->|Sends data to attacker| E[Attacker's Storage]