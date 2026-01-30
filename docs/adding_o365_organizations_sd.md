---
title: "Adding Microsoft 365 Organizations with Modern App-Only Authentication"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/adding_o365_organizations_sd.html"
last_updated: "8/23/2024"
product_version: "8.3.0.2201"
---

# Adding Microsoft 365 Organizations with Modern App-Only Authentication


When you add an organization using the [modern app-only authentication method](https://docs.microsoft.com/en-us/office365/enterprise/hybrid-modern-auth-overview#:~:text=Modern%20Authentication%20is%20a%20method,domain%20Skype%20for%20Business%20hybrids.), you are required to provide [Microsoft Entra application](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/what-is-application-management) settings. Veeam Backup for Microsoft 365 uses such an application to establish a connection to your Microsoft 365 organizations and maintain data transfer during [backup](vbo_data_backup.md) and [restore](vbo_data_restore.md) sessions.

With modern app-only authentication, you cannot use Veeam Backup account; only communications through Microsoft Entra application is possible. For limitations in Veeam Backup for Microsoft 365 functionality when protecting organizations with modern app-only authentication, see [this Veeam KB article](https://www.veeam.com/kb3146).

To add a new Microsoft 365 organization to Veeam Backup for Microsoft 365, do the following:

1. [Launch the Add Organization wizard](launch_add_organization_wizard_sd.md).
2. [Select an organization deployment type](vbo_add_o365_sd.md).
3. [Select Microsoft Entra region and authentication method](vbo_add_o365_2_sd.md).
4. [Configure connection to Microsoft 365](choose_active_directory_application.md).
5. [Register or select Microsoft Entra Application](register_ad_application.md).
6. [Log in to Microsoft 365](login_to_microsoft.md).
7. [Finish the wizard](finish_wizard_sd.md).


