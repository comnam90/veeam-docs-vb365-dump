---
title: "Adding Microsoft 365 Organizations"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_add_office365_org.html"
last_updated: "5/6/2025"
product_version: "8.3.0.2201"
---

# Adding Microsoft 365 Organizations


You can add Microsoft 365 organizations to the Veeam Backup for Microsoft 365 infrastructure to back up data of these organizations and quickly restore it back to production servers in case of an unexpected disaster.

When you add Microsoft 365 organizations, you can use the following authentication methods:

* [Modern app-only authentication](adding_o365_organizations_sd.md)

When you use this method, Veeam Backup for Microsoft 365 uses Microsoft Entra application to authenticate to your Microsoft 365 organizations. You cannot use Veeam Backup account with the modern app-only authentication method. For limitations in Veeam Backup for Microsoft 365 functionality when protecting organizations with modern app-only authentication, see [this Veeam KB article](https://www.veeam.com/kb3146).

* Basic authentication

This functionality is only available in Microsoft Entra China region through REST API and PowerShell. To add Microsoft 365 organization using basic authentication method in Microsoft Entra China region, run the [Add-VBOOrganization](https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboorganization.html?ver=80) cmdlet or use the POST /Organizations method.

|  |
| --- |
| Important |
| When you plan to add Microsoft 365 organizations to Veeam Backup for Microsoft 365, consider the following:   * Modern authentication method with legacy protocols allowed is not supported.  * Basic authentication method is supported only for Microsoft Entra China region and will be deprecated in future versions of Veeam Backup for Microsoft 365. * Veeam Backup for Microsoft 365 drops support for Microsoft 365 organizations in Microsoft Entra Germany region. For more information about Azure Germany, see [this Microsoft article](https://learn.microsoft.com/en-us/azure/germany/). |


