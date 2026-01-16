---
title: "set-vboemailsettings"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/set-vboemailsettings.html"
last_updated: "9/30/2025"
product_version: "8.3.0.2201"
---


In this article

Short Description

Modifies email notification settings. Email notifications are sent from a backup proxy server upon each execution of a backup or backup copy job.

Syntax

This cmdlet provides parameter sets that allow you to:

* Modify email notification settings to use a custom SMTP server with basic authentication.

|  |
| --- |
| Set-VBOEmailSettings [-EnableNotification] [-SMTPServer <String>] [-Port <Int32>] [-UseAuthentication] [-UseSSL] [-Credential <PSCredential>] [-From <String>] [-To <String>] [-Subject <String>] [-NotifyOnSuccess] [-NotifyOnWarning] [-NotifyOnFailure] [-SupressUntilLastRetry] [-AttachDetailedReport] [<CommonParameters>] |

* Modify email notification settings to use a Google account for authentication.

|  |
| --- |
| Set-VBOEmailSettings [-EnableNotification] [-GoogleGmail] [-ClientId <String>] [-ClientSecret <SecureString>] [-To <String>] [-Subject <String>] [-NotifyOnSuccess] [-NotifyOnWarning] [-NotifyOnFailure] [-SupressUntilLastRetry] [-AttachDetailedReport] [<CommonParameters>] |

* Modify email notification settings to use a Microsoft 365 account for authentication.

|  |
| --- |
| Set-VBOEmailSettings [-EnableNotification] [-ClientId <String>] [-Microsoft365] [-MailApiUrl <String>] [-TenantId <String>] [-To <String>] [-Subject <String>] [-NotifyOnSuccess] [-NotifyOnWarning] [-NotifyOnFailure] [-SupressUntilLastRetry] [-AttachDetailedReport] [<CommonParameters>] |

Detailed Description

This cmdlet modifies email notification settings for Veeam Backup for Microsoft 365. To modify settings, you need to enter the necessary parameters with new values. The parameters that you omit will remain unchanged.

|  |
| --- |
| ![Set-VBOEmailSettings](images/icon_note.webp) Note |
| Email notification settings are global, they will be applied to all backup and backup copy jobs configured in Veeam Backup for Microsoft 365. |

Parameters

| Parameter | Description | Type | Required | Position | Accept Pipeline Input |
| --- | --- | --- | --- | --- | --- |
| EnableNotification | Defines that Veeam Backup for Microsoft 365 will send email notifications.  Default: False | SwitchParameter | False | Named | False |
| SMTPServer | Specifies the full DNS name or IP address of the SMTP server for sending email notifications.  Default: smtp.office365.com | String | False | Named | False |
| Port | Specifies a port number for connecting to SMTP server.  Default: 587 | Int32 | False | Named | False |
| UseAuthentication | Defines that the SMTP server requires authentication. Otherwise, the connection will be established to the SMTP server, which does not enforce authentication.  Default: False | SwitchParameter | False | Named | False |
| UseSSL | Defines that Veeam Backup for Microsoft 365 will enable a secure connection for email notification transmission. Otherwise, email notifications will be transmitted through the connection that does not require SSL authentication.  Default: False | SwitchParameter | False | Named | False |
| Credential | Specifies credentials that you want to use for authentication to the SMTP server. | PSCredential | False | Named | False |
| From | Specifies email address of the notification sender.  Note: Use this parameter only to send email notifications using SMTP server with basic authentication. | String | False | Named | False |
| To | Specifies email address of the notification recipient. Semicolon is used for listing multiple recipients. | String | False | Named | False |
| Subject | Specifies the subject for email notifications. You can use the following system variables:   * %JobName% - name of a backup or backup copy job. * %JobResult% - a job result. * %OrgName% - organization whose data was processed by a backup or backup copy job. * %MailboxCount% - total number of processed objects. * %Issues% - number of objects that were processed with the Failed or Warning status. * %Time% - date and time of a job completion. | String | False | Named | False |
| NotifyOnSuccess | Defines that Veeam Backup for Microsoft 365 will send email notifications if a backup or backup copy job completes successfully without any warnings or errors.  Default: False | SwitchParameter | False | Named | False |
| NotifyOnWarning | Defines that Veeam Backup for Microsoft 365 will send email notifications if a backup or backup copy job completes with warnings.  Default: False | SwitchParameter | False | Named | False |
| NotifyOnFailure | Defines that Veeam Backup for Microsoft 365 will send email notifications if a backup or backup copy completes with errors.  Default: False | SwitchParameter | False | Named | False |
| SupressUntilLastRetry | Defines that Veeam Backup for Microsoft 365 will send email notifications according to the job schedule settings. The following email notification scenarios are possible:   * If the job fails, Veeam Backup for Microsoft 365 will send a notification message on the last job retry. * If the job completes with Success or Warning, Veeam Backup for Microsoft 365 will send a notification message on the last completion status. * If the job is scheduled to Terminate job if it exceeds allowed backup window, Veeam Backup for Microsoft 365 will send a notification message on the last attempt within the configured interval.   Default: False  For more information on job schedule settings, see the [New-VBOJobSchedulePolicy](new-vbojobschedulepolicy.md) and [New-VBOCopyJobSchedulePolicy](new-vbocopyjobschedulepolicy.md) cmdlets. | SwitchParameter | False | Named | False |
| AttachDetailedReport | Defines that a detailed report about the job results will be included as an email attachment.  Default: False | SwitchParameter | False | Named | False |
| GoogleGmail | Defines that Veeam Backup for Microsoft 365 will send email notifications on behalf of a Google account.  Default: False | SwitchParameter | True | Named | False |
| ClientId | Specifies the client ID obtained while registering an application in the Google Cloud console or Microsoft Identity platform. | String | False | Named | False |
| ClientSecret | Specifies a password.  Note: This parameter is required only for authentication with a Google account using a custom application. | SecureString | False | Named | False |
| Microsoft365 | Defines that Veeam Backup for Microsoft 365 will send email notifications on behalf of a Microsoft 365 account.  Default: False | SwitchParameter | True | Named | False |
| MailApiUrl | Specifies the Microsoft Graph API URL of Microsoft Entra application registered in the Microsoft Identity platform.  Default: https://graph.microsoft.com/v1.0 | String | False | Named | False |
| TenantId | Specifies a tenant ID in Microsoft Entra ID. | String | False | Named | False |

<CommonParameters>

This cmdlet supports Microsoft PowerShell common parameters. For more information on common parameters, see the [About CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216) section of Microsoft Docs.

Examples

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 1: Modifying Email Notification Settings for SMTP Server with Basic Authentication

|  |  |
| --- | --- |
| This command configures email notifications with the following settings:   * Email notifications will be sent through the default SMTP server with basic authentication. * Email notifications will be sent to several recipients if the job completes with error. * The body of the subject in email notifications will contain system variables.   |  | | --- | | Set-VBOEmailSettings -EnableNotification -From vbo@tech.com -To "helpdesk@tech.com; support@tech.com" -Subject "[%JobResult%] %Time% %OrgName% - %JobName% (%MailboxCount% objects), %Issues% issues" -NotifyOnFailure |  Run the Set-VBOEmailSettings cmdlet and specify the following settings:   * Provide the EnableNotification parameter. * Specify values for the From, To and Subject parameters. * Provide the NotifyOnFailure parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 2: Modifying Email Notification Settings for Authentication with Microsoft 365 Account Using Veeam Application

|  |  |
| --- | --- |
| This command configures email notifications with the following settings:   * Email notifications will be sent on behalf of the Microsoft 365 account. * Authentication will be performed using an application preinstalled by Veeam. * Email notifications will be sent to several recipients if the job completes without any warnings or errors. * The body of the subject in email notifications will contain system variables.   |  | | --- | | Set-VBOEmailSettings -EnableNotification -To "helpdesk@tech.com; support@tech.com" -Subject "[%JobResult%] %Time% %OrgName% - %JobName% (%MailboxCount% objects), %Issues% issues" -NotifyOnSuccess -Microsoft365 |  Run the Set-VBOEmailSettings cmdlet and specify the following settings:   * Provide the EnableNotification parameter. * Specify values for the To and Subject parameters. * Provide the Microsoft365 parameter. * Provide the NotifyOnSuccess parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 3: Modifying Email Notification Settings for Authentication with Google Account Using Veeam Application

|  |  |
| --- | --- |
| This command configures email notifications with the following settings:   * Email notifications will be sent on behalf of the Google account. * Authentication to Google will be performed using an application preinstalled by Veeam. * Email notifications will be sent to several recipients if the job completes without any warnings or errors. * The body of the subject in email notifications will contain system variables.   |  | | --- | | Set-VBOEmailSettings -EnableNotification -To "helpdesk@tech.com; support@tech.com" -Subject "[%JobResult%] %Time% %OrgName% - %JobName% (%MailboxCount% objects), %Issues% issues" -NotifyOnSuccess -GoogleGmail |  Run the Set-VBOEmailSettings cmdlet and specify the following settings:   * Provide the EnableNotification parameter. * Specify values for the To and Subject parameters. * Provide the GoogleGmail parameter. * Provide the NotifyOnSuccess parameter. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 4: Modifying Email Notification Settings for Authentication with Microsoft 365 Account Using Custom Application

|  |  |
| --- | --- |
| This command configures email notifications with the following settings:   * Email notifications will be sent on behalf of the Microsoft 365 account. * Authentication will be performed using a custom application registered in Microsoft Identity platform. * Email notifications will be sent to several recipients if the job completes without any warnings or errors. * The body of the subject in email notifications will contain system variables.   |  | | --- | | Set-VBOEmailSettings -EnableNotification -To "helpdesk@tech.com; support@tech.com" -Subject "[%JobResult%] %Time% %OrgName% - %JobName% (%MailboxCount% objects), %Issues% issues" -NotifyOnSuccess -Microsoft365 -ClientId bd0xxxxx-2d90-0000-86f5-5488df12xxxx -TenantId xxxxde96-x000-4a97-8ae0-ba91c4aaxxxx |  Run the Set-VBOEmailSettings cmdlet and specify the following settings:   * Provide the EnableNotification parameter. * Specify values for the To and Subject parameters. * Provide the Microsoft365 parameter. * Provide the NotifyOnSuccess parameter. * Specify values for the ClientId and TenantId parameters. |

![](//img.veeam.com/helpcenter/baggage/arrow_next.svg)Example 5: Modifying Email Notification Settings for Authentication with Google Account Using Custom Application

|  |  |
| --- | --- |
| This example shows how to configure email notifications with the following settings:   * Email notifications will be sent on behalf of the Google account. * Authentication to Google will be performed using a custom application registered in the Google Cloud console. * Email notifications will be sent to several recipients if the job completes without any warnings or errors. * The body of the subject in email notifications will contain system variables.   |  | | --- | | $clientsecret = "XXXXXX-xxxxXXxxxXXXXXXXXXXXxxxxxxxx"  $securepassword = $clientsecret | ConvertTo-SecureString -AsPlainText -Force  Set-VBOEmailSettings -EnableNotification -To "helpdesk@tech.com; support@tech.com" -Subject "[%JobResult%] %Time% %OrgName% - %JobName% (%MailboxCount% objects), %Issues% issues" -NotifyOnSuccess -GoogleGmail -ClientId 012345678901-xxxxxxxxxxxxxxxxxxxxxxxxxxxxkdgp.apps.googleusercontent.com -ClientSecret $securepassword |  Perform the following steps:   1. Assign a client secret of your custom application to the $clientsecret variable. 2. Run the [ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5) cmdlet with the $clientsecret variable to turn the password into the SecureString type. Save the result to the $securepassword variable. 3. Run the Set-VBOEmailSettings cmdlet. Specify the following settings:  * Provide the EnableNotification parameter. * Specify values for the To and Subject parameters. * Provide the GoogleGmail parameter. * Specify the ClientId parameter value. * Set the $securepassword variable as the ClientSecret parameter value. * Provide the NotifyOnSuccess parameter. |

Related Commands

[ConvertTo-SecureString](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/convertto-securestring?view=powershell-7.5)

Page updated 9/30/2025

Page content applies to build 8.3.0.2201
