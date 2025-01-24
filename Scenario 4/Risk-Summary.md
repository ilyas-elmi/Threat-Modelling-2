# Risk Summary for Insider Attack

| **Risk ID** | **Description**                                   | **Severity** | **Likelihood** | **Impact**      | **Mitigation Plan**                                         |
|-------------|---------------------------------------------------|--------------|----------------|-----------------|------------------------------------------------------------|
| R1          | Unauthorized access to sensitive patient data     | Critical     | High           | Very High       | Implement Role-Based Access Control (RBAC) and monitor all user activity |
| R2          | Data exfiltration to external devices or networks | High         | Medium         | Very High       | Deploy Data Loss Prevention (DLP) solutions and block unauthorized data transfers |
| R3          | Data manipulation or deletion                     | High         | Medium         | High            | Enable logging and monitoring of database modifications; restrict permissions |
| R4          | Log tampering to conceal malicious actions        | High         | Medium         | High            | Implement tamper-proof logging mechanisms and real-time alerts |
| R5          | Persistent access via unauthorized admin accounts | High         | Medium         | High            | Enforce MFA for admin accounts and regularly audit role changes |
| R6          | Compliance violations due to data misuse          | High         | Medium         | Very High       | Ensure encryption of sensitive data and align with GDPR/HIPAA requirements |
| R7          | Operational disruption from manipulated data      | High         | Medium         | High            | Regularly back up critical data and test disaster recovery plans |

