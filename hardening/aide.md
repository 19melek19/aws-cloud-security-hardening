# AIDE File Integrity Monitoring

## Objective

Detect unexpected filesystem modifications through baseline comparison.

## Technology

AIDE stands for Advanced Intrusion Detection Environment.

## Installation Reference

```bash
sudo apt update
sudo apt install aide -y
```

## Configuration File

/etc/aide/aide.conf

## Baseline Initialization

```bash
sudo aideinit
```

The generated database must be reviewed and activated according to the installed AIDE package configuration.

## Integrity Verification

```bash
sudo aide --check --config=/etc/aide/aide.conf
```

## Historical Validation Results

The integrity check reported:

```text
Added entries:   0
Removed entries: 1
Changed entries: 9
```

## Interpretation

AIDE detected differences between the baseline database and the current filesystem.

Several changes were associated with dynamic system files and logs, including audit logs and system service data.

These differences do not independently prove that the system was compromised.

## Security Benefits

- File integrity verification.
- Detection of unexpected modifications.
- Support for incident investigation.
- Improved system security visibility.

## Limitations

- Integrity checks can consume CPU resources.
- Dynamic files may generate expected alerts.
- Baselines must be generated from a trusted system state.
- Detected changes require investigation.
