# Insider Attack Targeting Sensitive Patient Data in SOE

## Introduction
This scenario examines the risk of an insider threat where a trusted employee misuses their legitimate access to the SOE desktop application to access, exfiltrate, or manipulate sensitive patient data. Insider threats pose unique challenges as they exploit authorized credentials and access permissions, making them harder to detect compared to external attacks.

---

## Stages of the Attack

### Origins
The attack originates from an insider, such as an employee, contractor, or technician, who has access to the SOE application installed on dental workstations. Motivations may include financial gain, personal grievances, or accidental misuse of access.

### Reconnaissance
The insider:
- Identifies the scope of their access within the SOE application.
- Locates sensitive patient data (e.g., PII, medical records).
- Tests system or application restrictions to gauge logging and monitoring effectiveness.

### Weaponization
The insider uses their access to:
- Export patient records via application features or direct database queries.
- Manipulate records, such as altering or deleting data to disrupt operations or conceal actions.
- Install unauthorized software or scripts to extract data periodically.

### Delivery
The insider exfiltrates sensitive data by:
- Downloading data directly to external storage devices (e.g., USB drives).
- Sending data through email or file-sharing services.
- Leveraging access to other connected systems to spread or export sensitive data.

### Exploitation
The insider misuses the exfiltrated or manipulated data:
- Selling PII or medical records on the dark web.
- Using the data for blackmail or personal gain.
- Tampering with records to sabotage operations.

### Actions on Objectives
The insider achieves their goals, which may include:
- Financial profit through data sale or blackmail.
- Disruption of operations via data manipulation or sabotage.
- Covering their tracks by erasing logs or bypassing monitoring systems.



---

```mermaid
flowchart TD
    A[Insider] -->|Logs in with valid credentials| B[SOE Application]
    B -->|Accesses sensitive patient data| C[SOE Backend Server]
    C -->|Queries patient records| D[SOE Database]
    D -->|Returns data| C
    C -->|Sends data to insider| B
    B -->|Exfiltrates data| E[External Storage/Network]
    B -->|Manipulates patient records| D
    D -->|Data tampered| C