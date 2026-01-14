---
title: "set-vboglobalretentionexclusion"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboglobalretentionexclusion.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies global retention policy settings for contacts and calendars.

Syntax

|  |
| --- |
| Set-VBOGlobalRetentionExclusion [-Contacts] [-Calendar] [<CommonParameters>] |

Detailed Description

This cmdlet modifies global retention policy settings for contacts and calendars. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Contacts | Defines that the cmdlet will change global retention policy settings for contacts.  Default: False  If you provide this parameter, the global retention policy will be applied to contacts. Otherwise, global retention policy will not be applied to contacts. | SwitchParameter | False | Named | False |
| Calendar | Defines that the cmdlet will change global retention policy settings for calendars.  Default: False  If you provide this parameter, the global retention policy will be applied to calendars. Otherwise, global retention policy will not be applied to calendars. | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOGlobalRetentionExclusionobject that contains retention policy settings for calendars and contacts.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Enabling Retention Policy for Contacts

|  |  |
| --- | --- |
| This command enables retention policy for contacts.  |  | | --- | | Set-VBOGlobalRetentionExclusion -Contacts | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Enabling Retention Policy for Calendars

|  |  |
| --- | --- |
| This command enables retention policy for calendars.  |  | | --- | | Set-VBOGlobalRetentionExclusion -Calendar | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Disabling Retention Policy for Contacts

|  |  |
| --- | --- |
| This command disables retention policy for contacts.  |  | | --- | | Set-VBOGlobalRetentionExclusion -Contacts:$false | |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Disabling Retention Policy for Calendars

|  |  |
| --- | --- |
| This command disables retention policy for calendars.  |  | | --- | | Set-VBOGlobalRetentionExclusion -Calendar:$false | |

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
