---
title: "Get-VBOJobSession"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vbojobsession.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# Get-VBOJobSession


Short Description

Returns backup and backup copy job sessions.

Syntax

This cmdlet provides parameter sets that allow you to:

* Get job sessions for jobs of the specified type and status.

|  |
| --- |
| Get-VBOJobSession [-JobType <VBOJobSessionType>] [-Status <VBOJobStatus>] [-Last] [<CommonParameters>] |

* Get a job session for a specific job.

|  |
| --- |
| Get-VBOJobSession [-Job <IVBOJobWithId>] [-Status <VBOJobStatus>] [-Last] [<CommonParameters>] |

Detailed Description

This cmdlet returns job sessions stored in Veeam Backup for Microsoft 365.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| JobType | Specifies a job type. The cmdlet will return job sessions for the jobs of the specified type:   * Backup * Copy | VBOJobSessionType | False | Named | False |
| Status | Specifies a job status. The cmdlet will return job sessions for the jobs with the specified status:   * Disconnected * Failed * NotConfigured * Queued * Running * Stopped * Success * Warning  * Updating | VBOJobStatus | False | Named | False |
| Last | Defines that the cmdlet will return the latest job session.  If the Job parameter is used, the cmdlet will return the latest job session for the specified job.  If the Status parameter is used, the cmdlet will return the latest job session for the jobs with the specified status.  Default: False | SwitchParameter | False | Named | False |
| Job | Specifies a job. The cmdlet will return job sessions for this backup or backup copy job. | IVBOJobWithId  Accepts the [VBOJob](vbojob.md) or [VBOCopyJob](vbocopyjob.md) object.  To get this object, run the [Get-VBOJob](get-vbojob.md) or [Get-VBOCopyJob](get-vbocopyjob.md) cmdlet. | False | Named | True (ByValue) |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOJobSession](vbojobsession.md) object that contains details about job sessions.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Getting All Job Sessions

|  |  |
| --- | --- |
| This command returns a list of all job sessions.  |  | | --- | | Get-VBOJobSession | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Getting Job Sessions for Backup Jobs with Success Status

|  |  |
| --- | --- |
| This command returns all job sessions for backup jobs with the Success status.  |  | | --- | | Get-VBOJobSession -JobType Backup -Status Success | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Getting Latest Job Session

|  |  |
| --- | --- |
| This command returns the latest job session stored in Veeam Backup for Microsoft 365.  |  | | --- | | Get-VBOJobSession -Last | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Getting Latest Job Session for Backup Jobs with Failed Status

|  |  |
| --- | --- |
| This command returns the latest job session for backup jobs with the Failed status.  |  | | --- | | Get-VBOJobSession -JobType Backup -Status Failed -Last | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 5: Getting Statistics for Latest Job Session

|  |  |
| --- | --- |
| This example shows how to get statistics for the latest job session.  |  | | --- | | $session = Get-VBOJobSession -Last  $session.statistics |  Perform the following steps:   1. Run the Get-VBOJobSession cmdlet with the Last parameter to get the latest job session. Save the result to the $session variable. 2. Get the job session statistics using the Statistics property of the job session object saved to the $session variable. |

Related Commands

* [Get-VBOJob](get-vbojob.md)
* [Get-VBOCopyJob](get-vbocopyjob.md)


