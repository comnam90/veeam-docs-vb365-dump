---
title: "System Requirements"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_system_requirements.html"
last_updated: "1/16/2026"
product_version: "8.3.0.2201"
---

# System Requirements


Make sure that your Microsoft organizations and backup infrastructure components meet the listed requirements.

Supported Organizations

The following table lists supported Microsoft Exchange and Microsoft SharePoint organizations:

| Organization | Requirement |
| --- | --- |
| Microsoft Exchange | Veeam Backup for Microsoft 365 supports the following Microsoft Exchange versions:  * Microsoft 365 Exchange Online   [Microsoft 365 and Office 365 service families](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options#service-families-and-plans), standalone services and plans for Business, Education, and Government\* hosted by Microsoft are supported. For more information about system requirements and limitations for Microsoft 365, see [this Microsoft article](https://www.microsoft.com/en-us/microsoft-365/microsoft-365-and-office-resources#Office365forBEG).   * Microsoft Exchange Server 2019 (on-premises) * Microsoft Exchange Server 2016 (on-premises)  For more information about limitations for backup and restore of mail items, see [Considerations and Limitations](vbo_considerations.md). |
| Microsoft SharePoint | Veeam Backup for Microsoft 365 supports the following Microsoft SharePoint versions:  * Microsoft 365 SharePoint Online   [Microsoft 365 and Office 365 service families](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options#service-families-and-plans), standalone services and plans for Business, Education, and Government\* hosted by Microsoft are supported. For more information about system requirements and limitations for Microsoft 365, see [this Microsoft article](https://www.microsoft.com/en-us/microsoft-365/microsoft-365-and-office-resources#Office365forBEG).   * Microsoft SharePoint Server 2019   For more information about hardware and software requirements, see [this Microsoft article](https://learn.microsoft.com/en-us/sharepoint/install/hardware-and-software-requirements-2019).   * Microsoft SharePoint Server 2016   For more information about hardware and software requirements, see [this Microsoft article](https://learn.microsoft.com/en-us/sharepoint/install/hardware-and-software-requirements).   * Microsoft SharePoint Server Subscription Edition   For more information about hardware and software requirements, see [this Microsoft article](https://docs.microsoft.com/en-us/sharepoint/install/hardware-and-topology-requirements-for-sharepoint-server-subscription-editon) and [this Microsoft article](https://docs.microsoft.com/en-us/sharepoint/install/software-requirements-for-database-servers-for-sharepoint-server-subscription-edition). |

\*Government support is experimental. For more information, see [this Veeam KB article](https://www.veeam.com/kb2976).

|  |
| --- |
| Note |
| Throttling policies for Exchange Online cannot be managed in the Microsoft 365 interface. |

Veeam Backup for Microsoft 365 Server

The following table lists system requirements for the machine with Veeam Backup for Microsoft 365:

| Specification | Requirement |
| --- | --- |
| Hardware | The following hardware is required:   * CPU: any modern multi-core x64 processor, 8 cores minimum.  * Memory: 16 GB RAM minimum. Allocating additional RAM and CPU resources can enhance backup, restore and search performance.   If you plan to deploy Veeam Backup for Microsoft 365 on VM with dynamic memory allocation, such VM must have 32 GB RAM minimum.   * Disk Space: 3 GB for product installation and additional free space required for product logs, and for the PostgreSQL instance and the NATS server deployment (if using the default installation).   For optimal performance, we recommend to use SSD drive. |
| OS | 64-bit version of the following Microsoft Windows operating systems are supported:   * Microsoft Windows Server 2016, 2019, 2022, 2025. * Microsoft Windows 10 (versions 21H2, 22H2). * Microsoft Windows 11 (versions 22H2, 23H2, 24H2, 25H2). * Microsoft Windows Server Core editions 2016 (LTSC 1607), 2019 (LTSC 1809), 2022. |
| Configuration and Cache Database | You can use one of the following:   * Local or remote installation of PostgreSQL 15.9, 15.12, 15.13, 15.14, 16.4, 16.9. * Azure Database for PostgreSQL 16 – Flexible Server. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/postgresql/).   Consider that the configuration and cache database are highly loaded and resource-consuming. For optimal performance, we recommend using an SSD drive with at least 5000 IOPS (including installations on Azure and AWS instances). IOPS consumption varies according to the frequency of backups, the number of jobs, the size of protected Microsoft organizations, and so on.  It is not recommended to share a PostgreSQL instance with any other services. It should be dedicated to host the Veeam Backup for Microsoft 365 configuration database and cached metadata only.  Note: If you plan to use a database engine other than PostgreSQL included in the [Veeam Backup for Microsoft 365 setup](download_package.md), you must install and maintain it yourself. If you want to use an already installed PostgreSQL instance for the configuration database, make sure the instance contains the default postgres database. If you allow the setup to install a new PostgreSQL instance, the postgres database will be created on the instance automatically. Since Veeam Backup for Microsoft 365 connects to the postgres database to access the configuration database, do not rename the postgres database upon the installation. |
| NATS | Local or remote installation of the NATS server 2.10.18, 2.10.22, 2.10.28.  Note: If you plan to use the NATS server other than the version included in the [Veeam Backup for Microsoft 365 setup](download_package.md), you must install and maintain it yourself. |
| Software | The following components are required:   * Microsoft ASP.NET Core Runtime 8.0.10–8.0.xx. * Microsoft .NET Desktop Runtime 8.0.10–8.0.xx. * Microsoft .NET Runtime 8.0.10–8.0.xx.  * To use PowerShell, Windows PowerShell 7.4.2 or later is required.   For more information about Microsoft 365 system requirements and limitations, see [this Microsoft article](https://www.microsoft.com/en-us/microsoft-365/microsoft-365-and-office-resources#Office365forBEG). |

|  |
| --- |
| Important |
| Consider the following:   * When you install Veeam Explorers and Veeam Backup for Microsoft 365 on different servers, the OS version on computers with Veeam Explorers must be the same or later than the OS version on a computer with Veeam Backup for Microsoft 365. * Veeam Explorers can be installed on a machine hosting Veeam Backup for Microsoft 365 8 or the Veeam Backup for Microsoft 365 Console component. You can also use a machine with Veeam Backup & Replication 12 or later that is deployed either along with any of these components, or as an independent solution.  * The account you want to use for launching Veeam Backup for Microsoft 365 must be a member of the local Administrators group or have been assigned the Veeam Backup Administrator role. For more information, see [Managing Users and Roles](manage_users_roles.md). |

Machine with REST API

The following table lists system requirements for the dedicated machine with the Veeam Backup for Microsoft 365 REST API component:

| Specification | Requirement |
| --- | --- |
| Hardware | The following hardware is required:   * CPU: any modern multi-core x64 processor, 8 cores minimum.  * Memory: 16 GB RAM minimum. Allocating additional RAM and CPU resources can enhance restore and search performance.   If you plan to deploy the Veeam Backup for Microsoft 365 REST API server on VM with dynamic memory allocation, such VM must have 32 GB RAM minimum.   * Disk Space: 1 GB for the Veeam Backup for Microsoft 365 REST API server installation and additional free space for product logs. |
| OS | 64-bit version of the following Microsoft Windows operating systems are supported:   * Microsoft Windows Server 2016, 2019, 2022, 2025. * Microsoft Windows 10 (versions 21H2, 22H2). * Microsoft Windows 11 (versions 22H2, 23H2, 24H2, 25H2). * Microsoft Windows Server Core editions 2016 (LTSC 1607), 2019 (LTSC 1809), 2022. |
| Software | The following components are required:   * Microsoft ASP.NET Core Runtime 8.0.10–8.0.xx. * Microsoft .NET Desktop Runtime 8.0.10–8.0.xx.  * Microsoft .NET Runtime 8.0.10–8.0.xx. |

Backup Proxy Server

The following table lists system requirements for machines that you plan to use as [backup proxy servers](vbo_backup_proxy_servers.md):

| Specification | Requirement |
| --- | --- |
| Hardware | The following hardware is required:   * CPU: any modern multi-core x64 processor, 4 cores minimum. * Memory: 16 GB RAM minimum. Allocating additional RAM and CPU resources can enhance backup, restore and search performance.   If you plan to deploy Veeam Backup for Microsoft 365 backup proxy server on VM with dynamic memory allocation, such VM must have 32 GB RAM minimum.   * Disk space: 3 GB for the backup proxy server installation and additional free space for product logs. |
| OS | 64-bit version of the following Microsoft Windows operating systems are supported:   * Microsoft Windows Server 2016, 2019, 2022, 2025. * Microsoft Windows 10 (versions 21H2, 22H2). * Microsoft Windows 11 (versions 22H2, 23H2, 24H2, 25H2). * Microsoft Windows Server Core editions 2016 (LTSC 1607), 2019 (LTSC 1809), 2022.   64-bit versions of the following Linux distributions are supported:   * RHEL 8.8 LTS, 8.10 LTS, 9.0 LTS, 9.2 LTS, 9.4 LTS and 9.6 LTS * Ubuntu 20.04 LTS, 22.04 LTS, and 24.04 LTS |
| Other | The following components are required:   * Microsoft .NET Runtime 8.0.10–8.0.xx.  * To use PowerShell, Windows PowerShell 7.4.2 or later is required.   For a machine used as a workgroup backup proxy, the following settings are required:   * The Remote Registry service must run on the target machine. The service startup type must be set to Automatic. * [Backup proxy server ports](vbo_used_ports.md#bp_ports) must be opened in a firewall. |


