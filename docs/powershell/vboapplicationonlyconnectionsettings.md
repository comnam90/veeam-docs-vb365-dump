---
title: "VBOApplicationOnlyConnectionSettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vboapplicationonlyconnectionsettings.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOApplicationOnlyConnectionSettings


Contains details about Microsoft Entra application settings.

| Property | Type | Description |
| --- | --- | --- |
| ApplicationId | GUID | Microsoft Entra application ID. |
| AuthenticationType | VBOOffice365AuthenticationType | Authentication type. Possible values:   * Basic * Modern * ApplicationOnly |
| ImpersonationAccountName | String | User name to authenticate to the Microsoft Exchange server. |
| OfficeOrganizationName | String | Name of a Microsoft organization to authenticate to the Microsoft 365 server. |
| NewApplicationName | String | Name of the new Microsoft Entra application. |
| ConfigureApplication | Bool | If True, Veeam Backup for Microsoft 365 automatically assigns the certificate and required permissions to the Microsoft Entra application. |
| ApplicationCertificateThumbprint | String | The application certificate thumbprint for connecting to Microsoft Entra. |
| ApplicationCertificatePath | String | Path to the folder where the application certificate is located. |
| ApplicationCertificatePassword | SecureString | Certificate password. |
| SharePointSaveAllWebParts | Bool | If True, SharePoint Web Parts are added to Microsoft Entra application settings. |

Related Commands

* [New-VBOOffice365ApplicationOnlyConnectionSettings](new-vbooffice365applicationonlyconnectionsettings.md)
* [Set-VBOOffice365ApplicationOnlyConnectionSettings](set-vbooffice365applicationonlyconnectionsettings.md)


