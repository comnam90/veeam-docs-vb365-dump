---
title: "Permissions for Azure Archiver Appliance"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/azure_archiver_appliance_permissions.html"
last_updated: "8/22/2024"
product_version: "8.3.0.2201"
---

# Permissions for Azure Archiver Appliance


Veeam Backup for Microsoft 365 allows you to use the Azure archiver appliance when the product copies backed-up data between different instances of Azure Blob Storage or to Azure Blob Storage Archive. To enable usage of the Azure archiver appliance, the Microsoft Azure service account is required.

A user account that you use to create Microsoft Entra application for the Microsoft Azure service account must be assigned the following roles:

* Application Administrator
* Owner of the Microsoft Azure subscription that you selected for the Microsoft Azure service account

Make sure that this user account is not a Contributor of the Microsoft Azure subscription that you selected for the Microsoft Azure service account.

If you prefer to use a custom application of your own for the Microsoft Azure service account, the following are minimal required permissions for this Microsoft Entra application:

|  |
| --- |
| {     "properties": {         "roleName": "APPLICATION\_MINIMAL\_PERMISSIONS",         "description": "APPLICATION\_MINIMAL\_PERMISSIONS",         "assignableScopes": [             "/subscriptions/\*"         ],         "permissions": [             {                 "actions": [                   "Microsoft.ApiManagement/service/subscriptions/read",                   "Microsoft.Storage/storageAccounts/read",                   "Microsoft.Resources/subscriptions/resourceGroups/read",                   "Microsoft.Resources/subscriptions/resourceGroups/write",                   "Microsoft.Compute/virtualMachines/\*",                   "Microsoft.Network/virtualNetworks/read",                   "Microsoft.Network/virtualNetworks/write",                   "Microsoft.Network/virtualNetworks/subnets/join/action",                   "Microsoft.Network/networkSecurityGroups/read",                   "Microsoft.Network/networkSecurityGroups/write",                   "Microsoft.Network/networkSecurityGroups/join/action",                   "Microsoft.Network/publicIPAddresses/read",                   "Microsoft.Network/publicIPAddresses/write",                   "Microsoft.Network/publicIPAddresses/delete",                   "Microsoft.Network/publicIPAddresses/join/action",                   "Microsoft.Network/networkInterfaces/\*",                   "Microsoft.Compute/disks/delete"                                   ],                 "notActions": [],                 "dataActions": [],                 "notDataActions": []             }         ]     }  } |

Related Topics

* [Configure Azure Archiver Appliance](new_azure_backup_proxy.md#appliance)
* [Adding Microsoft Azure Service Account](azure_service_account.md)
* [Azure Blob Storage Permissions](azure_archive_permissions.md)


