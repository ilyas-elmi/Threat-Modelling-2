# Kill Chain Attack Description: SOE Phishing Attack Scenario

## Stages of the Attack

### Origins
The attack begins with an external attacker identifying SOE, a dentistry-focused application, as a target due to its storage of sensitive patient data such as phone numbers, addresses, and medical records. The application's public-facing nature increases its exposure to threats.

### Reconnaissance
The attacker gathers information about SOE by researching its architecture, technologies, and public-facing components. This includes identifying potential weak points in the application, such as outdated libraries or unprotected login portals.

### Weaponization
The attacker crafts a phishing campaign tailored to SOE users. This involves creating emails that mimic legitimate communication from the SOE system, with malicious links or attachments designed to harvest admin credentials or infect systems with malware.

### Delivery
Phishing emails are sent to SOE users, including staff and administrators. These emails appear to come from trusted sources (e.g., "SOE System Notification") and contain urgent messages to click on a link or download an attachment.

### Exploitation
Once a user interacts with the phishing email (e.g., clicking a link), the attacker gains access to their credentials or installs malicious code. Using the credentials, the attacker logs into the SOE system and accesses sensitive patient data.

### Installation
After gaining access, the attacker establishes a foothold by creating a backdoor account or uploading malware to ensure persistent access. This may include manipulating SOE's user management system to create hidden accounts with elevated privileges.

### Actions on Objectives
With access to SOE, the attacker:
- Exfiltrates sensitive patient data, including contact details and medical records.
- Disrupts operations by corrupting or locking essential records.
- Uses the data to execute further attacks, such as identity theft or ransom demands.

```mermaid
flowchart LR
    A[Reconnaissance] -->|Identify SOE as a target| B
    B[Weaponization] -->|Craft phishing email| C
    C[Delivery] -->|Send phishing email| D
    D[Exploitation] -->|Gain admin credentials| E
    E[Installation] -->|Create backdoor account| F
    F[Actions on Objectives] -->|Exfiltrate patient data| G
    F -->|Disrupt SOE operations| H