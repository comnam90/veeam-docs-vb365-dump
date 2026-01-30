---
title: "Step 5. Select Service Account"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/add_linux_proxy_service_acc.html"
last_updated: "9/6/2024"
product_version: "8.3.0.2201"
---

# Step 5. Select Service Account


At this step of the wizard, specify an account that will be used to run Veeam Backup for Microsoft 365 Proxy Service on the [specified computer](vbo_proxy_server_address_linux.md).

To do this, select one of the following options:

* veeam365backup account. Select this option to use the default service account created by Veeam Backup for Microsoft 365.
* Use the following account. Select this option to use an account that already exists. In the Account field, enter a user name.

You must manually grant this account the [required permissions](permissions_linux.md) in advance.

* Create the following user account locally and assign the required permissions. Select this option to create a new account that Veeam Backup for Microsoft 365 will use as the service account. In the Account field, enter a user name.

Veeam Backup for Microsoft 365 will create a new service account and automatically grant the [required permissions](permissions_linux.md) to this account.

[![Adding Backup Proxy Server](images/add_proxy_linux_credentials.webp)](images/add_proxy_linux_credentials.webp "Adding Backup Proxy Server")


