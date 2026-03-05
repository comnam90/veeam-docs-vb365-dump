---
title: "Enabling Restore Operator Authentication"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_authentication_settings_restore_operators.html"
last_updated: "3/3/2026"
product_version: "8.3.0.2201"
---

# Enabling Restore Operator Authentication


Enabling restore operator authentication is required if you want to configure Restore Portal. Restore operators use Restore Portal to view and restore data from backups created by Veeam Backup for Microsoft 365 for other users, groups, sites, teams or the entire Microsoft 365 organization. To connect to Veeam Backup for Microsoft 365 and perform restore operations, restore operators authenticate to the Veeam Backup for Microsoft 365 server with their Microsoft 365 credentials.

|  |
| --- |
| Note |
| To configure access to Veeam Backup for Microsoft 365 for restore operators from multiple tenant organizations, you must also [enable tenant authentication](vbo_authentication_settings_tenants.md). |

To enable restore operator authentication, do the following:

1. In the main menu, click General Options.
2. Open the Authentication tab.
3. Select the Enable restore operator authentication with Microsoft credentials check box.
4. Click Install to run the Select Certificate wizard and install the restore operator authentication certificate. Proceed to any of the following options:

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Generate a new self-signed certificate

|  |
| --- |
| Perform the following steps:   1. Select the Generate a new self-signed certificate option.   ![Enabling Restore Operator Authentication](images/select_certificate_wizard_step1_type.webp "Generating New Certificate")   1. Specify a certificate name and click Finish.   ![Enabling Restore Operator Authentication](images/select_certificate_wizard_step2_create_new.webp "Generating New Certificate") |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import an existing TLS certificate from the certificate store

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Select certificate from the Certificate Store of this server option.   ![Enabling Restore Operator Authentication](images/select_certificate_wizard_step1_type_2.webp "Selecting Certificate")   1. Select the certificate from the certificate store and click Finish.   |  | | --- | | Note | | A TLS certificate that you want to use must be added to the Personal certificate store. It also must have a private exportable key. |  ![Enabling Restore Operator Authentication](images/select_certificate_wizard_step2_pick_from_store.webp "Selecting Certificate") |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Import a TLS certificate from a file in the PFX format

|  |  |  |
| --- | --- | --- |
| Perform the following steps:   1. Select the Import certificate from a PFX file option.   ![Enabling Restore Operator Authentication](images/select_certificate_wizard_step1_type_3.webp "Importing Certificate")   1. Click Browse and select a PFX file. Specify the certificate password if required.   |  | | --- | | Note | | A TLS certificate that you want to use must have a private exportable key. |  ![Enabling Restore Operator Authentication](images/select_certificate_wizard_step2_import_file.webp "Importing Certificate")   1. Click Finish. |

|  |
| --- |
| Note |
| If you have installed the Veeam Backup for Microsoft 365 REST API component on a separate machine and generated a new self-signed certificate for restore operators, you must import this certificate to the Trusted Root Certification Authorities certificate store on the separate machine with REST API installed. |

1. Click OK.

![Enabling Restore Operator Authentication](images/options_authentication_new.webp "Configuring Authentication Settings")


