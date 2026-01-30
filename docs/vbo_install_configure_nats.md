---
title: "Step 9. Configure NATS Server"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_install_configure_nats.html"
last_updated: "10/21/2024"
product_version: "8.3.0.2201"
---

# Step 9. Configure NATS Server


This step is only available if you have selected to configure installation settings manually at the [Review Default Installation Settings](vbo_install_default_settings.md) step of the wizard.

At the NATS Server step, specify settings to connect to the NATS server. For more information about the NATS server, see [NATS Server](architecture.md#nats).

To specify connection settings for the NATS server, do the following:

1. Select one of the following options:

* Install new instance. Select this option to install a new NATS server instance on the target machine.
* Use existing instance. Select this option to use an already installed NATS server instance and enter the instance name in the <host\_name>:<port> format.

1. Specify credentials to connect to the NATS server.

|  |
| --- |
| Important |
| By default, the NATS server that you deploy along with Veeam Backup for Microsoft 365 on the target machine does not use the TLS encryption. For more information, see [Enabling TLS Encryption on NATS Server](adjust_nats_instance.md). |

[![Installing Veeam Backup for Microsoft 365](images/vbo_iso_setup_nats.webp)](images/vbo_iso_setup_nats.webp "Installing Veeam Backup for Microsoft 365")


