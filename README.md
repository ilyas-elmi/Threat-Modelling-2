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
- **5 High-risk areas** requiring immediate action.
- **2 Medium-risk areas** requiring monitoring and mitigation.

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
  root((attack))
    STRIDE/MITRE/Kill Chain
      Inherent Risk Assesment
      ::icon(fa fa-book)
      Critical Asset List
        Schedule and Scope Workshop
    Controls Required
      Risks<br/>Mitigations
      Risk Summary
        Remediation workflow
            Email Alerts
            JIRA Tickets
    Scenarios
      Phishing Attack
      Credential Theft
      SQL Injection
      Insider Threat