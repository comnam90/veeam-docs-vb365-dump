---
title: "Enabling Tenant Authentication"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_authentication_settings_tenants.html"
last_updated: "3/3/2026"
product_version: "8.3.0.2201"
---

# Enabling Tenant Authentication


Enabling tenant authentication is required for users from tenant organizations to view and restore backups that are located on the service provider side. To connect to Veeam Backup for Microsoft 365 and perform restore operations, tenants authenticate to the Veeam Backup for Microsoft 365 server with Microsoft organization credentials.

To enable tenant authentication, do the following:

1. In the main menu, click General Options.
2. Open the Authentication tab.
3. Select the Enable tenants authentication with organization credentials check box.
4. Click Install to run the Select Certificate wizard and install the tenant authentication certificate. Proceed to any of the following options:

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Generate a new self-signed certificate

|  |
| --- |
| Perform the following steps:   1. Select the Generate a new self-signed certificate option.   ![Enabling Tenant Authentication](images/select_certificate_wizard_step1_type.webp "Generating New Certificate")   1. Specify a certificate name and click Finish.   ![Enabling Tenant Authentication](images/select_certificate_wizard_step2_create_new.webp "Generating New Certificate") |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import an existing TLS certificate from the certificate store

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Select certificate from the Certificate Store of this server option.   ![Enabling Tenant Authentication](images/select_certificate_wizard_step1_type_2.webp "Selecting Certificate")   1. Select the certificate from the certificate store and click Finish.   |  | | --- | | Note | | A TLS certificate that you want to use must be added to the Personal certificate store. It also must have a private exportable key. |  ![Enabling Tenant Authentication](images/select_certificate_wizard_step2_pick_from_store.webp "Selecting Certificate") |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import a TLS certificate from a file in the PFX format

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Import certificate from a PFX file option.   ![Enabling Tenant Authentication](images/select_certificate_wizard_step1_type_3.webp "Importing Certificate")   1. Click Browse and select a PFX file. Specify the certificate password if required.   |  | | --- | | Note | | A TLS certificate that you want to use must have a private exportable key. |  ![Enabling Tenant Authentication](images/select_certificate_wizard_step2_import_file.webp "Importing Certificate")   1. Click Finish. |

|  |
| --- |
| Tip |
| You can use the same certificate for both Veeam Backup for Microsoft 365 and Veeam Backup & Replication. |

1. Click OK.

![Enabling Tenant Authentication](images/options_authentication_new.webp "Configuring Authentication Settings")


