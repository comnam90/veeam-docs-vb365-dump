---
title: "azure_object_storage_settings"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/azure_object_storage_settings.html"
last_updated: "8/26/2024"
product_version: "8.3.0.2201"
---


In this article

At this step of the wizard, specify object storage container and folder where you want to save your data.

1. From the Container drop-down list, select an Azure Blob Storage container.

Make sure that the container you want to use to store your data was created in advance; Veeam Backup for Microsoft 365 does not support creating new containers.

1. In the Folder field, select a cloud folder to which you want to map your object storage repository, and which will be used to store backups.

To select a folder, click Browse and either select an existing folder or create a new one by clicking New Folder.

For more information on how data is stored, see [Object Storage Repository Structure](object_storage_structure.md).

1. Select the Limit object storage consumption to check box and specify the limit value in GB, TB or PB.

If you select this check box, Veeam Backup for Microsoft 365 limits capacity of the object storage repository and prohibits running new jobs when the specified value is exceeded.

[![Object Storage Container](images/new_object_storage_4_azure.webp)](images/new_object_storage_4_azure.webp "Object Storage Container")

Page updated 8/26/2024

Page content applies to build 8.3.0.2201
