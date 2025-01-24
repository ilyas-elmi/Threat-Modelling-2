# Credential Theft via Brute Force or Credential Stuffing

## Introduction
This scenario examines the risk of attackers gaining unauthorized access to the SOE desktop application by exploiting weak or reused credentials through brute force or credential stuffing techniques. The attack targets sensitive patient data stored within the SOE system, compromising both security and compliance.

---

## Stages of the Attack

### Origins
The attack is initiated by an external attacker who identifies SOE as a high-value target due to its storage of sensitive patient data. The attacker focuses on the login interface of the SOE application.

### Reconnaissance
The attacker collects email addresses and usernames associated with SOE users. This information may be obtained through:
- Public data breaches.
- Social engineering techniques targeting dental practices.

### Weaponization
- **Brute Force Attack**: The attacker uses automated tools to guess weak or commonly used passwords for SOE accounts.
- **Credential Stuffing**: The attacker leverages previously leaked credentials from unrelated breaches to attempt logins on the SOE application.

### Delivery
Automated login attempts are launched against the SOE desktop application. The attacker uses:
- High-frequency login attempts in brute force attacks.
- Batch testing of stolen credential pairs in credential stuffing attacks.

### Exploitation
If successful, the attacker gains access to valid SOE accounts:
- Brute force attacks may compromise accounts with weak passwords.
- Credential stuffing succeeds if users reuse passwords from other breached accounts.

### Installation
The attacker establishes persistence by:
- Creating new admin accounts with elevated privileges.
- Installing malware or backdoors on compromised desktops for continued access.

### Actions on Objectives
Once access is obtained, the attacker:
- Exfiltrates patient data (e.g., PII, medical records).
- Disrupts operations by tampering with patient records or locking access (e.g., via ransomware).
- Explores lateral movement within the system to escalate access.

---

```mermaid
flowchart TD
    A[Attacker] -->|Gather user credentials| B[SOE User Accounts]
    B -->|Brute force weak passwords| C[SOE Desktop Application]
    B -->|Use stolen credentials| C
    C -->|Valid login| D[Access Granted]
    D -->|Create admin accounts| E[SOE Backend Server]
    D -->|Exfiltrate patient data| F[SOE Database]
    F -->|Send data to attacker| G[Command & Control Server]