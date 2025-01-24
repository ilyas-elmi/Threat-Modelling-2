# Inherent Risk Assessment for SQL Injection Attack

## Risk Assessment Table

| **Risk**                  | **Description**                                                                 | **Type of Data**      | **Likelihood** | **Impact**      | **Overall Rating** |
|---------------------------|---------------------------------------------------------------------------------|-----------------------|----------------|-----------------|---------------------|
| **Unauthorized Data Access** | SQL injection allows attackers to extract sensitive patient data from the database. | PII, medical records  | High           | Very High       | **Critical**        |
| **Data Manipulation**     | Attackers alter or delete patient data using malicious SQL commands.             | PII, operational data | Medium         | High            | **High**            |
| **System Disruption**     | SQL injection is used to execute destructive queries, such as `DROP TABLE`.     | Operational data      | Medium         | Very High       | **High**            |
| **Credential Theft**      | SQL injection reveals login credentials or session tokens stored in the database. | User credentials      | High           | High            | **Critical**        |
| **Compliance Violations** | Exposure or manipulation of patient data violates GDPR or HIPAA regulations.    | PII, medical records  | Medium         | Very High       | **High**            |

