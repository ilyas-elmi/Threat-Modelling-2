# Inherent Risk Assessment for SOE Phishing Attack Scenario

## Risk Assessment Table

| **Risk**                  | **Description**                                                                 | **Type of Data**      | **Likelihood** | **Impact**      | **Overall Rating** |
|---------------------------|---------------------------------------------------------------------------------|-----------------------|----------------|-----------------|---------------------|
| **Credential Theft**      | Phishing emails trick users into providing credentials through a fake login page. | User credentials      | High           | High            | **Critical**        |
| **Malware Execution**     | Malware downloaded via email infects desktops, stealing credentials or persisting access. | User credentials, PII | High           | High            | **Critical**        |
| **Data Exfiltration**     | Sensitive patient data exfiltrated from the SOE database via malware or credentials. | PII, medical records  | Medium         | Very High       | **High**            |
| **Operational Disruption**| Malware or unauthorized access disrupts SOE's functionality, halting operations. | Operational data      | Medium         | High            | **High**            |
| **Compliance Violations** | Breach of patient data results in privacy regulation violations (e.g., GDPR, HIPAA). | PII, medical records  | Medium         | Very High       | **High**            |