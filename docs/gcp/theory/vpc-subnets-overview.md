# VPC Subnets - Complete Study Guide

> 📅 **Date:** 2026-02-24 | ✍️ **Author:** Hugo Souza | 🏷️ **Version:** 1.0.0

[![Status](https://img.shields.io/badge/Status-Study_Guide-blue?style=flat-square)](#)

## 🎯 Objective

This guide summarizes the most important concepts regarding **VPC Subnets** in Google Cloud Platform. It serves as a rapid review material for the **Professional Cloud Network Engineer** certification.

---

## 🏗️ 1. Core Concepts

- **Regional Resources:** Subnets (or subnetworks) are regional resources. A single VPC network (global) consists of one or more subnets.
- **Implicit Region Selection:** When you create a resource in a zone (e.g., a VM instance), you implicitly select its parent region. The selected network must have a subnet available in that region.
- **Auto vs. Custom Mode:**
  - **Auto mode:** Automatically creates a subnet in each region.
  - **Custom mode:** Starts with no subnets; gives you full control and allows you to create more than one subnet per region.
- **Naming:** Subnet names must be unique within a region for a given project. You cannot change the name or region of a subnet after creation (you must delete and recreate it).

---

## 🌐 2. Types and Purposes of Subnets

### Stack Types

VPC networks support subnets with three stack types:

1. **IPv4-only (single-stack)**
2. **IPv4 and IPv6 (dual-stack)**
3. **IPv6-only (single-stack)**

> **Note:** Subnets with IPv6 ranges are supported on **custom mode** VPC networks only. You can change IPv4-only to dual-stack, or change a dual-stack (with external IPv6) back to IPv4-only. You cannot change the access type (internal or external) of an IPv6 subnet once created.

### Subnet Purposes

Subnets are assigned a "purpose", which generally cannot be changed after creation:

- **Regular (PRIVATE/NONE):** Default type for VM instances.
- **Private Service Connect:** Subnet used to publish managed services via PSC.
- **Proxy-only:** Used with regional Envoy-based load balancers.
- **Private NAT:** Reserved as the source range for Private NAT.
- **Peer migration:** Used to migrate a Shared VPC service to PSC.
- **Hybrid:** Logically extends to an on-premises network to migrate workloads without changing IPs.

---

## 🔢 3. IPv4 Subnet Ranges

### Rules & Limitations

- **Minimum Size:** `/29` (8 addresses).
- **Maximum Size:** `/4` (though `/8` is the recommended max limit due to validation rules against reserved blocks).
- **Expansion:** You can expand a primary IPv4 range, but you cannot replace or shrink it.
- **Overlaps:** Cannot overlap with any allocated range, peer network ranges, or static routes. If connecting via VPN/Interconnect, ranges must not conflict with on-prem IP logic.
- **Avoid `10.128.0.0/9`:** This block is used by Auto mode VPCs. Using it for custom subnets breaks future VPC Peering or VPNs to auto mode networks.
- **Restricted Ranges:** Cannot use Google public IPs, Multicast (`224.0.0.0/4`), Link-local (`169.254.0.0/16`), Local host (`127.0.0.0/8`), or Broadcast (`255.255.255.255/32`).

### Unusable IPv4 Addresses

In every primary IPv4 subnet, **4 addresses are unusable**:

1. **Network Address:** First address (e.g., `10.1.2.0`).
2. **Default Gateway:** Second address (e.g., `10.1.2.1`). Note: Virtual gateways do not respond to ping.
3. **Second-to-last Address:** Reserved by Google for potential future use (e.g., `10.1.2.254`).
4. **Broadcast Address:** Last address (e.g., `10.1.2.255`).

_(Note: Secondary IP ranges do not have a reserved virtual gateway)._

---

## 🔤 4. IPv6 Subnet Ranges

IPv6 addresses can be assigned as **Internal** or **External**.

- **Internal (ULAs):** Routable only within VPC networks. Not internet routable. Assigned an unused `/64` from the VPC network's `/48` ULA range.
- **External (GUAs):** Routable within the VPC and on the Internet. Supplied by Google's regional pools or Bring Your Own IP (BYOIP).

### Assignment Sizes

- **VPC Network:** `/48` range.
- **Subnet:** `/64` range. (For external, the first `/65` is for VMs, the second `/65` is for Cloud Load Balancing).
- **VM Instance / Forwarding Rules:** `/96` range.

### Unusable IPv6 Addresses

For Internal IPv6 subnets, Google Cloud reserves two `/96` ranges for system use:

1. **First `/96` range:** e.g., `fd20:db8::/96` from range `fd20:db8::/64`.
2. **Last `/96` range:** e.g., `fd20:db8:0:0:ffff:ffff::/96` from range `fd20:db8::/64`.

---

## 📚 Official References

- [🔗 Google Cloud Subnets Documentation](https://cloud.google.com/vpc/docs/subnets)
- [🔗 Professional Cloud Network Engineer Exam Guide](https://cloud.google.com/certification/guides/cloud-network-engineer)

[⬅️ Back to GCP Index](../README.md)
