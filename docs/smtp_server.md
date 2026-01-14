---
title: "smtp_server"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/smtp_server.html"
last_updated: "7/18/2024"
product_version: "8.3.0.2201"
---


In this article

To configure sending email notifications using a custom SMTP server with basic authentication, do the following:

1. In the main menu, click General Options.
2. Open the Notifications tab.
3. Select the Enable email notifications check box.
4. From the Mail server drop-down list, select SMTP server (basic authentication).
5. Click Advanced to configure advanced settings. You can do the following:

* Specify a port number of an SMTP server that you want to use.

By default, Veeam Backup for Microsoft 365 uses the port number 587. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365).

* Select the Connect using SSL check box to establish a secure connection.
* If an SMTP server requires an authentication for outgoing mail, select the The SMTP server requires authentication check box and provide authentication credentials.

1. In the SMTP server field, specify the address of a server that you want to use as an SMTP server.

By default, Veeam Backup for Microsoft 365 establishes a connection to the smtp.office365.com server through the port 587. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365).

1. In the From field, specify the email address to be shown as a sender.
2. In the To field, specify the email address of the notification recipient.

To specify multiple email addresses, use semicolon.

1. In the Subject field, edit a notification subject if needed.

By default, a notification subject is "[%JobResult%] %OrgName% - %JobName% (%ObjectCount% objects), %Issues% issues",

where:

* %JobResult%. A job result (Success, Warning, Failed).
* %OrgName%. A Microsoft 365 organization for which the job was configured.
* %JobName%. A job name.
* %ObjectCount%. Total number of processed objects.
* %Issues%. Number of objects with Failed or Warning statuses.
* %Time%. Date and time of a job completion.

1. Select the Include detailed report as an attachment check box if you want to include a detailed report as an email attachment.

If you select this option, Veeam Backup for Microsoft 365 will provide a summary about the job results in the notification body and a detailed report for each object processed by the job in the email attachment. Keep in mind that for jobs that process up to 1000 objects, Veeam Backup for Microsoft 365 always provides both a summary and a detailed report in the notification body.

1. By default, system notifications are sent every time a job session is completed with any of the following statuses: Success, Warning and Failure. To turn off unwanted notifications, clear check boxes next to the events for which you do not want to receive notifications:

* Notify on success

Veeam Backup for Microsoft 365 will send email notifications if a backup or backup copy job completes successfully without any warnings or errors.

* Notify on warning

Veeam Backup for Microsoft 365 will send email notifications if a backup or backup copy job completes with warnings.

* Notify on failure

Veeam Backup for Microsoft 365 will send email notifications if a backup or backup copy completes with errors.

1. If a backup or backup copy job is configured to perform retry attempts, select the Suppress notifications until the last retry check box to send email notifications according to the job schedule settings. The following email notification scenarios are possible:

* If the job fails, Veeam Backup for Microsoft 365 will send a notification message on the last job retry.
* If the job completes with Success or Warning, Veeam Backup for Microsoft 365 will send a notification message on the last completion status.
* If the job is scheduled to Terminate job if it exceeds allowed backup window, Veeam Backup for Microsoft 365 will send a notification message on the last attempt within the configured interval.

1. Click Test Message to send a test message.
2. Click OK.

[![Configuring Notification Settings](images/options_email_notifications.webp)](images/options_email_notifications.webp "Configuring Notification Settings")

Page updated 7/18/2024

Page content applies to build 8.3.0.2201
