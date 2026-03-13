---
layout: post
title: "Transmission Time Calculation: How Long Does It Take to Send a File?"
date: 2026-03-12
author: Hugo Souza
tags: [Networking, Tutorials, Basics]
reading_time: "3 min read"
---

# Transmission Time Calculation: How Long Does It Take to Send a File?

> ⏱️ **Estimated time:** 3 min | 🏷️ **Tags:** `#Networking` `#Theory` `#Transmission`

## 📖 Summary

This is a transmission time calculation. It shows how long it takes to send a file (an image, in this case) over a connection with a specific speed.

---

## 1. The Step-by-Step Calculation

Here is the simplified step-by-step:

**File Size**: The image is 25 Megabytes (MB). Since network speed is measured in bits, we first convert bytes to bits by multiplying by 8 (since 1 byte = 8 bits).
_25 MB × 8 = 200 Megabits (Mb)_ (_200,000,000 bits_.

**Network Speed (Bandwidth)**: The connection is 10 Mbps (Megabits per second).
_10 Mbps = 10,000,000 bits per second_.

**The Final Math**: You divide the total bits by the speed:
_200,000,000 / 10,000,000 = 20 seconds_.

In short: If you have a file made of 200 million 'pieces' and you can send 10 million per second, it will take you 20 seconds to finish the transfer.

---

## 2. The Prefix Staircase

Here is the logic of the 'staircase':

- **Kilo (K)** = 10³ (1,000) — Thousand.
- **Mega (M)** = 10⁶ (1,000,000) — Million.
- **Giga (G)** = 10⁹ (1,000,000,000) — Billion.
- **Tera (T)** = 10¹² (1,000,000,000,000) — Trillion.

---

## 3. Other Examples

### Example 1: 500 GB File over a 1 Gbps Link

**File Size in Bits:**
A 500 GB (Gigabyte) file needs to be converted to bits by multiplying by 8.
_500 GB × 8 = 4,000 Gigabits (Gb)_ (or _4,000,000,000,000 bits_).

**Network Speed (Bandwidth):**
The connection speed is 1 Gbps (1 Gigabit per second).
_1 Gbps = 1,000,000,000 bits per second_.

**The Final Math:**
Divide the total bits by the network speed:
_4,000 Gb / 1 Gbps = 4,000 seconds_ (approx. 1 hour and 6 minutes).

### Example 2: 1 TB File over a 10 Gbps Link

**File Size in Bits:**
A 1 TB (Terabyte) file is 1,000 GB. Multiply by 8 to get the bits.
_1,000 GB × 8 = 8,000 Gigabits (Gb)_ (or _8,000,000,000,000 bits_).

**Network Speed (Bandwidth):**
The connection speed is 10 Gbps (10 Gigabits per second).
_10 Gbps = 10,000,000,000 bits per second_.

**The Final Math:**
Divide the total bits by the network speed:
_8,000 Gb / 10 Gbps = 800 seconds_ (exactly 13 minutes and 20 seconds).

---

[⬅️ Back to articles list](../blog/README.md)
