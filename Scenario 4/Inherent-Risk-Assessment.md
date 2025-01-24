# Inherent Risk Assessment for Insider Attack

## Risk Assessment Table

| **Risk**                  | **Description**                                                                 | **Type of Data**      | **Likelihood** | **Impact**      | **Overall Rating** |
|---------------------------|---------------------------------------------------------------------------------|-----------------------|----------------|-----------------|---------------------|
| **Unauthorized Data Access** | Insiders misuse legitimate access to view sensitive patient records.            | PII, medical records  | High           | Very High       | **Critical**        |
| **Data Exfiltration**     | Patient data is transferred to external storage or shared over unauthorized channels. | PII, medical records  | Medium         | Very High       | **High**            |
| **Data Manipulation**     | Insiders alter or delete patient records to disrupt operations or conceal actions. | PII, operational data | Medium         | High            | **High**            |
| **Compliance Violations** | Exposure or misuse of sensitive data violates privacy regulations (e.g., GDPR, HIPAA). | PII, medical records  | Medium         | Very High       | **High**            |
| **Operational Disruption**| Manipulated or deleted data disrupts workflows and damages patient care.         | Operational data      | Medium         | High            | **High**            |
| **Log Tampering**         | Insiders erase or modify activity logs to avoid detection.                       | Log data              | Medium         | High            | **High**            |

