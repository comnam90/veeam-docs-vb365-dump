---
title: "adjust_postgres_instance"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/adjust_postgres_instance.html"
last_updated: "10/8/2025"
product_version: "8.3.0.2201"
---


In this article

If you have selected to use an already installed PostgreSQL instance at the [Configure PostgreSQL Instance](vbo_install_configure_instance.md) step of the wizard, right after you deploy Veeam Backup for Microsoft 365, make sure that the instance configuration is sufficient for the product performance.

|  |
| --- |
| Note |
| To enhance security of the PostgreSQL instance, we recommend that you also enable the TLS encryption for the PostgreSQL instance traffic. For more information, see [this PostgreSQL article](https://www.postgresql.org/docs/current/ssl-tcp.html). |

To adjust the configuration of the PostgreSQL instance, do the following:

1. On the Veeam Backup for Microsoft 365 server, run the [Set-VBOPSQLDatabaseServerLimits](https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbopsqldatabaseserverlimits.html?ver=80) cmdlet. The cmdlet generates the necessary PostgreSQL configuration and saves it to a dump SQL file.

|  |
| --- |
| Set-VBOPSQLDatabaseServerLimits -OSType <String> -CPUCount <number of CPU cores> -RamGb <RAM in GB> -DumpToFile <file path> |

For example,

|  |
| --- |
| Set-VBOPSQLDatabaseServerLimits -OSType Windows -CPUCount 8 -RamGb 16 -DumpToFile "c:\temp\PSqlLimitConfig.sql" |

1. On the machine with the PostgreSQL instance where you have deployed the Veeam Backup for Microsoft 365 configuration database, use the psql tool to apply the configuration from the dump file.

The tool is located in the PostgreSQL installation folder.

|  |
| --- |
| psql -U <user> -f <file path> |

For example,

|  |
| --- |
| psql -U postgres -f "C:\config.sql" |

After you apply the configuration from the dump file, all changes will be written into the postgresql.auto.conf file located in the PostgreSQL installation folder. This file is loaded when the service starts and takes precedence over the default PostgreSQL configuration file.

1. Include the [pg\_stat\_statements](https://www.postgresql.org/docs/current/pgstatstatements.html) library to the PostgreSQL configuration. To add the library, you can manually edit the shared\_preload\_libraries option in the postgresql.conf file.

Alternatively, you can do it by by executing the SQL code:

1. Check the content of the shared\_preload\_libraries variable.

|  |
| --- |
| SELECT \* FROM pg\_settings  WHERE name = 'shared\_preload\_libraries'; |

1. Add the pg\_stat\_statements library to the shared preloaded libraries. Do one of the following:

* If the shared\_preload\_libraries value is empty, assign pg\_stat\_statements to the shared\_preload\_libraries variable.

|  |
| --- |
| ALTER SYSTEM SET shared\_preload\_libraries = pg\_stat\_statements; |

* If the shared\_preload\_libraries value is not empty, add pg\_stat\_statements to the current value separated by comma.

|  |
| --- |
| ALTER SYSTEM SET shared\_preload\_libraries = <existing libraries>, pg\_stat\_statements; |

1. Restart the PostgreSQL service for the new configuration to take effect.
2. Install the pg\_stat\_statements extension. The extension is used to analyze the PostgreSQL performance.

|  |
| --- |
| CREATE EXTENSION IF NOT EXISTS "pg\_stat\_statements"; |

Page updated 10/8/2025

Page content applies to build 8.3.0.2201
