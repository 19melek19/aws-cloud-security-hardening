# Security Controls and Compliance Mapping

## Defense-in-Depth Strategy

The project implements complementary security controls across the network, authentication and operating system layers.

## Security Control Classification

| Control | Classification | Objective |
|---|---|---|
| AWS VPC | Preventive | Network isolation |
| Security Groups | Preventive | Restrict network access |
| SSH key authentication | Preventive | Secure remote administration |
| Fail2Ban | Detective and preventive | Monitor authentication failures and support blocking |
| Auditd | Detective | Record security-relevant events |
| AIDE | Detective | Detect filesystem modifications |
| Nmap | Assessment | Evaluate network exposure |

## CIA Triad

| Principle | Supporting Controls |
|---|---|
| Confidentiality | Security Groups and SSH authentication |
| Integrity | AIDE and Auditd |
| Availability | Network access restriction and Fail2Ban |

## NIST SP 800-53 Control Mapping

| Control Reference | Description | Supporting Implementation |
|---|---|---|
| AC-3 | Access Enforcement | AWS Security Groups |
| AC-17 | Remote Access | SSH hardening |
| IA-2 | Identification and Authentication | SSH key authentication |
| AC-7 | Unsuccessful Logon Attempts | Fail2Ban |
| AU-2 | Event Logging | Auditd |
| AU-12 | Audit Record Generation | Auditd |
| SI-7 | Software, Firmware, and Information Integrity | AIDE |
| SC-7 | Boundary Protection | VPC and Security Groups |

## Compliance Limitations

This mapping illustrates how the implemented controls relate to selected NIST security requirements.

It does not represent a formal compliance audit, certification or complete implementation of NIST SP 800-53.

## Future Improvements

- AWS IAM least-privilege policies.
- AWS CloudTrail.
- Amazon CloudWatch.
- AWS GuardDuty.
- AWS KMS encryption.
- Centralized security monitoring.
- Infrastructure as Code using Terraform.
- Automated compliance assessment.
