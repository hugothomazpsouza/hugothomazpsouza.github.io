# [DOCUMENTATION OR PROCEDURE TITLE]

> 📅 **Date:** YYYY-MM-DD | ✍️ **Author:** Hugo Souza | 🏷️ **Version:** 1.0.0

[![Status](https://img.shields.io/badge/Status-Under_Review-yellow?style=flat-square)](#)

## 🎯 Objective

[Briefly describe the objective of this technical procedure or document. What will be possible to achieve or conclude after reading it?]

## 📋 Prerequisites

- [ ] Administrator/Root access on the target infrastructure.
- [ ] Understanding and prior knowledge of Y.
- [ ] CLI tools that must be installed (e.g., `terraform`, `aws-cli`).

---

## 🏗️ Architecture

> _(Insert the diagram representing the deployed topology or architecture below)_  
> `![Architecture Diagram](../../assets/diagrams/placeholder.png)`

---

## 🚀 Step by Step

### 1. [First Step of the Procedure]

Subtitle to organize the process and a clear instruction of the first action to be taken.

```bash
# Commands needed in this step (avoid long texts, show the practice)
aws ec2 describe-instances --region us-east-1
```

### 2. [Second Step of the Procedure]

Describe the second step concisely.

> ⚠️ **Attention:** In a production environment, make sure to perform tests during an approved maintenance window before executing the following changes.

```python
# Validation script (if any)
def test_connectivity():
    print("Testing...")
```

---

## 🔧 Troubleshooting

If the steps do not go as expected, check the common issues table:

| Symptom                          | Probable Cause                     | Recommended Solution                                            |
| -------------------------------- | ---------------------------------- | --------------------------------------------------------------- |
| Ping Timeout (ICMP)              | Security Group / Firewall blocking | Allow ICMP Echo Request port/protocol                           |
| Failed to establish BGP Neighbor | Mismatched secret or incorrect AS  | Replace the password on the on-premises router and Cloud Router |

---

## 📚 Official References

- [🔗 AWS Documentation - VPC](https://docs.aws.amazon.com/vpc/)
- [🔗 RFC #4271 (A Border Gateway Protocol 4)](https://datatracker.ietf.org/doc/html/rfc4271)

[⬅️ Back to Index](../README.md)
