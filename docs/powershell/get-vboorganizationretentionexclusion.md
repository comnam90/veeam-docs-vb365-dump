---
title: "Get-VBOOrganizationRetentionExclusion"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/get-vboorganizationretentionexclusion.html"
last_updated: "1/8/2026"
product_version: "8.3.0.2201"
---

# Get-VBOOrganizationRetentionExclusion


Short Description

Returns retention policy settings for contacts and calendars of a specific organization.

Syntax

|  |
| --- |
| Get-VBOOrganizationRetentionExclusion -Organization <VBOOrganization> [<CommonParameters>] |

Detailed Description

This cmdlet returns retention policy settings for contacts and calendars of a specific organization.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| Organization | Specifies a Microsoft organization. The cmdlet will return retention policy settings for this organization. | Accepts the [VBOOrganization](vboorganization.md) object.  To get this object, run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

This cmdlet returns the [VBOOrganizationRetentionExclusion](vboorganizationretentionexclusion.md) object that contains settings of organization retention policy for contacts and calendars.

Example

Getting Settings of Organization Retention Policy for Contacts and Calendar

This example shows how to get settings of a retention policy for contacts and calendars that are added to the Atlanta organization.

|  |
| --- |
| $org = Get-VBOOrganization -Name "Atlanta"  Get-VBOOrganizationRetentionExclusion -Organization $org  Organization                                                       SkipCalendar                            SkipContacts  ------------                                                       ------------                            ------------  abc.onmicrosoft.com                                                  False                                    True |

Perform the following steps:

1. Run the [Get-VBOOrganization](get-vboorganization.md) cmdlet. Set the Name parameter value. Save the result to the $org variable.
2. Run the Get-VBOOrganizationRetentionExclusion cmdlet. Set the $org variable as the Organization parameter value.

The cmdlet output will contain the settings of organization retention policy for contacts and calendars.

Related Commands

[Get-VBOOrganization](get-vboorganization.md)


