---
title: "Get-VBOGlobalRetentionExclusion"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboglobalretentionexclusion.html"
last_updated: "1/13/2026"
product_version: "8.3.0.2201"
---

# Get-VBOGlobalRetentionExclusion


Short Description

Returns global retention policy settings for contacts and calendars.

Syntax

|  |
| --- |
| Get-VBOGlobalRetentionExclusion [<CommonParameters>] |

Detailed Description

This cmdlet returns the following global retention policy settings for contacts and calendars:

* SkipCalendar

* If set to True, retention policy will not be applied to calendars.
* If set to False, retention policy will be applied to calendars.
* Default: False.

* SkipContact

* If set to True, retention policy will not be applied to contacts.
* If set to False, retention policy will be applied to contacts.
* Default: False.

Parameters

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the [VBOGlobalRetentionExclusion](vboglobalretentionexclusion.md) object that contains retention policy settings for calendars and contacts.

Example

Getting Details on Retention Policy

This command returns retention policy settings for calendars and contacts.

|  |
| --- |
| Get-VBOGlobalRetentionExclusion                     SkipCalendar                                                SkipContacts                     ------------                                                ------------                            False                                                       False |


