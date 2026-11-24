# Cloud Security Architecture

## Defense-in-Depth Architecture

```mermaid
flowchart TD
    A[Authorized Administrator]
    B[Kali Linux Validation Environment]

    subgraph AWS["AWS Cloud - eu-central-1"]
        subgraph VPC["VPC - 10.0.0.0/16"]
            IGW[Internet Gateway]
            SG[AWS Security Group]

            subgraph PUBLIC["Public Subnet - 10.0.1.0/24"]
                EC2[Ubuntu EC2 Instance]
                SSH[SSH Key Authentication]
                NGINX[Nginx Web Server]
                F2B[Fail2Ban]
                AUDIT[Auditd]
                AIDE[AIDE]
            end

            subgraph PRIVATE["Private Subnet - 10.0.2.0/24"]
                RESERVED[Isolated Network Segment]
            end

            IGW --> SG
            SG --> EC2
            EC2 --> SSH
            EC2 --> NGINX
            EC2 --> F2B
            EC2 --> AUDIT
            EC2 --> AIDE
        end
    end

    A --> IGW
    B --> IGW
```

## Security Layers

1. Network isolation using Amazon VPC.
2. Network access control using AWS Security Groups.
3. Secure authentication using SSH keys.
4. Authentication monitoring using Fail2Ban.
5. System auditing using Auditd.
6. File integrity monitoring using AIDE.

## Architecture Status

This diagram represents the reconstructed historical project architecture.
It is not a live AWS infrastructure inventory.
