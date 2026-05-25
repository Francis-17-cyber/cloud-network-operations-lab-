# Core Network Design & IP Schema

## Network Topology Overview
This section outlines the baseline IP addressing scheme for the hybrid cloud environment, mapping out local sandbox subnets and AWS Virtual Private Cloud (VPC) space.

---

## IP Addressing Plan (IPv4)

| Network Zone | Subnet / CIDR Block | Purpose / Description |
| :--- | :--- | :--- |
| **AWS VPC Corporate** | `10.0.0.0/16` | Main cloud infrastructure block |
| **Public Subnet (DMZ)** | `10.0.1.0/24` | External facing resources / NAT Gateways |
| **Private App Subnet** | `10.0.2.0/24` | Internal backend resources |
| **On-Prem Sandbox** | `192.168.10.0/24` | Local simulated corporate office |

---

## Routing & Security Policies
* **Default Route:** All outbound traffic from private zones must clear through a secure NAT Gateway.
* **Access Control:** Inter-subnet traffic is strictly restricted via Network ACLs (NACLs) and Security Groups.