# Risk Summary for Scenario 2: Credential Theft

| **Risk ID** | **Description**                                   | **Severity** | **Likelihood** | **Impact**      | **Mitigation Plan**                                         |
|-------------|---------------------------------------------------|--------------|----------------|-----------------|------------------------------------------------------------|
| R1          | Weak passwords exploited via brute force attacks | High         | High           | High            | Enforce strong password policies and implement MFA         |
| R2          | Credential reuse from other breaches (stuffing)  | Critical     | High           | Very High       | Use credential monitoring tools and notify users to reset  |
| R3          | Unauthorized access to patient data              | High         | Medium         | Very High       | Enable RBAC and monitor access logs                        |
| R4          | Lack of rate-limiting allows automated attacks   | Critical     | High           | High            | Introduce rate-limiting and account lockout mechanisms     |
| R5          | Admin accounts created for persistence           | High         | Medium         | High            | Monitor for unauthorized admin account creation            |
| R6          | Exfiltration of sensitive patient data           | High         | Medium         | Very High       | Monitor data transfers and implement DLP (Data Loss Prevention) solutions |
| R7          | Operational downtime due to malicious actions    | High         | Medium         | High            | Develop and test a robust disaster recovery plan           |

---

