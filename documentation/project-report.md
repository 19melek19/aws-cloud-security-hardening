# Securing a Public Cloud Server: An AWS EC2 Case Study

## Abstract

Cloud computing introduces security challenges related to network exposure, authentication, unauthorized access and system integrity.

This project demonstrates a defense-in-depth approach to securing an AWS EC2 Linux server through network hardening, secure authentication, intrusion prevention, security auditing and file integrity monitoring.

## 1. Introduction

Public cloud infrastructure requires security controls at both the cloud infrastructure and operating system levels.

The project evaluates the initial security posture of an EC2 instance and implements complementary controls to reduce security risks.

## 2. Project Objectives

- Deploy a Linux server on AWS.
- Establish isolated cloud networking.
- Identify exposed services.
- Reduce the external attack surface.
- Strengthen remote authentication.
- Monitor authentication failures.
- Audit sensitive system modifications.
- Verify filesystem integrity.

## 3. Technical Environment

| Component | Technology |
|---|---|
| Cloud provider | AWS |
| Cloud region | eu-central-1 |
| Compute | Amazon EC2 |
| Network | Amazon VPC |
| Operating system | Ubuntu Linux |
| Web server | Nginx |
| Validation environment | Kali Linux |
| Assessment | Nmap |
| Authentication | OpenSSH |
| Intrusion prevention | Fail2Ban |
| Security auditing | Auditd |
| Integrity monitoring | AIDE |

## 4. Methodology

The project followed five main phases:

1. Cloud infrastructure deployment.
2. Initial security assessment.
3. Implementation of security controls.
4. Security validation.
5. Documentation and evaluation.

## 5. Cloud Infrastructure

A dedicated AWS VPC was configured with public and private subnets.

An Internet Gateway and route table provided connectivity for public-facing resources.

An Ubuntu EC2 instance hosted an Nginx web server.

AWS Security Groups were used to control network access.

## 6. Threat Model

The project considered the following security risks:

- Unauthorized network access.
- Unnecessary service exposure.
- Password-based authentication attacks.
- Unauthorized system modifications.
- Insufficient security monitoring.

## 7. Security Implementation

### 7.1 Network Hardening

Security Group policies were restricted to reduce unnecessary external access.

### 7.2 Authentication Hardening

SSH key-based authentication was implemented and password authentication was disabled.

### 7.3 Intrusion Prevention

Fail2Ban was configured to monitor SSH authentication failures and support temporary IP blocking.

### 7.4 Security Auditing

Auditd was configured to monitor modifications to sensitive system files and authentication logs.

### 7.5 File Integrity Monitoring

AIDE was used to establish a filesystem integrity baseline and identify subsequent changes.

## 8. Evaluation Results

| Security Area | Observed Result |
|---|---|
| Network exposure | Tested external ports became filtered |
| Authentication | Unauthorized SSH authentication rejected |
| Intrusion prevention | SSH authentication failures monitored |
| Auditing | Audit rules successfully loaded |
| File integrity | Filesystem changes detected |

## 9. Limitations

The assessment was conducted in an academic environment.

The original configuration files and screenshots are unavailable.

The historical results do not demonstrate complete protection against all cloud security threats.

Fail2Ban IP blocking was not confirmed in the available results.

AIDE detected changes that included expected modifications to dynamic system files.

## 10. Future Work

Future improvements include:

- Infrastructure automation using Terraform.
- Centralized logging and monitoring.
- AWS IAM security assessment.
- AWS CloudTrail integration.
- AWS GuardDuty integration.
- Encryption using AWS KMS.
- Automated CIS benchmark assessment.

## 11. Conclusion

The project demonstrates how defense in depth can improve the security posture of a public cloud server.

Combining cloud network controls with operating system security mechanisms provides stronger authentication, reduced network exposure and improved security visibility.

## References

- AWS Documentation: https://docs.aws.amazon.com/
- Ubuntu Server Documentation: https://documentation.ubuntu.com/server/
- Nmap Documentation: https://nmap.org/docs.html
- Fail2Ban: https://github.com/fail2ban/fail2ban
- Linux Audit: https://github.com/linux-audit/audit-userspace
- AIDE: https://aide.github.io/
- NIST SP 800-53: https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final

## Reconstruction Notice

This report reconstructs a previously implemented academic project from historical project records.
It is not a newly executed security assessment.
