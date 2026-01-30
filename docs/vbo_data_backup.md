---
title: "Data Backup"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_data_backup.html"
last_updated: "8/15/2025"
product_version: "8.3.0.2201"
---

# Data Backup


To back up data of your [Microsoft organizations](vbo_managing_organizations.md), you use backup jobs.

A backup job is a configuration unit of the backup activity. A backup job defines a list of users, groups, sites, teams, and organizations to back up, a location where to store backups, a schedule according to which new backups must be created. The first backup job session always produces a full backup of all objects included to a backup job scope. Subsequent backup job sessions are incremental, processing only those objects that have changed since the previous backup job session, as long as no new objects are added to the backup job scope. If new objects that have not been backed up before are added to the backup job scope, the subsequent backup job session is considered a full run.

If you back up data of you Microsoft organizations to an object storage repository, Veeam Backup for Microsoft 365 allows you to prohibit deletion of data from the object storage repository by making that data temporarily immutable and to protect data against malware activity. For more information about protecting data in backups, see [Immutability](immutability.md).

In This Section

* [Organization Object Types](vbo_object_types.md)
* [How Backup Works](how_backup_works.md)
* [Creating Backup Job](vbo_new_backup_job.md)
* [Managing Backup Jobs](managing_backup_jobs.md)


