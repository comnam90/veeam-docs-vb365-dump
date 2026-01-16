---
title: "ssp_ad_application_permissions"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/ssp_ad_application_permissions.html"
last_updated: "8/22/2024"
product_version: "8.3.0.2201"
---


In this article

The following table lists permissions for Microsoft Entra applications that are granted automatically by Veeam Backup for Microsoft 365 when you [configure the Restore Portal settings](vbo_restore_portal_settings.md).

If you prefer to use a custom application of your own, make sure to grant all the permissions listed in this table manually.

All listed permissions are of the Delegated type.

| API | Permission name | Description |
| --- | --- | --- |
| Microsoft Graph | User.Read | Sign in and read user profile. |
| <Microsoft Entra application> | access\_as\_user | Obtain an access token on behalf of the user to implement On-Behalf-Of flow.  For more information about On-Behalf-Of flow, see [this Microsoft article](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow).  For more information on how to expose a web API, see [this Microsoft article](https://docs.microsoft.com/en-gb/azure/active-directory/develop/quickstart-configure-app-expose-web-apis). |

Page updated 8/22/2024

Page content applies to build 8.3.0.2201
