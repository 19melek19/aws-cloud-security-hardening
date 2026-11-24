# Amazon EC2 Instance

## Overview

An Amazon EC2 instance was deployed to host an Nginx web server and implement Linux security controls.

## Environment

| Component | Configuration |
|---|---|
| Cloud Provider | Amazon Web Services |
| Service | Amazon EC2 |
| Region | eu-central-1 |
| Operating System | Ubuntu Linux |
| Web Server | Nginx |
| Remote Administration | OpenSSH |
| Authentication | SSH key pair |
| Validation Environment | Kali Linux |

## Software Components

- Nginx
- OpenSSH
- Fail2Ban
- Auditd
- AIDE

## Security Objectives

- Secure remote administration.
- Minimize exposed services.
- Monitor authentication events.
- Audit sensitive system modifications.
- Detect filesystem integrity changes.

## Verification Commands

```bash
cat /etc/os-release
hostnamectl
systemctl status nginx
systemctl status ssh
systemctl status fail2ban
systemctl status auditd
```

## Security Considerations

SSH private keys must be stored securely.
AWS credentials and sensitive instance information must not be committed to GitHub.

## Documentation Status

The original deployment used Ubuntu Linux.
Ubuntu 22.04 was referenced during initial deployment and Ubuntu 24.04 during later validation.
The exact final AMI identifier and instance type require verification.
