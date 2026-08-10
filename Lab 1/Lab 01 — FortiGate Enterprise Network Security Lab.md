# Lab 01 — FortiGate Enterprise Network Security Lab

A hands-on enterprise network security lab built with **FortiGate and PNETLab**, focusing on network segmentation, inter-VLAN routing, stateful firewall policy enforcement, controlled Internet access, and practical troubleshooting.

## Overview

This lab simulates a segmented enterprise network where the FortiGate acts as the central Layer 3 security boundary between multiple user and server VLANs.

The environment demonstrates how network segmentation and firewall policies can be combined to control both **North-South Internet traffic** and **East-West internal traffic**.

The lab also includes a real troubleshooting scenario involving an incorrect upstream gateway configuration and the process used to identify and resolve the issue.

## Architecture

The lab consists of multiple logical network segments connected through a VLAN trunk to the FortiGate.

### Main Components

- FortiGate Firewall
- Layer 2 Switch
- PNETLab virtual environment
- Multiple endpoint VLANs
- Server VLAN
- WAN / Internet connection

### Network Segmentation

| Segment | Purpose |
|---|---|
| HR | Human Resources users |
| Sales | Sales users |
| IT | IT / administrative users |
| Server | Internal server resources |
| WAN | External / Internet connectivity |

The FortiGate terminates the VLAN interfaces and provides:

- Inter-VLAN routing
- DHCP services
- Firewall policy enforcement
- Network segmentation
- Internet access control
- Source NAT for outbound traffic

## Security Design

The security model follows a **least-privilege and segmentation-oriented approach**.

Key controls implemented in the lab include:

- VLAN-based network segmentation
- Centralized Layer 3 routing through FortiGate
- Stateful firewall policies
- Explicit access control between internal segments
- Restricted access to the Server VLAN
- Controlled Internet access
- Source NAT for outbound Internet traffic
- Policy ordering and explicit deny rules

The intended result is that different user groups do not receive unrestricted access to internal resources.

## Traffic Control

Examples of the implemented security model include:

| Traffic Flow | Intended Result |
|---|---|
| HR → Server | Denied |
| Sales → Server | Denied |
| IT → Server | Allowed for required access |
| User VLANs → Internet | Allowed through controlled outbound access |
| Internal traffic between protected segments | Controlled by FortiGate policies |

Actual verification status is documented in the main lab documentation and is not assumed from configuration alone.

## Troubleshooting

One of the main engineering scenarios in this lab involved an Internet connectivity failure.

The issue was investigated through a layered troubleshooting process rather than assuming the FortiGate configuration was the root cause.

The investigation ultimately identified an incorrect upstream/default gateway configuration.

The troubleshooting workflow followed:

**Connectivity Failure → Investigation → Gateway Verification → Root Cause Identification → Configuration Correction → Connectivity Validation**

This scenario demonstrates practical troubleshooting of the interaction between the firewall, upstream network, and Internet connectivity.

## Validation

The lab includes validation of:

- VLAN connectivity
- Inter-VLAN access control
- Firewall policy behavior
- Internet connectivity
- Network isolation
- DHCP operation
- Routing and NAT behavior

Where application-level validation or additional evidence was not independently captured, the main documentation explicitly identifies it as unverified rather than treating configuration as proof of successful operation.

## Technologies

- FortiGate
- FortiOS
- PNETLab
- VLANs
- IEEE 802.1Q
- Inter-VLAN Routing
- DHCP
- Static Routing
- NAT
- Stateful Firewall Policies
- Network Segmentation

## Documentation

Detailed implementation steps, configuration evidence, screenshots, troubleshooting analysis, and validation results are available in the project documentation:

**[FortiGate Enterprise Network Security Lab Documentation](./Documentation/FortiGate_PNETLab_Enterprise_Security_Lab.docx)**

## Lab Status

**Status:** Completed — Foundation Lab

This lab serves as the first stage of a growing Fortinet security lab portfolio.

Future labs will extend the environment with deeper security and infrastructure capabilities such as:

- Site-to-Site IPsec VPN
- Advanced firewall security
- Authentication and identity integration
- FortiAnalyzer / centralized logging
- Additional Fortinet security products and integrations

---

### Author

**Cybersecurity / Network Security Lab Portfolio**

Built and documented as a practical Fortinet security engineering project.