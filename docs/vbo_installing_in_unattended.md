---
title: "Installing in Unattended Mode"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_installing_in_unattended.html"
last_updated: "4/30/2025"
product_version: "8.3.0.2201"
---

# Installing in Unattended Mode


You can install Veeam Backup for Microsoft 365, Veeam Explorer for Microsoft Exchange, Veeam Explorer for Microsoft SharePoint and Veeam Explorer for Microsoft Teams in unattended mode.

Use the following syntax to run an MSI file:

|  |
| --- |
| msiexec /i <path\_to\_msi> /qn ADDLOCAL=<feature1,feature2,feature3> ACCEPT\_THIRDPARTY\_LICENSES=1 ACCEPT\_EULA=1 CONNECTION="Host=<PostgreSQL hostname>;Port=<port number>;Database=<PostgreSQL database name>;Username=<PostgreSQL database account name>;Password=<password>" JETSTREAM\_CONNECTION="nats://<NATS user account name>:<password>@<NATS server hostname>:<port number>" |

|  |
| --- |
| Important |
| You cannot install new PostgreSQL and NATS server instances using this installation scenario. To install Veeam Backup for Microsoft 365 in unattended mode, PostgreSQL and NATS server instances must be already preinstalled. For more information, see [PostgreSQL Instance](architecture.md#postgresql) and [NATS Server](architecture.md#nats). |

The following table lists components and feature names or feature descriptions for Veeam Backup for Microsoft 365:

| Component | Feature |
| --- | --- |
| EXO V3 PowerShell Module1 | PS\_MODULES |
| Server | BR\_OFFICE365 |
| Console | CONSOLE\_OFFICE365 |
| PowerShell | PS\_OFFICE365 |
| REST API | REST\_OFFICE365 |
| CONNECTION | Specify the following properties of an already installed PostgreSQL instance:   * Host — a public IPv4 address or a DNS host name of a machine with the PostgreSQL instance. The default value is 127.0.0.1. * Port — a port number to connect to a machine with the PostgreSQL instance. The default value is 5432. * Database — a name of the PostgreSQL database. The default value is postgres. * Username — a user name of the database account. The default value is postgres. * Password — a password of the database account. |
| JETSTREAM\_CONNECTION | Specify a full URL which includes a user account credentials, a host name and a port to connect to an already installed NATS server instance. The default port number is 4222. |

1The EXO V3 PowerShell Module component must be installed along with any other component.

The following table lists components and feature names for Veeam Explorer for Microsoft Exchange:

| Component | Feature |
| --- | --- |
| UI | BR\_EXCHANGEEXPLORER |
| PowerShell | PS\_EXCHANGEEXPLORER |

The following table lists components and feature names for Veeam Explorer for Microsoft SharePoint:

|  |
| --- |
| Note |
| Veeam Explorer for Microsoft SharePoint and Veeam Explorer for Microsoft OneDrive for Business are distributed in a single package. |

| Component | Feature |
| --- | --- |
| UI | BR\_SHAREPOINTEXPLORER |
| PowerShell | PS\_SHAREPOINTEXPLORER |

The following table lists components and feature names for Veeam Explorer for Microsoft Teams:

| Component | Feature |
| --- | --- |
| UI | BR\_TEAMSEXPLORER |
| PowerShell | PS\_TEAMSEXPLORER |

Examples

To install Veeam Backup for Microsoft 365, and the EXO V3 PowerShell Module, Console, PowerShell and REST API components:

|  |
| --- |
| msiexec /i Veeam.Backup365.msi /qn ADDLOCAL=BR\_OFFICE365,CONSOLE\_OFFICE365,PS\_OFFICE365,REST\_OFFICE365,PS\_MODULES ACCEPT\_THIRDPARTY\_LICENSES=1 ACCEPT\_EULA=1 CONNECTION="Host=127.0.0.1;Port=5432;Database=postgres;Username=postgres;Password=123password" JETSTREAM\_CONNECTION="nats://admin:123password@demo.nats.io:4222" |

To install the REST API component only:

|  |
| --- |
| msiexec /i Veeam.Backup365.msi /qn ADDLOCAL=REST\_OFFICE365,PS\_MODULES ACCEPT\_THIRDPARTY\_LICENSES=1 ACCEPT\_EULA=1 |

To install the Veeam Explorer for Microsoft Exchange, UI and PowerShell components:

|  |
| --- |
| msiexec /i VeeamExplorerForExchange.msi /qn ADDLOCAL=BR\_EXCHANGEEXPLORER,PS\_EXCHANGEEXPLORER ACCEPT\_THIRDPARTY\_LICENSES=1 ACCEPT\_EULA=1 |

To install the Veeam Explorer for Microsoft SharePoint, UI and PowerShell components:

|  |
| --- |
| msiexec /i VeeamExplorerForSharePoint.msi /qn ADDLOCAL=BR\_SHAREPOINTEXPLORER,PS\_SHAREPOINTEXPLORER ACCEPT\_THIRDPARTY\_LICENSES=1 ACCEPT\_EULA=1 |

|  |
| --- |
| Note |
| Veeam Explorer for Microsoft SharePoint and Veeam Explorer for Microsoft OneDrive for Business are distributed in a single package. |

To install the Veeam Explorer for Microsoft Teams, UI and PowerShell components:

|  |
| --- |
| msiexec /i VeeamExplorerForTeams.msi /qn ADDLOCAL=BR\_TEAMSEXPLORER,PS\_TEAMSEXPLORER ACCEPT\_THIRDPARTY\_LICENSES=1 ACCEPT\_EULA=1 |


