# Fail2Ban Intrusion Prevention

## Objective

Monitor SSH authentication failures and provide automated IP-based blocking.

## Installation Reference

```bash
sudo apt update
sudo apt install fail2ban -y
sudo systemctl enable --now fail2ban
```

## Recommended Configuration

Configuration file: /etc/fail2ban/jail.local

```ini
[sshd]
enabled = true
port = ssh
backend = systemd
maxretry = 5
findtime = 600
bantime = 3600
```

These thresholds are reconstructed recommendations rather than recovered original values.

## Verification Commands

```bash
sudo systemctl status fail2ban
sudo fail2ban-client status
sudo fail2ban-client status sshd
```

## Historical Validation Results

The SSH jail was active and authentication failures were recorded.

Reconstructed historical status:

```text
Jail list: sshd

Currently failed: 1
Total failed: 2
Currently banned: 0
Total banned: 0
```

## Interpretation

Fail2Ban successfully monitored authentication failures.
An actual IP ban was not confirmed in the available historical results.

## Security Benefits

- Automated authentication monitoring.
- Configurable temporary IP blocking.
- Additional protection against repeated authentication failures.
