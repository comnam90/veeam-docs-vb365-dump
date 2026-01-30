---
title: "Set-VBOPSQLDatabaseServerLimits"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbopsqldatabaseserverlimits.html"
last_updated: "11/10/2025"
product_version: "8.3.0.2201"
---

# Set-VBOPSQLDatabaseServerLimits


Short Description

Modifies settings of the PostgreSQL instance.

Syntax

This cmdlet provides parameter sets that allow you to:

* Modify settings of the PostgreSQL instance automatically.

|  |
| --- |
| Set-VBOPSQLDatabaseServerLimits [-DumpToFile <String>] [<CommonParameters>] |

* Modify settings of the PostgreSQL instance manually.

|  |
| --- |
| Set-VBOPSQLDatabaseServerLimits -OSType <String> -CPUCount <Int32> -RamGb <Int32> [-DumpToFile <String>] [<CommonParameters>] |

Detailed Description

This cmdlet allows you to modify settings for the PostgreSQL instance. Use this cmdlet to extend hardware resources of the PostgreSQL instance where the Veeam Backup for Microsoft 365 configuration database is located.

Depending on your configuration, you can use the following parameter sets:

* Automatic modification. Use this parameter set if you installed the PostgreSQL instance and the Veeam Backup for Microsoft 365 server on the same machine, and the PostgreSQL instance is used as the Veeam Backup for Microsoft 365 configuration database.
* Manual modification. Use this parameter set in the following cases:

* If the PostgreSQL instance is already installed on a remote machine and it is used by Veeam Backup for Microsoft 365 as the configuration database. In this case, you must specify the OS of the machine where the PostgreSQL database installed, number of CPU cores and amount of memory in GB.
* If the PostgreSQL instance is installed on a remote machine and currently is not used by Veeam Backup for Microsoft 365 as the configuration database. In this case, you must create a dump file with the necessary settings at the path you specified. Also, you must specify the OS of the machine where the PostgreSQL database installed, number of CPU cores, and amount of memory in GB.

To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

|  |
| --- |
| ![Set-VBOPSQLDatabaseServerLimits](images/icon_important.webp) Important |
| Consider the following:   * If you deploy a PostgreSQL instance along with the Veeam Backup for Microsoft 365 installation, the necessary resource capacity will be configured automatically during the installation. * If the CPU or RAM resources are changed after Veeam Backup for Microsoft 365 installation, you must run this cmdlet again to adjust hardware resources of the PostgreSQL instance. * You must restart the PostgreSQL service after you run this cmdlet. * In larger environments to improve database connection efficiency and performance, it is recommended to use PgBouncer. For more information, see [this Veeam KB article](https://www.veeam.com/kb4758). |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| DumpToFile | Specifies a path to a dump file. The cmdlet will save a dump SQL file on a machine where you run the cmdlet. | String | False | Named | False |
| OSType | Specifies the OS of the machine where the PostgreSQL instance is installed:   * Windows * Linux | String | True | Named | False |
| CPUCount | Specifies a number of CPU cores that you want to assign to a machine where the PostgreSQL instance is installed. | Int32 | True | Named | False |
| RamGb | Specifies amount of memory in GB that you want to assign to a machine where the PostgreSQL instance is installed. | Int32 | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Local PostgreSQL Instance

|  |  |
| --- | --- |
| This command automatically modifies settings of the PostgreSQL instance. The PostgreSQL instance and the Veeam Backup for Microsoft 365 server are installed on the same machine, and the PostgreSQL instance is used as the Veeam Backup for Microsoft 365 configuration database.  |  | | --- | | Set-VBOPSQLDatabaseServerLimits | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Modifying Remote PostgreSQL Instance

|  |  |
| --- | --- |
| This command manually modifies settings of the PostgreSQL instance. The PostgreSQL instance is already installed on a remote machine and it is used by Veeam Backup for Microsoft 365 as the configuration database.  |  | | --- | | Set-VBOPSQLDatabaseServerLimits -OSType Windows -CPUCount 8 -RamGb 32 | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Modifying Remote PostgreSQL Instance and Creating Dump File

|  |  |  |
| --- | --- | --- |
| This command creates a dump file with the necessary settings of the PostgreSQL instance, which you must then apply manually to the configuration database. The PostgreSQL instance is already installed on a remote machine and currently it is not used by Veeam Backup for Microsoft 365 as the configuration database.  |  | | --- | | Set-VBOPSQLDatabaseServerLimits -OSType Windows -CPUCount 8 -RamGb 32 -DumpToFile "c:\temp\PSqlLimitConfig.sql" |  The following is the example of a dump file that you must apply manually to the configuration database:  |  | | --- | | ALTER SYSTEM SET max\_connections = '1000';  ALTER SYSTEM SET effective\_cache\_size = '<dynamically calculated value>';  ALTER SYSTEM SET checkpoint\_completion\_target = '0.9';  ALTER SYSTEM SET wal\_buffers = '16MB';  ALTER SYSTEM SET default\_statistics\_target = '100';  ALTER SYSTEM SET random\_page\_cost = '1.1';  ALTER SYSTEM SET max\_worker\_processes = '<dynamically calculated value>';  ALTER SYSTEM SET max\_parallel\_workers\_per\_gather = '<dynamically calculated value>';  ALTER SYSTEM SET max\_parallel\_workers = '<dynamically calculated value>';  ALTER SYSTEM SET max\_parallel\_maintenance\_workers = '<dynamically calculated value>';  ALTER SYSTEM SET min\_wal\_size = '2GB';  ALTER SYSTEM SET max\_wal\_size = '8GB';  ALTER SYSTEM SET hash\_mem\_multiplier = '2';  ALTER SYSTEM SET log\_temp\_files = '10MB';  ALTER SYSTEM SET log\_lock\_waits = 'on';  ALTER SYSTEM SET join\_collapse\_limit = '8';  ALTER SYSTEM SET geqo\_threshold = '10';  ALTER SYSTEM SET log\_line\_prefix = '%m [%p] %q[user=%u,db=%d,app=%a] ';  ALTER SYSTEM SET jit = 'off';  ALTER SYSTEM SET log\_autovacuum\_min\_duration = '60s';  ALTER SYSTEM SET log\_min\_duration\_sample = '1000';  ALTER SYSTEM SET log\_statement\_sample\_rate = '0.01';  ALTER SYSTEM SET log\_rotation\_age = '10d';  ALTER SYSTEM SET shared\_buffers = '<dynamically calculated value>';  ALTER SYSTEM SET maintenance\_work\_mem = '<dynamically calculated value>';  ALTER SYSTEM SET work\_mem = '<dynamically calculated value>'; | |


