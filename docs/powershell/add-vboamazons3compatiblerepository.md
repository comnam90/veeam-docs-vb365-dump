---
title: "add-vboamazons3compatiblerepository"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/add-vboamazons3compatiblerepository.html"
last_updated: "10/2/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Adds S3 Compatible object storage repository to the Veeam Backup for Microsoft 365 infrastructure.

Syntax

This cmdlet provides parameter sets that allow you to:

* Add S3 Compatible object storage repository with the default retention period.

|  |
| --- |
| Add-VBOAmazonS3CompatibleRepository [-ImmutabilityPeriodDays <Int32>] -ObjectStorageSettings <VBOAmazonS3ObjectStorageRepository> [-ObjectStorageEncryptionKey <IVBOCredentialKey>] [-SyncNow] [-SizeLimit <UInt64>] [-EnableImmutability] [-EnableImmutabilityGovernanceMode] [-Proxy <VBOProxy>] [-ProxyPool <VBOProxyPool>] -Name <String> [-Description <String>] [-RetentionType <VBORetentionType>] [-Force] [<CommonParameters>] |

* Add S3 Compatible object storage repository. The retention period set to years and retention policy applied daily.

|  |
| --- |
| Add-VBOAmazonS3CompatibleRepository [-ImmutabilityPeriodDays <Int32>] -ObjectStorageSettings <VBOAmazonS3ObjectStorageRepository> -RetentionPeriod <VBORetentionPeriod> -RetentionFrequencyType <VBORetentionFrequencyType> -DailyTime <TimeSpan> -DailyType <VBODailyType> [-ObjectStorageEncryptionKey <IVBOCredentialKey>] [-SyncNow] [-SizeLimit <UInt64>] [-EnableImmutability] [-EnableImmutabilityGovernanceMode] [-Proxy <VBOProxy>] [-ProxyPool <VBOProxyPool>] -Name <String> [-Description <String>] [-RetentionType <VBORetentionType>] [-Force] [<CommonParameters>] |

* Add S3 Compatible object storage repository. The retention period set to years and retention policy applied monthly.

|  |
| --- |
| Add-VBOAmazonS3CompatibleRepository [-ImmutabilityPeriodDays <Int32>] -ObjectStorageSettings <VBOAmazonS3ObjectStorageRepository> -RetentionPeriod <VBORetentionPeriod> -RetentionFrequencyType <VBORetentionFrequencyType> -MonthlyTime <TimeSpan> -MonthlyDayNumber <VBOMonthlyDayNumber> -MonthlyDayOfWeek <DayOfWeek> [-ObjectStorageEncryptionKey <IVBOCredentialKey>] [-SyncNow] [-SizeLimit <UInt64>] [-EnableImmutability] [-EnableImmutabilityGovernanceMode] [-Proxy <VBOProxy>] [-ProxyPool <VBOProxyPool>] -Name <String> [-Description <String>] [-RetentionType <VBORetentionType>] [-Force] [<CommonParameters>] |

* Add S3 Compatible object storage repository with the custom retention period. Veeam Backup for Microsoft 365 applies the retention policy daily.

|  |
| --- |
| Add-VBOAmazonS3CompatibleRepository [-ImmutabilityPeriodDays <Int32>] -ObjectStorageSettings <VBOAmazonS3ObjectStorageRepository> -CustomRetentionPeriodType <VBORetentionPeriodType> -CustomRetentionPeriod <Int32> -RetentionFrequencyType <VBORetentionFrequencyType> -DailyTime <TimeSpan> -DailyType <VBODailyType> [-ObjectStorageEncryptionKey <IVBOCredentialKey>] [-SyncNow] [-SizeLimit <UInt64>] [-EnableImmutability] [-EnableImmutabilityGovernanceMode] [-Proxy <VBOProxy>] [-ProxyPool <VBOProxyPool>] -Name <String> [-Description <String>] [-RetentionType <VBORetentionType>] [-Force] [<CommonParameters>] |

* Add S3 Compatible object storage repository with the custom retention period. Veeam Backup for Microsoft 365 applies the retention policy monthly.

|  |
| --- |
| Add-VBOAmazonS3CompatibleRepository [-ImmutabilityPeriodDays <Int32>] -ObjectStorageSettings <VBOAmazonS3ObjectStorageRepository> -CustomRetentionPeriodType <VBORetentionPeriodType> -CustomRetentionPeriod <Int32> -RetentionFrequencyType <VBORetentionFrequencyType> -MonthlyTime <TimeSpan> -MonthlyDayNumber <VBOMonthlyDayNumber> -MonthlyDayOfWeek <DayOfWeek> [-ObjectStorageEncryptionKey <IVBOCredentialKey>] [-SyncNow] [-SizeLimit <UInt64>] [-EnableImmutability] [-EnableImmutabilityGovernanceMode] [-Proxy <VBOProxy>] [-ProxyPool <VBOProxyPool>] -Name <String> [-Description <String>] [-RetentionType <VBORetentionType>] [-Force] [<CommonParameters>] |

Detailed Description

This cmdlet adds a backup repository of S3 Compatible object storage type to the Veeam Backup for Microsoft 365 infrastructure. Veeam Backup for Microsoft 365 uses backup repositories as storage systems for backups and backup copies created for Microsoft 365 and on-premises Microsoft organizations. Every backup repository has the retention policy that defines how long you want to keep backups on a backup repository.

You can specify the following retention policy settings:

* Retention period to specify how long you want to keep data on a backup repository. You can set the period to years, months or days.
* Retention policy schedule to specify the day and time when Veeam Backup for Microsoft 365 must check the backup repository and remove the outdated backups. You can set the schedule to daily or monthly.
* Retention policy type to set it to Item-level or to snapshot-based types.

For more information on retention policy, see the [Retention Policy](https://helpcenter.veeam.com/docs/vbo365/guide/retention_policy.html?ver=80) section of the Veeam Backup for Microsoft 365 User Guide.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| ImmutabilityPeriodDays | Specifies the number of days when your data will be blocked for deletion or modification.  Note: If you set the null or 0 value, data will be blocked for deletion or modification for the same period as the retention period. | Int32 | False | Named | False |
| ObjectStorageSettings | Specifies S3 Compatible object storage, IBM Cloud Object Storage or Wasabi Cloud Object Storage settings. | Accepts the VBOAmazonS3ObjectStorageRepository object.  To get this object, run the [New-VBOAmazonS3CompatibleObjectStorageSettings](new-vboamazons3compatibleobjectstoragesettings.md) cmdlet. | True | Named | False |
| ObjectStorageEncryptionKey | Specifies object storage encryption key. Veeam Backup for Microsoft 365 will encrypt data that is saved to this object storage repository. | IVBOCredentialKey  Accepts the VBOEncryptionKey object.  To get this object, run the [Get-VBOEncryptionKey](get-vboencryptionkey.md) cmdlet. | False | Named | False |
| SyncNow | Defines that the cmdlet will start to synchronize cache between the object storage repository and the PersistentCache database on the PostgreSQL instance.  Default: False | SwitchParameter | False | Named | False |
| SizeLimit | Specifies a soft limit in GB for the object storage repository consumption that can be exceeded temporarily. If the specified limit is exceeded, Veeam Backup for Microsoft 365 will not run a new job.  Permitted values: 1024–1073741824.  Default: 1024  Note: In PowerShell you can specify a soft limit in GB only. | UInt64 | False | Named | False |
| EnableImmutability | Defines that the cmdlet will add the object storage repository to the Veeam Backup for Microsoft 365 infrastructure with the immutability feature enabled. Veeam Backup for Microsoft 365 allows you to prohibit deletion of data from the object storage repository by making that data temporarily immutable and to protect data against malware activity.  For more information about the immutability feature, see the [Immutability](https://helpcenter.veeam.com/docs/vbo365/guide/immutability.html?ver=80) section of the Veeam Backup for Microsoft 365 User Guide.  Default: False | SwitchParameter | False | Named | False |
| EnableImmutabilityGovernanceMode | Defines that a storage administrator with specific permissions to be allowed to override the lock settings and to delete the protected backups in the object storage repository added by the cmdlet.  Default: False | SwitchParameter | False | Named | False |
| Proxy | Specifies a backup proxy server. The cmdlet will map a new S3 Compatible object storage repository to this backup proxy server. | Accepts the VBOProxy object.  To get this object, run the [Get-VBOProxy](get-vboproxy.md) cmdlet. | False | Named | False |
| ProxyPool | Specifies a backup proxy pool. The cmdlet will map a new S3 Compatible object storage repository to this backup proxy pool. | Accepts the VBOProxyPool object.  To get this object, run the [Get-VBOProxyPool](get-vboproxypool.md) cmdlet. | False | Named | False |
| Name | Specifies a name of S3 Compatible object storage repository. The cmdlet will add an object storage repository with this name. | String | True | Named | False |
| Description | Specifies a description of S3 Compatible object storage repository. The cmdlet will add an object storage repository with this description.  The default description contains information on the user who added the object storage repository, date and time when the object storage repository was added. | String | False | Named | False |
| RetentionType | Specifies a type of retention policy. You can set either of the following types:   * ItemLevel * SnapshotBased   Default: SnapshotBased | VBORetentionType | False | Named | False |
| Force | Defines that the cmdlet will add the object storage repository to the Veeam Backup for Microsoft 365 infrastructure without notifying the user.  Default: False | SwitchParameter | False | Named | False |
| RetentionPeriod | Specifies the retention period in years. Veeam Backup for Microsoft 365 will remove items from the object storage repository once this period is passed. You can set either of the following periods:   * Year1 * Years2 * Years3 * Years5 * Years7 * Years10 * Years25 * KeepForever   Default: Years3  Note: Apply the CustomRetentionPeriodType parameter to set the retention period in months or days. | VBORetentionPeriod | True | Named | False |
| RetentionFrequencyType | Specifies retention policy schedule. Veeam Backup for Microsoft 365 will check the object storage repository and will remove the outdated backups according to this schedule. You can set either of the following types of schedule:   * Daily: to check and remove the outdated backups once a day. * Monthly: to check and remove the outdated backups once a month.   Default: Daily | VBORetentionFrequencyType | True | Named | False |
| DailyTime | For daily retention policy schedule.  Specifies the time of the day when Veeam Backup for Microsoft 365 must apply the retention policy.  Default: 00:00:00 | TimeSpan | True | Named | False |
| DailyType | For daily retention policy schedule.  Specifies the days when Veeam Backup for Microsoft 365 must apply the retention policy:   * Sunday * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday * Everyday * Workdays * Weekends   Default: Everyday | VBODailyType | True | Named | False |
| MonthlyTime | For monthly retention policy schedule.  Specifies the time of the day when Veeam Backup for Microsoft 365 must apply the retention policy.  Default: 18:00:00 | TimeSpan | True | Named | False |
| MonthlyDayNumber | For monthly retention policy schedule.  Specifies the order number for the day of the week when Veeam Backup for Microsoft 365 must apply the retention policy.   * First * Second * Third * Fourth * Last   Default: First | VBOMonthlyDayNumber | True | Named | False |
| MonthlyDayOfWeek | For monthly retention policy schedule.  Specifies the day of the week when Veeam Backup for Microsoft 365 must apply the retention policy.   * Sunday * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday   Default: Monday | DayOfWeek | True | Named | False |
| CustomRetentionPeriodType | Specifies a type of custom retention period. Veeam Backup for Microsoft 365 will remove items from the object storage repository once this period is passed. You can set the custom retention period to either of the following types:   * Months * Days   Set the CustomRetentionPeriod parameter to specify the number of days or the number of months. | VBORetentionPeriodType | True | Named | False |
| CustomRetentionPeriod | For the CustomRetentionPeriodType option.  Specifies the retention period to keep data on the object storage repository. The retention period is defined according to the CustomRetentionPeriod settings:   * Sets the retention period to the number of months if the CustomRetentionPeriodType parameter is set to Months. * Sets the retention period to the number of days if the CustomRetentionPeriodType parameter is set to Days.   Veeam Backup for Microsoft 365 will remove items from the object storage repository once this period is passed. | Int32 | True | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3CompatibleRepository object that contains settings of S3 Compatible object storage repository.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Adding S3 Compatible Object Storage with Default Retention Policy Period

|  |  |
| --- | --- |
| This example shows how to add the S3 Compatible Backup object storage repository. The retention type is set to snapshot-based.  |  | | --- | | $proxy = Get-VBOProxy -Hostname support.north.local  $account = Get-VBOAmazonS3CompatibleAccount -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000"  $bucket = Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  $settings = New-VBOAmazonS3CompatibleObjectStorageSettings -Folder $folder  Add-VBOAmazonS3CompatibleRepository -Proxy $proxy -Name "S3 Compatible Backup" -Description "Backup" -RetentionType SnapshotBased -ObjectStorageSettings $settings |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 2. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 3. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable. 4. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3CompatibleConnectionSettings parameter value. Specify the Name parameter value. Save the result to the $bucket variable. 5. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. Save the result to the $folder variable. 6. Run the [New-VBOAmazonS3CompatibleObjectStorageSettings](new-vboamazons3compatibleobjectstoragesettings.md) cmdlet. Set the $folder variable as the Folder parameter value. Save the result to the $settings variable. 7. Run the Add-VBOAmazonS3CompatibleRepository cmdlet. Specify the following settings:  * Set the $proxy variable as the Proxy parameter value. * Specify the Name parameter value. * Specify the Description parameter value. * Set SnapshotBased as the RetentionType parameter value. * Set the $settings variable as the ObjectStorageSettings parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Adding S3 Compatible Object Storage with Yearly Retention Period [Policy Applied Daily]

|  |  |
| --- | --- |
| This example shows how to add the S3 Compatible Backup object storage repository.  The retention settings will be the following:   * The retention period is set to 1 year. * Veeam Backup for Microsoft 365 will check the object storage repository and remove the outdated backups daily at 3:00 PM. * The retention type is item-level.   |  | | --- | | $proxy = Get-VBOProxy -Id d96f55a4-d15d-410b-b0f0-d51d17ccdab6  $account = Get-VBOAmazonS3CompatibleAccount -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000"  $bucket = Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  $settings = New-VBOAmazonS3CompatibleObjectStorageSettings -Folder $folder  Add-VBOAmazonS3CompatibleRepository -Proxy $proxy -Name "S3 Compatible Backup" -RetentionPeriod Year1 -RetentionFrequencyType Daily -DailyTime 15:00:00 -DailyType Everyday -Description "Daily Backup" -RetentionType ItemLevel -ObjectStorageSettings $settings |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Id parameter value. Save the result to the $proxy variable. 2. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 3. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable. 4. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3CompatibleConnectionSettings parameter value. Specify the Name parameter value. Save the result to the $bucket variable. 5. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. Save the result to the $folder variable. 6. Run the [New-VBOAmazonS3CompatibleObjectStorageSettings](new-vboamazons3compatibleobjectstoragesettings.md) cmdlet. Set the $folder variable as the Folder parameter value. Save the result to the $settings variable. 7. Run the Add-VBOAmazonS3CompatibleRepository cmdlet. Specify the following settings:  * Set the $proxy variable as the Proxy parameter value. * Specify the Name parameter value.  * Set Year1 as the RetentionPeriod parameter value. * Set Daily as the RetentionFrequencyType parameter value. * Set 15:00:00 as the DailyTime parameter value. * Set Everyday as the DailyType parameter value.  * Specify the Description parameter value.  * Set ItemLevel as the RetentionType parameter value.  * Set the $settings variable as the ObjectStorageSettings parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Adding S3 Compatible Object Storage with Yearly Retention Period [Policy Applied Monthly]

|  |  |
| --- | --- |
| This example shows how to add the S3 Compatible Backup object storage repository.  The retention settings will be the following:   * The retention period is 2 years. * Veeam Backup for Microsoft 365 will check the object storage repository and remove the outdated backups every last Sunday at 2:00 PM.  * The retention type is snapshot-based.   |  | | --- | | $proxy = Get-VBOProxy -Hostname support.south.local  $account = Get-VBOAmazonS3CompatibleAccount -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000"  $bucket = Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  $settings = New-VBOAmazonS3CompatibleObjectStorageSettings -Folder $folder  Add-VBOAmazonS3CompatibleRepository -Proxy $proxy -Name "S3 Compatible Backup" -RetentionPeriod Year2 -RetentionFrequencyType Monthly -MonthlyTime 14:00:00 -MonthlyDayNumber Last -MonthlyDayOfWeek Sunday -Description "Monthly Backup" -RetentionType SnapshotBased -ObjectStorageSettings $settings |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 2. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 3. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable. 4. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3CompatibleConnectionSettings parameter value. Specify the Name parameter value. Save the result to the $bucket variable. 5. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. Save the result to the $folder variable. 6. Run the [New-VBOAmazonS3CompatibleObjectStorageSettings](new-vboamazons3compatibleobjectstoragesettings.md) cmdlet. Set the $folder variable as the Folder parameter value. Save the result to the $settings variable. 7. Run the Add-VBOAmazonS3CompatibleRepository cmdlet. Specify the following settings:  * Set the $proxy variable as the Proxy parameter value.  * Specify the Name parameter value. * Set Years2 as the RetentionPeriod parameter value. * Set Monthly as the RetentionFrequencyType parameter value. * Set 14:00:00 as the MonthlyTime parameter value. * Set Last as the MonthlyDayNumber parameter value. * Set Sunday as the MonthlyDayOfWeek parameter value. * Specify the Description parameter value. * Set SnapshotBased as the RetentionType parameter value.  * Set the $settings variable as the ObjectStorageSettings parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Adding S3 Compatible Object Storage with Custom Retention period [Policy Applied Daily]

|  |  |
| --- | --- |
| This example shows how to add the S3 Compatible Backup object storage repository.  The retention settings will be the following:   * The retention period is 3 months. * Veeam Backup for Microsoft 365 will check the object storage repository and remove the outdated backups daily at 12:00 PM.  * The retention type is snapshot-based.   |  | | --- | | $proxy = Get-VBOProxy -Id d96f55a4-d15d-410b-b0f0-d51d17ccdab6  $account = Get-VBOAmazonS3CompatibleAccount -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000"  $bucket = Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  $settings = New-VBOAmazonS3CompatibleObjectStorageSettings -Folder $folder  Add-VBOAmazonS3CompatibleRepository -Proxy $proxy -Name "S3 Compatible Backup" -CustomRetentionPeriodType Months -CustomRetentionPeriod 3 -RetentionFrequencyType Daily -DailyTime 12:00:00 -DailyType Workdays -Description "Daily Backup" -RetentionType SnapshotBased -ObjectStorageSettings $settings |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Id parameter value. Save the result to the $proxy variable. 2. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 3. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable. 4. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3CompatibleConnectionSettings parameter value. Specify the Name parameter value. Save the result to the $bucket variable. 5. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. Save the result to the $folder variable. 6. Run the [New-VBOAmazonS3CompatibleObjectStorageSettings](new-vboamazons3compatibleobjectstoragesettings.md) cmdlet. Set the $folder variable as the Folder parameter value. Save the result to the $settings variable. 7. Run the Add-VBOAmazonS3CompatibleRepository cmdlet. Specify the following settings:  * Set the $proxy variable as the Proxy parameter value. * Specify the Name parameter value. * Set Months as the CustomRetentionPeriodType parameter value. * Set 3 as the CustomRetentionPeriod parameter value. * Set Daily as the RetentionFrequencyType parameter value. * Set 12:00:00 as the DailyTime parameter value. * Set Workdays as the DailyType parameter value. * Specify the Description parameter value. * Set SnapshotBased as the RetentionType parameter value.  * Set the $settings variable as the ObjectStorageSettings parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 5: Adding S3 Compatible Object Storage with Custom Retention period [Policy Applied Monthly]

|  |  |
| --- | --- |
| This example shows how to add the S3 Compatible Backup object storage repository.  The retention settings will be the following:   * The retention period is 7 days.  * Veeam Backup for Microsoft 365 will check the object storage repository and remove the outdated backups every first Monday at 8:00 AM.  * The retention type is item-level.   |  | | --- | | $proxy = Get-VBOProxy -Hostname support.west.local  $account = Get-VBOAmazonS3CompatibleAccount -Id 26e61916-0257-4a05-8f65-204628d2ed7a  $connection = New-VBOAmazonS3CompatibleConnectionSettings -Account $account -ServicePoint "172.17.186.13:9000"  $bucket = Get-VBOAmazonS3Bucket -AmazonS3CompatibleConnectionSettings $connection -Name "BucketName"  $folder = Get-VBOAmazonS3Folder -Bucket $bucket -Name "FolderName"  $settings = New-VBOAmazonS3CompatibleObjectStorageSettings -Folder $folder  Add-VBOAmazonS3CompatibleRepository -Proxy $proxy -Name "S3 Compatible Backup" -CustomRetentionPeriodType Days -CustomRetentionPeriod 7 -RetentionFrequencyType Monthly -MonthlyTime 08:00:00 -MonthlyDayNumber First -MonthlyDayOfWeek Monday -Description "Monthly Backup" -RetentionType ItemLevel -ObjectStorageSettings $settings |  Perform the following steps:   1. Run the [Get-VBOProxy](get-vboproxy.md) cmdlet. Specify the Hostname parameter value. Save the result to the $proxy variable. 2. Run the [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md) cmdlet. Specify the Id parameter value. Save the result to the $account variable. 3. Run the [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md) cmdlet. Specify the necessary parameters. Save the result to the $connection variable. 4. Run the [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md) cmdlet. Set the $connection variable as the AmazonS3CompatibleConnectionSettings parameter value. Specify the Name parameter value. Save the result to the $bucket variable. 5. Run the [Get-VBOAmazonS3Folder](get-vboamazons3folder.md) cmdlet. Set the $bucket variable as the Bucket parameter value. Specify the Name parameter value. Save the result to the $folder variable. 6. Run the [New-VBOAmazonS3CompatibleObjectStorageSettings](new-vboamazons3compatibleobjectstoragesettings.md) cmdlet. Set the $folder variable as the Folder parameter value. Save the result to the $settings variable. 7. Run the Add-VBOAmazonS3CompatibleRepository cmdlet. Specify the following settings:  * Set the $proxy variable as the Proxy parameter value. * Specify the Name parameter value. * Set Days as the CustomRetentionPeriodType parameter value. * Set 7 as the CustomRetentionPeriod parameter value. * Set Monthly as the RetentionFrequencyType parameter value. * Set 08:00:00 as the MonthlyTime parameter value. * Set First as the MonthlyDayNumber parameter value. * Set Monday as the MonthlyDayOfWeek parameter value.  * Specify the Description parameter value.  * Set ItemLevel as the RetentionType parameter value.  * Set the $settings variable as the ObjectStorageSettings parameter value. |

Related Commands

* [Get-VBOProxy](get-vboproxy.md)
* [Get-VBOProxyPool](get-vboproxypool.md)
* [Get-VBOEncryptionKey](get-vboencryptionkey.md)
* [Get-VBOAmazonS3CompatibleAccount](get-vboamazons3compatibleaccount.md)
* [New-VBOAmazonS3CompatibleConnectionSettings](new-vboamazons3compatibleconnectionsettings.md)
* [Get-VBOAmazonS3Bucket](get-vboamazons3bucket.md)
* [Get-VBOAmazonS3Folder](get-vboamazons3folder.md)
* [New-VBOAmazonS3CompatibleObjectStorageSettings](new-vboamazons3compatibleobjectstoragesettings.md)

Page updated 10/2/2025

Page content applies to build 8.3.0.2201
