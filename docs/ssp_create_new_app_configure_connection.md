---
title: "Step 2. Configure Connection to Restore Portal"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/ssp_create_new_app_configure_connection.html"
last_updated: "1/31/2025"
product_version: "8.3.0.2201"
---

# Step 2. Configure Connection to Restore Portal


At this step of the wizard, choose whether you want to register a new [Microsoft Entra application](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/what-is-application-management) to connect to Restore Portal or configure an existing Microsoft Entra application.

You can select one of the following options:

* Register a new Microsoft Entra ID application automatically

With this option selected, Veeam Backup for Microsoft 365 requires to provide an application name, a certificate to register a new Microsoft Entra application in Microsoft Entra ID and specify web address of a machine with the Veeam Backup for Microsoft 365 REST API component installed. For more information, see [Registering New Microsoft Entra Application](ssp_create_new_app_2.md#cna).

* Use an existing Microsoft Entra ID application

With this option selected, Veeam Backup for Microsoft 365 requires to modify connection parameters of the existing Microsoft Entra application. For more information, see [Configuring Existing Microsoft Entra Application](ssp_create_new_app_2.md#conf_ea).

[![Configure Connection to Restore Portal](images/ssp_ad_application_selection.webp)](images/ssp_ad_application_selection.webp "Configure Connection to Restore Portal")


