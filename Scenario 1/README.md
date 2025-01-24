# Kill Chain Attack Description: SOE Phishing Attack Scenario

## Stages of the Attack

### Origins
The attack begins with an external attacker identifying SOE, a dentistry-focused desktop application, as a target. The attacker is motivated by the application's storage of sensitive patient data, including phone numbers, addresses, and medical records.

### Reconnaissance
The attacker gathers information about SOE users and their workflows:
- Researching email domains of dental practices using SOE.
- Identifying high-value targets such as administrators or staff with access to patient data.

### Weaponization
The attacker creates a phishing campaign tailored to SOE users:
- Emails designed to look like official SOE notifications (e.g., password reset requests or urgent security alerts).
- Payloads include links to fake login pages or malicious attachments that install malware on the user’s system.

### Delivery
The phishing emails are sent to SOE users. These emails are crafted to:
- Appear urgent and legitimate, encouraging the user to interact.
- Contain malicious links or attachments.

### Exploitation
Once a user interacts with the email:
- If the user enters credentials on a fake page, the attacker harvests those credentials for later use.
- If the user downloads a malicious attachment, malware is executed on their system, compromising their access to SOE.

### Installation
The attacker establishes persistence by:
- Installing backdoors or remote access tools on the compromised desktop.
- Harvesting more credentials stored locally or in SOE sessions.

### Actions on Objectives
With access to the SOE desktop application and its backend systems, the attacker:
- Exfiltrates sensitive patient data from the SOE database.
- Disrupts operations by corrupting or locking patient records (e.g., via ransomware).
- Uses the stolen data for identity theft or ransom demands.

```mermaid
flowchart TD
    A[Attacker] -->|Phishing Email| B[SOE User]
    B -->|Clicks Link or Downloads Attachment| C[SOE Application]
    C -->|Validates Credentials| D[SOE Database]
    C -->|Executes Malware| E[Backend Server]
    E -->|Communicates With| F[Command and Control Server]
    F -->|Commands to Exfiltrate Data| E
    E -->|Transfers Data to Attacker| G[Attacker's Storage]