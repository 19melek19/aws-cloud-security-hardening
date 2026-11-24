# Security Assessment Before Hardening

## Objective

Identify the initial attack surface of the AWS EC2 instance.

## Assessment Environment

- Target: Authorized AWS EC2 instance
- Testing environment: Kali Linux
- Assessment tool: Nmap

## Historical Results

| Port | State | Service | Detected Software |
|---|---|---|---|
| 22/tcp | Open | SSH | OpenSSH 9.6p1 Ubuntu |
| 80/tcp | Open | HTTP | Nginx 1.24.0 |
| 443/tcp | Filtered | HTTPS | Not detected |

## Identified Security Risks

- Unnecessary external network exposure.
- Remote service version disclosure.
- Potential unauthorized authentication attempts.
- Insufficient security monitoring.
- Lack of established file integrity monitoring.

## Risk Mitigation Strategy

- Restrict inbound traffic using AWS Security Groups.
- Enforce SSH key-based authentication.
- Implement authentication monitoring.
- Enable system auditing.
- Establish a filesystem integrity baseline.

## Evidence Status

These results are reconstructed from historical project records.
The original assessment screenshots are unavailable.
