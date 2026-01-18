---
title: "Remove-VBOOrganizationRetentionExclusion"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/remove-vboorganizationretentionexclusion.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# Remove-VBOOrganizationRetentionExclusion


Short Description

Removes retention policy settings for contacts and calendars of a specific organization.

Syntax

|  |
| --- |
| Remove-VBOOrganizationRetentionExclusion -Exclusion <VBOOrganizationRetentionExclusion> [-WhatIf] [-Confirm] [<CommonParameters>] |

Detailed Description

This cmdlet removes retention policy settings for contacts and calendars of a specific organization.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Exclusion | Specifies the retention policy settings for contacts and calendars of a specific organization. The cmdlet will remove these settings. | Accepts the [VBOOrganizationRetentionExclusion](vboorganizationretentionexclusion.md) object.  To get this object, run the [Get-VBOOrganizationRetentionExclusion](get-vboorganizationretentionexclusion.md) cmdlet. | True | Named | False |
| WhatIf | Defines that the cmdlet will write a message that describes the effects of running the cmdlet without actually performing any action.  Default: False | SwitchParameter | False | Named | False |
| Confirm | Defines that the cmdlet will display a prompt that asks if the user is sure that he wants to continue.  Default: True | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

None.

Example

Removing Organization Retention Policy Settings for Contacts and Calendars

This example shows how to remove retention policy settings for contacts and calendars of a specific organization.

|  |
| --- |
| $org = Get-VBOOrganization -Name "Atlanta"  $policysettings = Get-VBOOrganizationRetentionExclusion -Organization $org  Remove-VBOOrganizationRetentionExclusion -Exclusion $policysettings |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Set the Name parameter value. Save the result to the $org variable.
2. Run the [Get-VBOOrganizationRetentionExclusion](get-vboorganizationretentionexclusion.md) cmdlet. Set the $org variable as the Organization parameter value. Save the result to the $policysettings variable.
3. Run the Remove-VBOOrganizationRetentionExclusion cmdlet. Set the $policysettings variable as the Exclusion parameter value.

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationRetentionExclusion](get-vboorganizationretentionexclusion.md)


