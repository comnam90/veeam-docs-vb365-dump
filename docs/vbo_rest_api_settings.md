---
title: "REST API Settings"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_rest_api_settings.html"
last_updated: "3/3/2026"
product_version: "8.3.0.2201"
---

# REST API Settings


You can use REST API to communicate with Veeam Backup for Microsoft 365. For more information, see [REST API Reference](https://helpcenter.veeam.com/references/vbo365/8/rest/).

Also, REST API is used by Restore Portal to communicate with the Veeam Backup for Microsoft 365 server. Restore Portal allows users to perform self-service restore. For more information about Restore Portal, see [Data Restore Using Restore Portal](ssp_restore.md).

To configure Veeam Backup for Microsoft 365 REST API settings, do the following:

1. In the main menu, click General Options.
2. Open the REST API tab.
3. Select the Enable REST service check box.
4. In the Authentication token lifetime field, specify the lifetime value for an authentication token (in minutes).

REST API authorization is based on the [OAuth 2.0 Authorization Framework](https://datatracker.ietf.org/doc/html/rfc6749).

1. In the HTTPS port field, specify a port number which you use to access Veeam Backup for Microsoft 365 REST API Service.

Also, Restore Portal uses this port to communicate with Veeam Backup for Microsoft 365 REST API Service. For more information, see [Ports](vbo_used_ports.md).

|  |
| --- |
| Note |
| The default value is 4443. If you use a different port, make sure that you configure the same value for the Restore Portal web address. Otherwise, Restore Portal will be unavailable. For more information, see [Register Microsoft Entra Application](ssp_create_new_app_2.md) and [Configure Microsoft Entra Application](ssp_configure_existing_app_3.md). |

1. Click Install to run the Select Certificate wizard and install the REST API certificate. Proceed to any of the following options:

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Generate a new self-signed certificate

|  |
| --- |
| Perform the following steps:   1. Select the Generate a new self-signed certificate option.   ![REST API Settings](images/select_certificate_wizard_step1_type.webp "Generating New Certificate")   1. Specify a certificate name and click Finish.   ![REST API Settings](images/select_certificate_wizard_step2_create_new.webp "Generating New Certificate") |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import an existing TLS certificate from the certificate store

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Select certificate from the Certificate Store of this server option.   ![REST API Settings](images/select_certificate_wizard_step1_type_2.webp "Selecting Certificate")   1. Select the certificate from the certificate store and click Finish.   |  | | --- | | Note | | A TLS certificate that you want to use must be added to the Personal certificate store. It also must have a private exportable key. |  ![REST API Settings](images/select_certificate_wizard_step2_pick_from_store.webp "Selecting Certificate") |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import a TLS certificate from a file in the PFX format

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Import certificate from a PFX file option.   ![REST API Settings](images/select_certificate_wizard_step1_type_3.webp "Importing Certificate")   1. Click Browse and select a PFX file. Specify the certificate password if required.   |  | | --- | | Note | | A TLS certificate that you want to use must have a private exportable key. |  ![REST API Settings](images/select_certificate_wizard_step2_import_file.webp "Importing Certificate")   1. Click Finish. |

1. If you want to use Swagger UI, select the Enable Swagger UI check box. If you do not require permanent access, leave the check box clear to reduce the potential attack surface.
2. Select the Enable restore operator authentication only check box to use REST API only for authentication of restore operators to Restore Portal. Keep in mind that if you enable this check box, all other REST API endpoints will be unavailable.
3. Click OK.

![REST API Settings](images/options_restapi_cert_installed.webp "Configuring REST API Settings")


