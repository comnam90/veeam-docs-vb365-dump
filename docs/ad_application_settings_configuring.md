---
title: "ad_application_settings_configuring"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/ad_application_settings_configuring.html"
last_updated: "8/23/2024"
product_version: "8.3.0.2201"
---


In this article

For data restore using Microsoft Entra application, do the following to configure the application settings:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/).
2. Go to Identity > Applications > App registrations, and select an application.
3. Select Authentication > Advanced settings > Allow public client flows and set the Enable the following mobile and desktop flows option to Yes. For more information on application settings, see [this Microsoft article](https://docs.microsoft.com/en-us/azure/active-directory/develop/scenario-desktop-app-registration).

Keep in mind that this option is unavailable for legacy Microsoft Entra Germany region. In this region, you must register Microsoft Entra applications used for backup and restore as applications of the Public client/Native type.

1. Select Authentication > Platform configurations > Add a platform > Configure platforms > Mobile and desktop applications and specify a redirect URI for the application. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app#add-a-redirect-uri).

When creating a new Microsoft Entra application automatically, Veeam Backup for Microsoft 365 specifies http://localhost as a redirect URI.

Page updated 8/23/2024

Page content applies to build 8.3.0.2201
