# Threat Modelling Workshop

## Introduction
A 3-hour threat modelling workshop was conducted to evaluate the potential threats against SOE, a dentistry-focused application used for managing sensitive patient details such as phone numbers, addresses, emails, and other personal data.

## Attendees
- Dental Practice IT Team
- Product Managers
- Security Engineers
- DevSecOps Team

## Scope
Four scenarios were explored, covering:
1. Phishing email targeting admin credentials to access patient records.
2. Unauthorized access to patient data via a brute force or credential stuffing attack.
3. SQL Injection targeting the database where patient information is stored.
4. Insider threat involving malicious activity by a staff member accessing sensitive patient records.

## Methodology
Each scenario was assessed using the cyber attack kill chain, MITRE ATT&CK framework, and STRIDE to identify potential gaps in security controls and to determine the associated risks.

## Conclusion
The workshop identified:
- **Scenario 1 (Phishing Attack):** Exposed vulnerabilities that could lead to unauthorized access to patient records. **2 High-risk issues** were identified:
  - **High Risk 1:** Compromised admin credentials leading to unauthorized access to patient data.
  - **High Risk 2:** Spread of malware or ransomware, disrupting system operations.

- **Scenario 2 (Credential Theft):** A brute force attack simulation highlighted weaknesses in password policies. **1 High-risk issue** was identified:
  - **High Risk:** Lack of strong password enforcement, increasing exposure to credential-based attacks.

- **Scenario 3 (SQL Injection):** Demonstrated the need for stricter input validation and query sanitization. **1 High-risk issue** and **1 Medium-risk issue** were identified:
  - **High Risk:** Vulnerability to SQL injection attacks that could expose patient data.
  - **Medium Risk:** Lack of robust monitoring for database queries.

- **Scenario 4 (Insider Threat):** Highlighted insufficient RBAC policies. **1 High-risk issue** was identified:
  - **High Risk:** Unauthorized access to sensitive data by a malicious insider.

In total, **5 High-risk areas** and **2 Medium-risk areas** were identified, requiring action and monitoring.

## Controls Required
- Conduct regular security audits of the SOE system to uncover vulnerabilities in software and configurations.
- Implement robust patch management to ensure the SOE system and supporting technologies are up-to-date against known vulnerabilities.
- Roll out comprehensive staff training on phishing awareness to help users identify and report suspicious emails or activity.
- Deploy a Web Application Firewall (WAF) configured to SOE's specific requirements to block malicious web traffic.
- Enforce Multi-factor Authentication (MFA) for all user logins to protect patient data from unauthorized access.
- Enable continuous monitoring of network and application logs for suspicious activity in the SOE system.
- Introduce Role-based Access Control (RBAC) to ensure that only authorized users can access sensitive patient data and perform critical actions.

## Threat Modelling Process Summary
```mermaid
mindmap
  root((SOE Threat Modelling))
    STRIDE/MITRE/Kill Chain
      Inherent Risk Assessment
      ::icon(fa fa-book)
      Critical Asset List
        Patient Records
        Sensitive Contact Information
        System Credentials
        Admin Interfaces
    Controls Required
      Risks<br/>Mitigations
      Risk Summary
        Remediation Workflow
            SOE Alerts
            JIRA Tickets
    Scenarios
      Phishing Attack
        High Risk 1
        High Risk 2
      Credential Theft
        High Risk 1
      SQL Injection
        High Risk 1
        Medium Risk 1
      Insider Threat
        High Risk 1