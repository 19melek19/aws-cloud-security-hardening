# Security Assessment After Hardening

## Objective

Evaluate the effectiveness of the implemented security controls.

## Network Assessment

| Port | Before Hardening | After Hardening |
|---|---|---|
| 22/tcp | Open | Filtered |
| 80/tcp | Open | Filtered |
| 443/tcp | Filtered | Filtered |

The results were observed from an external validation source.

## SSH Authentication

Unauthorized authentication was rejected with:

Permission denied (publickey).

Password-based SSH authentication was disabled.

## Fail2Ban Validation

- SSH jail active.
- Authentication failures recorded.
- Automated blocking capability configured.
- Actual IP banning was not confirmed.

## Auditd Validation

Audit rules were loaded for:

- /etc/passwd
- /etc/shadow
- /var/log/auth.log

## AIDE Validation

| Metric | Result |
|---|---|
| Added entries | 0 |
| Removed entries | 1 |
| Changed entries | 9 |

Detected changes included dynamic system files and logs.
These results do not independently establish a security compromise.

## Conclusion

The assessment demonstrated reduced network exposure, stronger authentication, security monitoring and filesystem integrity verification.

## Evidence Status

Historical results reconstructed from previous project records.
No new live assessment was performed during repository reconstruction.
