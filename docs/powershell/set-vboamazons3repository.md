---
title: "set-vboamazons3repository"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboamazons3repository.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies settings of Amazon S3 object storage repository (Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes).

Syntax

This cmdlet provides parameter sets that allow you to:

* Modify Amazon S3 object storage repository with retention period measured in years.

|  |
| --- |
| Set-VBOAmazonS3Repository [-UseArchiverAppliance] [-ArchiverAppliance <VBOAmazonArchiverAppliance>] [-IgnoreProxyPoolApplianceAccessValidation] [-EnableSizeLimit] [-SizeLimit <UInt64>] [-EnableDefragmentation] [-ImmutabilityPeriodDays <Int32>] -Repository <VBORepository> [-Name <String>] [-Description <String>] [-RetentionPeriod <VBORetentionPeriod>] [-RetentionFrequencyType <VBORetentionFrequencyType>] [-DailyTime <TimeSpan>] [-DailyType <VBODailyType>] [-MonthlyTime <TimeSpan>] [-MonthlyDayNumber <VBOMonthlyDayNumber>] [-MonthlyDayOfWeek <DayOfWeek>] [<CommonParameters>] |

* Modify Amazon S3 object storage repository with retention period measured in months or days.

|  |
| --- |
| Set-VBOAmazonS3Repository [-UseArchiverAppliance] [-ArchiverAppliance <VBOAmazonArchiverAppliance>] [-IgnoreProxyPoolApplianceAccessValidation] [-EnableSizeLimit] [-SizeLimit <UInt64>] [-EnableDefragmentation] [-ImmutabilityPeriodDays <Int32>] -Repository <VBORepository> [-Name <String>] [-Description <String>] [-CustomRetentionPeriodType <VBORetentionPeriodType>] [-CustomRetentionPeriod <Int32>] [-RetentionFrequencyType <VBORetentionFrequencyType>] [-DailyTime <TimeSpan>] [-DailyType <VBODailyType>] [-MonthlyTime <TimeSpan>] [-MonthlyDayNumber <VBOMonthlyDayNumber>] [-MonthlyDayOfWeek <DayOfWeek>] [<CommonParameters>] |

Detailed Description

This cmdlet modifies settings of Amazon S3 object storage repository (Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes) added to the Veeam Backup for Microsoft 365 infrastructure. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| UseArchiverAppliance | Defines that the cmdlet will enable usage of the Amazon archiver appliance when transferring backed-up data to the object storage repository during backup copy jobs.  Default: False | SwitchParameter | False | Named | False |
| ArchiverAppliance | Specifies the Amazon archiver appliance. The cmdlet will replace the current Amazon archiver appliance with the specified one.  The cmdlet will use this archiver appliance when transferring backed-up data between different instances of the general purpose object storage repositories (Amazon S3 Standard, Amazon S3 Standard-Infrequent Access and Amazon S3 One Zone-Infrequent Access storage classes) or to any of Amazon S3 Glacier object storage repositories (Amazon S3 Glacier Instant Retrieval, Amazon S3 Glacier Flexible Retrieval and Amazon S3 Glacier Deep Archive storage classes) during backup copy jobs. | Accepts the VBOAmazonArchiverAppliance object.  To create this object, run the [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md) cmdlet. | False | Named | False |
| IgnoreProxyPoolApplianceAccessValidation | Defines that the cmdlet will ignore check whether backup proxy servers that belong to the associated backup proxy pool can access the archiver appliance.  Default: False | SwitchParameter | False | Named | False |
| EnableSizeLimit | Defines that the cmdlet will enable a soft limit in GB for the object storage repository consumption that can be exceeded temporarily.  Use the SizeLimit parameter to specify the soft limit value.  Default: False | SwitchParameter | False | Named | False |
| SizeLimit | For the EnableSizeLimit option.  Specifies a soft limit in GB for the object storage repository consumption that can be exceeded temporarily. If the specified limit is exceeded, Veeam Backup for Microsoft 365 will not run a new job.  Permitted values: 1024–1073741824.  Default: 1024  Note: In PowerShell you can specify a soft limit in GB only. | UInt64 | False | Named | False |
| EnableDefragmentation | Defines that the cmdlet will enable defragmentation for the specified Amazon S3 object storage repository. After applying the retention policy, Veeam Backup for Microsoft 365 will start merging small blobs of data into a bigger one.  Default: False | SwitchParameter | False | Named | False |
| ImmutabilityPeriodDays | Specifies the number of days when your data will be blocked for deletion or modification.  Note: If you set the null or 0 value, data will be blocked for deletion or modification for the same period as the retention period. | Int32 | False | Named | False |
| Repository | Specifies Amazon S3 object storage repository. The cmdlet will modify settings of this object storage repository. | Accepts the VBORepository object.  To get this object, run the [Get-VBORepository](get-vborepository.md) cmdlet. | True | Named | True (ByValue) |
| Name | Specifies a name of Amazon S3 object storage repository. The cmdlet will change the name of this object storage repository. | String | False | Named | False |
| Description | Specifies a description of Amazon S3 object storage repository. The cmdlet will replace the current description with the specified description. | String | False | Named | False |
| RetentionPeriod | Specifies the retention period in years. Veeam Backup for Microsoft 365 will remove items from the object storage repository once this period is passed. You can set either of the following periods:   * Year1 * Years2 * Years3 * Years5 * Years7 * Years10 * Years25 * KeepForever   Default: Years3  Note: Apply the CustomRetentionPeriodType parameter to set the retention period in months or days. | VBORetentionPeriod | False | Named | False |
| RetentionFrequencyType | Specifies retention policy schedule. Veeam Backup for Microsoft 365 will check the object storage repository and will remove the outdated backups according to this schedule. You can set either of the following types of schedule:   * Daily: to check and remove the outdated backups once a day. * Monthly: to check and remove the outdated backups once a month.   Default: Daily | VBORetentionFrequencyType | False | Named | False |
| DailyTime | For daily retention policy schedule.  Specifies the time of the day when Veeam Backup for Microsoft 365 must apply the retention policy.  Default: 00:00:00 | TimeSpan | False | Named | False |
| DailyType | For daily retention policy schedule.  Specifies the days when Veeam Backup for Microsoft 365 must apply the retention policy:   * Sunday * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday * Everyday * Workdays * Weekends   Default: Everyday | VBODailyType | False | Named | False |
| MonthlyTime | For monthly retention policy schedule.  Specifies the time of the day when Veeam Backup for Microsoft 365 must apply the retention policy.  Default: 18:00:00 | TimeSpan | False | Named | False |
| MonthlyDayNumber | For monthly retention policy schedule.  Specifies the order number for the day of the week when Veeam Backup for Microsoft 365 must apply the retention policy.   * First * Second * Third * Fourth * Last   Default: First | VBOMonthlyDayNumber | False | Named | False |
| MonthlyDayOfWeek | For monthly retention policy schedule.  Specifies the day of the week when Veeam Backup for Microsoft 365 must apply the retention policy.   * Sunday * Monday * Tuesday * Wednesday * Thursday * Friday * Saturday   Default: Monday | DayOfWeek | False | Named | False |
| CustomRetentionPeriodType | Specifies a type of custom retention period. Veeam Backup for Microsoft 365 will remove items from the object storage repository once this period is passed. You can set the custom retention period to either of the following types:   * Months * Days   Set the CustomRetentionPeriod parameter to specify the number of days or the number of months. | VBORetentionPeriodType | False | Named | False |
| CustomRetentionPeriod | For the CustomRetentionPeriodType option.  Specifies the retention period to keep data on the object storage repository. The retention period is defined according to the CustomRetentionPeriod settings:   * Sets the retention period to the number of months if the CustomRetentionPeriodType parameter is set to Months. * Sets the retention period to the number of days if the CustomRetentionPeriodType parameter is set to Days.   Veeam Backup for Microsoft 365 will remove items from the object storage repository once this period is passed. | Int32 | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Output Object

The cmdlet returns the VBOAmazonS3Repository object that contains settings of Amazon S3 object storage repository.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Retention Policy Settings

|  |  |
| --- | --- |
| This example shows how to modify retention policy settings for Amazon S3 object storage repository. The repository will have the following settings:   * The retention period is set to 5 years. * Veeam Backup for Microsoft 365 will check the object storage repository and remove the outdated backups on weekends at 11:59 PM.   |  | | --- | | $repository = Get-VBORepository -Name "Amazon S3 Backup"  Set-VBOAmazonS3Repository -Repository $repository -RetentionPeriod Years5 -RetentionFrequencyType Daily -DailyType Weekends -DailyTime 23:59:00 |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Save the result to the $repository variable. 2. Run the Set-VBOAmazonS3Repository cmdlet. Specify the following settings:  * Set the $repository variable as the Repository parameter value. * Set Years5 as the RetentionPeriod parameter value. * Set Daily as the RetentionFrequencyType parameter value. * Set Weekends as the DailyType parameter value. * Set 23:59:00 as the DailyTime parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Modifying Amazon S3 Object Storage Name and Retention Policy

|  |  |
| --- | --- |
| This example shows how to change the name of the Amazon S3 Backup object storage repository and configure the clean-up schedule with the following settings:   * The retention period for organization backups is set to 6 months. * Veeam Backup for Microsoft 365 will check the object storage repository and remove the outdated backups every second Monday at 7:59 AM.   |  | | --- | | $repository = Get-VBORepository -Name "Amazon S3 Backup"  Set-VBOAmazonS3Repository -Repository $repository -Name "Monthly Reports" -CustomRetentionPeriodType Months -CustomRetentionPeriod 6 -RetentionFrequencyType Monthly -MonthlyDayNumber Second -MonthlyDayOfWeek Monday -MonthlyTime 07:59:00 |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 2. Run the Set-VBOAmazonS3Repository cmdlet. Specify the following settings:  * Set the $repository variable as the Repository parameter value. * Specify the Name parameter value. * Set Months as the CustomRetentionPeriodType parameter value. * Set 6 as the CustomRetentionPeriod parameter value. * Set Monthly as the RetentionFrequencyType parameter value. * Set Second as the MonthlyDayNumber parameter value. * Set Monday as the MonthlyDayOfWeek parameter value. * Set 07:59:00 as the MonthlyTime parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Modifying Amazon S3 Object Storage Soft Limit

|  |  |
| --- | --- |
| This example shows how to modify a soft limit for the Amazon S3 Backup object storage repository.  |  | | --- | | $repository = Get-VBORepository -Name "Amazon S3 Backup"  Set-VBOAmazonS3Repository -Repository $repository -EnableSizeLimit -SizeLimit 2048 |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 2. Run the Set-VBOAmazonS3Repository cmdlet. Specify the following settings:  * Set the $repository variable as the Repository parameter value. * Provide the EnableSizeLimit parameter. * Specify the SizeLimit parameter value. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Disabling Amazon S3 Object Storage Soft Limit

|  |  |
| --- | --- |
| This example shows how to disable the soft limit for the Amazon S3 Backup object storage repository.  |  | | --- | | $repository = Get-VBORepository -Name "Amazon S3 Backup"  Set-VBOAmazonS3Repository -Repository $repository -EnableSizeLimit:$false |  Perform the following steps:   1. Run the [Get-VBORepository](get-vborepository.md) cmdlet. Specify the Name parameter value. Save the result to the $repository variable. 2. Run the Set-VBOAmazonS3Repository cmdlet. Specify the following settings:  * Set the $repository variable as the Repository parameter value. * Set the false value for the EnableSizeLimit parameter. |

Related Commands

* [Get-VBORepository](get-vborepository.md)
* [New-VBOAmazonArchiverAppliance](new-vboamazonarchiverappliance.md)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
