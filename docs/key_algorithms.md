---
title: "key_algorithms"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/key_algorithms.html"
last_updated: "8/28/2024"
product_version: "8.3.0.2201"
---


In this article

Veeam Backup for Microsoft 365 supports the following key algorithms: RSA, DSA, ECDSA, EdDSA (ED25519). For these algorithms you can use the following key formats:

| Key Formats | Key Algorithms | | | |
| --- | --- | --- | --- | --- |
| RSA | DSA | ECDSA | EdDSA (ED25519) |
| PEM | ✔ | ✔ | ✔ |  |
| private | ✔ | ✔ | ✔ | ✔ |
| private-openssh | ✔ | ✔ | ✔ |  |
| sshcom | ✔ | ✔ |  |  |
| PKCS8 | ✔ |  | ✔ |  |
| RDC4716 (private-openssh-new) | ✔ | ✔ | ✔ | ✔ |

Page updated 8/28/2024

Page content applies to build 8.3.0.2201
