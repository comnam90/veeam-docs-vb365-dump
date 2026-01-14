---
title: "set-vbodataretrieval"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vbodataretrieval.html"
last_updated: "5/6/2024"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies retrieval job settings.

Syntax

|  |
| --- |
| Set-VBODataRetrieval -DataRetrieval <VBODataRetrieval> [-Name <String>] [-Description <String>] [-AvailabilityPeriodDays <Int32>] [-EnableExpirationNotification] [-ExpirationHoursThreshold <Int32>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies settings of a retrieval job. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| DataRetrieval | Specifies a retrieval job. The cmdlet will modify settings of this retrieval job. | Accepts the VBODataRetrieval object.  To get this object, run the [Get-VBODataRetrieval](get-vbodataretrieval.md) cmdlet. | True | Named | True (ByValue) |
| Name | Specifies a new name of a retrieval job. The cmdlet will replace the current name with the specified name. | String | False | Named | False |
| Description | Specifies a description of the retrieval job.  The cmdlet will replace the current description with the specified description. | String | False | Named | False |
| AvailabilityPeriodDays | Specifies the number of days during which the retrieved backed-up data will be available to explore and restore using Veeam Explorers.  Default: 1 | Int32 | False | Named | False |
| EnableExpirationNotification | Defines that Veeam Backup for Microsoft 365 will notify you when the availability period is about to end.  Default: False | SwitchParameter | False | Named | False |
| ExpirationHoursThreshold | For the EnableExpirationNotification option.  Specifies how many hours should remain before the retrieved backed-up data expires to send a notification by email. | Int32 | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBODataRetrieval object that contains settings for a retrieval job.

Example

Changing Availability Period for Retrieved Data

This example shows how to change the availability period of the retrieved backed-up data and enable notification by email before the retrieved backed-up data expires.

|  |
| --- |
| $retrievaljob = Get-VBODataRetrieval -Id 3192dfc9-353f-468f-91b6-c66e5710c63f  Set-VBODataRetrieval -DataRetrieval $retrievaljob -Name "ABC User Mailbox" -AvailabilityPeriodDays 5 -EnableExpirationNotification -ExpirationHoursThreshold 2 |

Perform the following steps:

1. Run the [Get-VBODataRetrieval](get-vbodataretrieval.md) cmdlet. Specify the Id parameter value. Save the result to the $retrievaljob variable.
2. Run the Set-VBODataRetrieval cmdlet. Specify the following settings:

* Set the $retrievaljob variable as the DataRetrieval parameter value.
* Specify the Name parameter value.
* Set 5 as the AvailabilityPeriodDays parameter value.
* Specify the EnableExpirationNotification parameter value.
* Set 2 as the ExpirationHoursThreshold parameter value.

Related Commands

[Get-VBODataRetrieval](get-vbodataretrieval.md)

Page updated 5/6/2024

Page content applies to build 8.3.0.2201
