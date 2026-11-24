# Linux Security Auditing with Auditd

## Objective

Monitor sensitive system files and maintain security audit records for incident investigation.

## Installation Reference

```bash
sudo apt update
sudo apt install auditd audispd-plugins -y
sudo systemctl enable --now auditd
```

## Historical Audit Rules

```text
-w /etc/passwd -p wa -k passwd_changes
-w /etc/shadow -p wa -k shadow_changes
-w /var/log/auth.log -p wa -k authlog
```

## Rule Explanation

| Parameter | Meaning |
|---|---|
| -w | Watch a filesystem path |
| -p w | Monitor write operations |
| -p a | Monitor attribute changes |
| -k | Assign an audit search key |

## Persistent Configuration Reference

Audit rules can be stored in:

/etc/audit/rules.d/security.rules

The authentication log path must exist before configuring its watch rule.

## Verification Commands

```bash
sudo auditctl -l
sudo systemctl status auditd
sudo ausearch -k passwd_changes -i
sudo ausearch -k shadow_changes -i
sudo ausearch -k authlog -i
```

## Historical Validation

The audit rules were loaded and verified using auditctl.

## Security Benefits

- Monitoring sensitive system modifications.
- Improved incident investigation.
- Security event traceability.
- Support for compliance assessments.

## Limitations

Auditd records events but does not automatically prevent all unauthorized modifications.
