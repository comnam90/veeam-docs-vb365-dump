---
title: "General Security Considerations"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_general_security_considerations.html"
last_updated: "3/3/2026"
product_version: "8.3.0.2201"
---

# General Security Considerations


General security considerations include best practices which help you to harden Veeam Backup for Microsoft 365 infrastructure, build a more secure environment, and mitigate risks of being compromised. Ensure that your infrastructure meets the common recommendations described in this section. For more information about hardening specific Veeam Backup for Microsoft 365 components, see [Securing Veeam Backup for Microsoft 365 Infrastructure](vbo_securing_infrastructure.md).

Network

To secure the communication channel for network traffic, consider the following recommendations:

* Create network segmentation policies to define network boundaries, control traffic between subnets and limit access to security-sensitive Veeam Backup for Microsoft 365 components.
* Make sure that only ports used by Veeam Backup for Microsoft 365 components are opened. For more information, see [Ports](vbo_used_ports.md).
* Use an isolated network to transport data between Veeam Backup for Microsoft 365 components.

* Disable outdated network protocols:

* SSL 2.0 and 3.0 as they have well-known security vulnerabilities and are not NIST-approved. For more information, see [NIST guidelines](https://csrc.nist.gov/publications/detail/sp/800-52/rev-2/final).

* TLS 1.0 and 1.1 if they are not needed. For more information, see [NIST guidelines](https://csrc.nist.gov/publications/detail/sp/800-52/rev-2/final).

* LLMNR and NetBIOS broadcast protocols to prevent spoofing and man-in-the-middle (MITM) attacks.

* SMB 1.0 protocol as it has a number of serious security vulnerabilities including remote code execution. For more information, see [this Microsoft article](https://techcommunity.microsoft.com/t5/storage-at-microsoft/stop-using-smb1/ba-p/425858).

User Permissions

Administrator privileges on the machine where the Veeam Backup for Microsoft 365 server is deployed allow users to access other infrastructure components. If an attacker gains such permissions, they can erase most of the production data as well as compromise other systems in your environment. To mitigate risks, use the principle of least privilege. Provide the minimal required permissions needed for the accounts to operate correctly. For more information, see [Permissions](vbo_required_permissions.md).

File System

Do not add paths writable by untrusted users to the PATH environment variable. A potential attacker may exploit this vulnerability to execute malware or access sensitive data. For more information, see [this CWE article](https://cwe.mitre.org/data/definitions/426.html).

Security Audit

Perform regular security audits to assess your Veeam Backup for Microsoft 365 infrastructure against security criteria and understand if it is compliant with best practices, industry standards, and federal regulations.

To reduce the risk of exploiting vulnerabilities by attackers, follow these recommendations:

* Regularly install the latest security updates and patches on the Veeam Backup for Microsoft 365 server and Veeam Backup for Microsoft 365 components.
* Develop an update management strategy to prevent a negative impact on the production environment.

|  |
| --- |
| Tip |
| You can subscribe to Veeam security advisories published in the [Veeam Knowledge Base](https://www.veeam.com/knowledge-base.html) to stay up to date with the latest security updates. |

Microsoft Windows Server

To secure Microsoft Windows-based components in Veeam Backup for Microsoft 365 infrastructure, consider the following recommendations:

* Use operating system versions with Long Term Servicing Channel (LTSC). For these versions, Microsoft provides extended support including regular security updates. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/windows-server/get-started/extended-security-updates-overview).
* Regularly install the latest operating system and security updates for Microsoft Windows. To prevent a negative impact on the production environment, develop an update management strategy.

* Turn on Microsoft Defender Firewall with Advanced Security. Set up rules for inbound and outbound connections according to your infrastructure and Microsoft best practices. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/best-practices-configuring).
* Disable remote services if they are not needed:

* Remote Desktop Service
* Remote Registry service
* Remote PowerShell
* Windows Remote Management service

Linux Server

To secure Linux-based components in Veeam Backup for Microsoft 365 infrastructure, consider the following recommendations:

* Use operating system versions with long-term support (LTS). LTS versions of popular community-based and commercial Linux distributions have extended support including regular security updates. For more information, see [System Requirements](vbo_system_requirements.md#BackupProxy).

* Regularly install the latest operating system and security updates for Linux distributions. To prevent a negative impact on the production environment, develop an update management strategy.

* For the SSH tunnel, use a strong and proven encryption algorithm with sufficient key length. Make sure that private keys are kept in a highly secure place and cannot be uncovered by a third-party.
* Avoid using password authentication to connect to remote servers over SSH. Using key-based SSH authentication is generally considered more secure than using password authentication and helps avert man-in-the-middle (MITM) attacks. The private key is not passed to the server and cannot be captured even if a user connects to a fake server and accepts a bad fingerprint.


