# Risk Summary for SQL Injection Attack

| **Risk ID** | **Description**                                   | **Severity** | **Likelihood** | **Impact**      | **Mitigation Plan**                                         |
|-------------|---------------------------------------------------|--------------|----------------|-----------------|------------------------------------------------------------|
| R1          | Unauthorized access to sensitive patient data via SQL injection | Critical     | High           | Very High       | Use parameterized queries and sanitize all user inputs      |
| R2          | Data manipulation or deletion caused by malicious SQL commands | High         | Medium         | Very High       | Restrict database permissions and monitor query patterns    |
| R3          | Credential theft through exposed or poorly secured database fields | High         | High           | High            | Encrypt stored credentials and limit access to sensitive fields |
| R4          | Operational downtime from destructive SQL commands (e.g., DROP TABLE) | High         | Medium         | Very High       | Set up database triggers and backups to prevent data loss  |
| R5          | Compliance violations due to exposure of patient data | High         | Medium         | Very High       | Regularly audit database security and ensure compliance with GDPR/HIPAA |
| R6          | Persistent access enabled through unauthorized account creation | High         | Medium         | High            | Monitor for unauthorized admin account creation and enforce MFA |
| R7          | Exfiltration of patient data to external servers | High         | Medium         | Very High       | Monitor data transfers and implement Data Loss Prevention (DLP) solutions |

