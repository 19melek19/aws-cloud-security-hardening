# SSH Authentication Hardening

## Objective

Protect remote administration against unauthorized access and password-based authentication attacks.

## Implemented Security Controls

- SSH public-key authentication.
- Disabled password authentication.
- Restricted network access through AWS Security Groups.

## Reference Configuration

Configuration file: /etc/ssh/sshd_config

```text
PubkeyAuthentication yes
PasswordAuthentication no
PermitRootLogin no
KbdInteractiveAuthentication no
```

These settings represent a recommended hardened configuration.
The exact original configuration file is unavailable.

## Verification Commands

```bash
sudo sshd -t
sudo sshd -T
sudo systemctl status ssh
sudo journalctl -u ssh --no-pager -n 30
```

## Historical Validation

An unauthorized SSH authentication attempt returned:

```text
Permission denied (publickey).
```

The server also recorded an invalid username in its authentication logs.

## Security Benefits

- Reduced password-based attack risk.
- Stronger administrator authentication.
- Improved authentication accountability.

## Operational Precautions

Validate the configuration and maintain an existing administrative session before applying SSH configuration changes.
