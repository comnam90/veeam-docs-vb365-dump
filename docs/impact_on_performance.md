---
title: "Impact of Multiple Backup Applications on Performance"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/impact_on_performance.html"
last_updated: "2/26/2026"
product_version: "8.3.0.2201"
---

# Impact of Multiple Backup Applications on Performance


Previously Veeam Backup for Microsoft 365 recommended you to add auxiliary Microsoft Entra applications to the product configuration for Microsoft 365 organizations added using modern app-only authentication. Such backup applications were intended to improve performance and minimize throttling from Microsoft 365 when backing up Microsoft SharePoint Online and Microsoft OneDrive for Business data.

Due to recent restrictions that were applied by Microsoft, Veeam Backup for Microsoft 365 invokes you to use a single Microsoft Entra application when backing up data in your production SharePoint environment.


