---
title: "set-vboorganizationretentionexclusion"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboorganizationretentionexclusion.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies retention policy settings for contacts and calendars of a specific organization.

Syntax

|  |
| --- |
| Set-VBOOrganizationRetentionExclusion -Exclusion <VBOOrganizationRetentionExclusion> [-Calendar] [-Contacts] [<CommonParameters>] |

Detailed Description

This cmdlet modifies retention policy settings for contacts and calendars of a specific organization. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Exclusion | Specifies retention policy settings for contacts and calendars of a specific organization. The cmdlet will modify these settings. | Accepts the VBOOrganizationRetentionExclusion object.  To get this object, run the [Get-VBOOrganizationRetentionExclusion](get-vboorganizationretentionexclusion.md) cmdlet. | True | Named | False |
| Calendar | Defines that Veeam Backup for Microsoft 365 will not apply retention policy for calendars of the specified organization.  Default: False  If you do not provide this parameter, Veeam Backup for Microsoft 365 will apply retention policy for calendars. | SwitchParameter | False | Named | False |
| Contacts | Defines that Veeam Backup for Microsoft 365 will not apply retention policy for contacts of the specified organization.  Default: False  If you do not provide this parameter, Veeam Backup for Microsoft 365 will apply retention policy for contacts. | SwitchParameter | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

This cmdlet returns the VBOOrganizationRetentionExclusion object that contains settings of organization retention policy for contacts and calendars.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Enabling Organization Retention Policy for Contacts

|  |  |
| --- | --- |
| This example shows how to enable organization retention policy for contacts.  |  | | --- | | $org = Get-VBOOrganization -Name "Atlanta"  $policysettings = Get-VBOOrganizationRetentionExclusion -Organization $org  Set-VBOOrganizationRetentionExclusion -Exclusion $policysettings -Contacts:$true |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Set the Name parameter value. Save the result to the $org variable. 2. Run the [Get-VBOOrganizationRetentionExclusion](get-vboorganizationretentionexclusion.md) cmdlet. Set the $org variable as the Organization parameter value. Save the result to the $policysettings variable. 3. Run the Set-VBOOrganizationRetentionExclusion cmdlet. Set the $policysettings variable as the Exclusion parameter value. Set the true value for the Contacts parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Enabling Organization Retention Policy for Calendars

|  |  |
| --- | --- |
| This example shows how to enable organization retention policy for calendars.  |  | | --- | | $org = Get-VBOOrganization -Name "Atlanta"  $policysettings = Get-VBOOrganizationRetentionExclusion -Organization $org  Set-VBOOrganizationRetentionExclusion -Exclusion $policysettings -Calendar:$true |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Set the Name parameter value. Save the result to the $org variable. 2. Run the [Get-VBOOrganizationRetentionExclusion](get-vboorganizationretentionexclusion.md) cmdlet. Set the $org variable as the Organization parameter value. Save the result to the $policysettings variable. 3. Run the Set-VBOOrganizationRetentionExclusion cmdlet. Set the $policysettings variable as the Exclusion parameter value. Set the true value for the Calendar parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Disabling Organization Retention Policy for Contacts

|  |  |
| --- | --- |
| This example shows how to disable organization retention policy for contacts.  |  | | --- | | $org = Get-VBOOrganization -Name "Atlanta"  $policysettings = Get-VBOOrganizationRetentionExclusion -Organization $org  Set-VBOOrganizationRetentionExclusion -Exclusion $policysettings -Contacts:$false |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Set the Name parameter value. Save the result to the $org variable. 2. Run the [Get-VBOOrganizationRetentionExclusion](get-vboorganizationretentionexclusion.md) cmdlet. Set the $org variable as the Organization parameter value. Save the result to the $policysettings variable. 3. Run the Set-VBOOrganizationRetentionExclusion cmdlet. Set the $policysettings variable as the Exclusion parameter value. Set the false value for the Contacts parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Disabling Organization Retention Policy for Calendars

|  |  |
| --- | --- |
| This example shows how to disable organization retention policy for calendars.  |  | | --- | | $org = Get-VBOOrganization -Name "Atlanta"  $policysettings = Get-VBOOrganizationRetentionExclusion -Organization $org  Set-VBOOrganizationRetentionExclusion -Exclusion $policysettings -Calendar:$false |  Perform the following steps:   1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Set the Name parameter value. Save the result to the $org variable. 2. Run the [Get-VBOOrganizationRetentionExclusion](get-vboorganizationretentionexclusion.md) cmdlet. Set the $org variable as the Organization parameter value. Save the result to the $policysettings variable. 3. Run the Set-VBOOrganizationRetentionExclusion cmdlet. Set the $policysettings variable as the Exclusion parameter value. Set the false value for the Calendar parameter. |

Related Commands

* [Get-VBOOrganization](get-vboorganization.md)
* [Get-VBOOrganizationRetentionExclusion](get-vboorganizationretentionexclusion.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
