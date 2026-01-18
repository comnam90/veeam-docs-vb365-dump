---
title: "VBOLicense"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbolicense.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOLicense


Contains details about an installed product license for Veeam Backup for Microsoft 365.

| Property | Type | Description |
| --- | --- | --- |
| Status | VBOLicenseStatus | Current status of the license. Possible values:   * Valid * Expired |
| ExpirationDate | DateTime? | Date and time when the license expires. |
| Type | VBOLicenseType | License type. Possible values:   * Subscription * Evaluation * NFR * Rental * Community * AwsPrivateOffer |
| Package | String | Information if Veeam Service Provider Console or Veeam One is allowed to monitor the Veeam Backup for Microsoft 365 server. |
| LicensedTo | String | Company to which the license was issued. |
| TotalNumber | Int | Total number of units within the license. |
| UsedNumber | Int | Number of units consumed by objects. |
| NewNumber | Int | Number of users with the new user status. |
| SupportId | String | Support ID. |
| LicenseId | GUID? | ID of the installed license. |
| Email | String | Email of a user to which the license was issued. |

Related Commands

[Get-VBOLicense](get-vbolicense.md)


