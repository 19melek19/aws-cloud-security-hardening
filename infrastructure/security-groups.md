# AWS Security Groups

## Overview

AWS Security Groups provide stateful network access control for EC2 instances.

## Initial Network Exposure

| Port | Protocol | Service | Observed State |
|---|---|---|---|
| 22 | TCP | SSH | Open |
| 80 | TCP | HTTP | Open |
| 443 | TCP | HTTPS | Filtered |

## Hardening Strategy

- Restrict SSH access to authorized administrative IP addresses.
- Remove unnecessary inbound rules.
- Apply the principle of least privilege.
- Permit web traffic only when required.
- Review inbound and outbound access policies.

## Recommended Inbound Policy

| Port | Service | Authorized Source |
|---|---|---|
| 22 | SSH | Administrator IP/32 |
| 80 | HTTP | Only when required |
| 443 | HTTPS | Only when required |
| Other ports | Other services | No inbound rule by default |

## Historical Validation Results

| Port | Before Hardening | After Hardening |
|---|---|---|
| 22 | Open | Filtered |
| 80 | Open | Filtered |
| 443 | Filtered | Filtered |

The post-hardening results were observed from an external test source.

## Security Benefits

- Reduced attack surface.
- Restricted remote administration.
- Reduced unauthorized service access.
- Network-level defense in depth.

## Limitations

Filtered ports do not mean the public IP address is invisible.
Authorized sources may still access permitted services.
The exact historical Security Group rules are not available.
