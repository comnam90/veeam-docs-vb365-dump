---
title: "retrieving_backed_up_files"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/retrieving_backed_up_files.html"
last_updated: "9/2/2024"
product_version: "8.3.0.2201"
---


In this article

Data retrieval is the process of receiving temporary access to backup copies, so that backed-up data can be explored. You can retrieve backed-up data from the following object storage repositories: Azure Blob Storage Archive access tier, Amazon S3 Glacier Flexible Retrieval or Amazon S3 Glacier Deep Archive storage classes.

As well as data backup and backup copy, data retrieval is a job-driven process. When you want to access your data in backup copies stored in Azure Blob Storage Archive, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive, you create a retrieval job. For more information, see [Creating Retrieval Job](vbo_new_retrieval_job.md).

|  |
| --- |
| Note |
| Consider the following:   * You do not need to retrieve backed-up data from Amazon S3 Glacier Instant Retrieval storage class. For more information, see [Exploring Backup Copies](vbo_exploring_backup_copies.md). * If you want to view the created retrieval jobs and their statuses, in the inventory pane, open the Organizations view, select the Data retrieval node and view the list in the preview pane. |

When the retrieval job is complete, the retrieved data will be available for a specified period of time, during which you can [explore](vbo_exploring_retrieved.md) and [restore](https://helpcenter.veeam.com/docs/vbo365/explorers/explorers_introduction.html?ver=80) your data using Veeam Explorers. You can extend the availability period for data that Veeam Backup for Microsoft 365 has retrieved. For more information, see [Editing Retrieval Job Settings](editing_retrieval_job_settings.md) and [Extending Availability of Retrieved Data](vbo_extending_availability.md).

Data retrieval cost varies depending on the desired speed of the process. You can select an option that you prefer at the [Select Retrieval Mode](retrieval_mode.md) step of the Retrieve Backup Copy wizard. Keep in mind that options differ for Azure Blob Storage Archive, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes.

In This Section

* [Creating Retrieval Job](vbo_new_retrieval_job.md)
* [Editing Retrieval Job Settings](editing_retrieval_job_settings.md)
* [Extending Availability of Retrieved Data](vbo_extending_availability.md)

Page updated 9/2/2024

Page content applies to build 8.3.0.2201
