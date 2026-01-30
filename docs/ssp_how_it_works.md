---
title: "How Restore Portal Works"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/ssp_how_it_works.html"
last_updated: "9/2/2024"
product_version: "8.3.0.2201"
---

# How Restore Portal Works


The following components are involved in the Restore Portal operation:

* Veeam Backup for Microsoft 365 server
* Veeam Backup for Microsoft 365 REST API Service
* Microsoft 365 organization
* Restore Portal
* Veeam Backup for Microsoft 365 Proxy Service

Veeam Backup for Microsoft 365 uses REST API and Microsoft Entra application when authenticating users to Restore Portal with their Microsoft 365 user account credentials. REST API authorization is based on the [OAuth 2.0 Authorization Framework](https://datatracker.ietf.org/doc/html/rfc6749). For more information on how to create and configure Microsoft Entra application to access Restore Portal, see [Creating or Configuring Microsoft Entra Application](ssp_create_new_app_wizard.md).

Restore Portal uses REST API to communicate with the Veeam Backup for Microsoft 365 server. For more information on how to configure REST API, see [REST API Settings](vbo_rest_api_settings.md).

Data exchange between the Veeam Backup for Microsoft 365 server, Microsoft 365 organization, Microsoft Entra application, Veeam Backup for Microsoft 365 REST API Service and Restore Portal is performed using SSL certificates. For more information, see [Installing SSL Certificates](vbo_installing_certificate.md).

Related Topics

[Configuring REST API and Restore Portal on Separate Machine](vbo_configuring_rest_separate.md)


