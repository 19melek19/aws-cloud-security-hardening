# AWS Virtual Private Cloud (VPC)

## Overview

A dedicated VPC was created to provide network isolation for the cloud infrastructure.

## Network Configuration

| Component | Configuration |
|---|---|
| AWS Region | eu-central-1 (Frankfurt) |
| VPC CIDR | 10.0.0.0/16 |
| Public Subnet | 10.0.1.0/24 |
| Private Subnet | 10.0.2.0/24 |
| Internet Gateway | Attached to VPC |
| Public Route | 0.0.0.0/0 via Internet Gateway |

## Architecture

- The public subnet provides connectivity for public-facing resources.
- The private subnet provides an isolated network segment.
- The Internet Gateway enables internet connectivity.
- Route tables control network traffic forwarding.
- Security Groups restrict access to EC2 instances.

## Security Benefits

- Network segmentation.
- Resource isolation.
- Controlled internet connectivity.
- Reduced unnecessary network exposure.

## Documentation Status

This configuration is reconstructed from historical project records.
Original AWS resource identifiers are not included.
