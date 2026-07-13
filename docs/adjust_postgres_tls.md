---
title: "Enabling TLS Encryption on PostgreSQL Instance"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/adjust_postgres_tls.html"
last_updated: "2026"
product_version: "8.5.0.1014"
---

# Enabling TLS Encryption on PostgreSQL Instance


To enhance security of the PostgreSQL instance, we recommend that you also enable the TLS encryption for the PostgreSQL instance traffic.

For more information on how to enable TLS on the PostgreSQL instance, see [this PostgreSQL article](https://www.postgresql.org/docs/current/runtime-config-connection.html#RUNTIME-CONFIG-CONNECTION-SSL).

To enable TLS manually on the Veeam Backup for Microsoft 365 server, run the [Set-VBOConfigurationParameter](https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboconfigurationparameter.html?ver=8) cmdlet.

Related Topics

[Security Guidelines](vbo_security_guidelines.md)

Page updated 2026-07-10

