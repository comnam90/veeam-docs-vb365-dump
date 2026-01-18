---
title: "Add-VBOOrganizationRetentionExclusion"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboorganizationretentionexclusion.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# Add-VBOOrganizationRetentionExclusion


Short Description

Adds retention policy settings for contacts and calendars of a specific organization.

Syntax

|  |
| --- |
| Add-VBOOrganizationRetentionExclusion -Organization <VBOOrganization> [-Contacts] [-Calendar] [<CommonParameters>] |

Detailed Description

This cmdlet adds retention policy settings for contacts and calendars of a specific organization.

|  |
| --- |
| ![Add-VBOOrganizationRetentionExclusion](images/icon_important.webp) Important |
| This retention policy has higher priority than the global retention policy. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will set retention policy for contacts and calendars added to the specified organization. | Accepts the [VBOOrganization](vboorganization.md) object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | False |
| Contacts | Defines that Veeam Backup for Microsoft 365 will not apply retention policy for contacts of the specified organization.  If you do not provide this parameter, Veeam Backup for Microsoft 365 will apply retention policy for contacts.  Default: False | SwitchParameter | False | Named | False |
| Calendar | Defines that Veeam Backup for Microsoft 365 will not apply retention policy for calendars of the specified organization.  If you do not provide this parameter, Veeam Backup for Microsoft 365 will apply retention policy for calendars.  Default: False | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

This cmdlet returns the [VBOOrganizationRetentionExclusion](vboorganizationretentionexclusion.md) object that contains settings of organization retention policy for contacts and calendars.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Enabling Retention Policy for Organization Contacts

|  |  |
| --- | --- |
| This example shows how to enable retention policy for contacts of the Atlanta organization. Veeam Backup for Microsoft 365 will apply retention policy for contacts added to the Atlanta organization.  |  | | --- | | $org = Get-VBOOrganization -Name "Atlanta"  Add-VBOOrganizationRetentionExclusion -Organization $org -Contacts |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Set the Name parameter value. Save the result to the $org variable. 2. Run the Add-VBOOrganizationRetentionExclusion cmdlet. Set the $org variable as the Organization parameter value. Provide the Contacts parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Enabling Retention Policy for Organization Calendars

|  |  |
| --- | --- |
| This example shows how to enable retention policy for calendars of the Atlanta organization. Veeam Backup for Microsoft 365 will apply retention policy for calendars added to the Atlanta organization.  |  | | --- | | $org = Get-VBOOrganization -Name "Atlanta"  Add-VBOOrganizationRetentionExclusion -Organization $org -Calendar |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Set the Name parameter value. Save the result to the $org variable. 2. Run the Add-VBOOrganizationRetentionExclusion cmdlet. Set the $org variable as the Organization parameter value. Provide the Calendar parameter. |

Related Commands

[Get-VBOOrganization](get-vboorganization.md)


