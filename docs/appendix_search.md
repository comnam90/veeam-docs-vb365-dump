---
title: "appendix_search"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/appendix_search.html"
last_updated: "5/6/2025"
product_version: "8.3.0.2201"
---


In this article

You can search for items in backups created by Veeam Backup for Microsoft 365 using the following instruments:

* Restore Portal user interface

For more information on how to explore and restore data from backups using Restore Portal, see [Performing Restore](ssp_performing_restore.md).

* Veeam Backup for Microsoft 365 REST API

For more information about item search functionality in the Veeam Backup for Microsoft 365 REST API, see the [Search for Backed-Up Items](https://helpcenter.veeam.com/references/vbo365/8/rest/tag/SectionOverview#section/Search-for-Backed-Up-Items) section of the REST API Reference.

* Veeam Explorers user interface

For more information about item search functionality in Veeam Explorers, see the Searching for Objects in Backup File sections of the [Veeam Explorers User Guide](https://helpcenter.veeam.com/docs/vbo365/explorers/explorers_introduction.html?ver=80) for each Veeam Explorer.

* Veeam Explorers PowerShell

For more information about item search functionality in Veeam Explorers PowerShell, see [Veeam Explorers PowerShell Reference](https://helpcenter.veeam.com/docs/vbo365/explorers_powershell/getting_started.html?ver=80).

When you search for items in backups created by Veeam Backup for Microsoft 365, you can use query parameters to narrow the search criteria. In a query, you can specify search parameters in the form of canonical names (for example: System.Message.FromAddress and System.Message.ToAddress) or their shortcuts (where applicable; for example: from and to).

You can specify search parameters in search requests for the following types of items:

* [Microsoft Exchange Items](#exchange)
* [Microsoft SharePoint and Microsoft OneDrive for Business Items](#sp_od)
* [Microsoft Teams Items](#teams)

For examples of how to provide values for search parameters and combine parameters when searching for Microsoft Exchange items, see [this Microsoft article](https://support.microsoft.com/en-us/office/learn-to-narrow-your-search-criteria-for-better-searches-in-outlook-d824d1e9-a255-4c8a-8553-276fb895a8da).

|  |
| --- |
| Note |
| If a value for a query parameter contains a space, provide the value in the quotation marks (""). Use the backslash (\) symbol as an escape character before these quotation marks. For example, in REST API: "query": "from: \"user X\" to: \"user Y\"". |

Search Parameters for Microsoft Exchange Items

The following table contains parameters that can be used to search for Microsoft Exchange items in backups created by Veeam Backup for Microsoft 365.

| Name | Canonical Name | Shortcut |
| --- | --- | --- |
| Body | System.Search.Contents | body, content, contents |
| Categories | System.Category | category |
| Company | System.Company | company |
| Date Completed | System.DateCompleted | completed |
| Date Created | System.DateCreated | datecreated |
| Date Modified | System.DateModified | datemodified |
| Due Date | System.DueDate | due, duedate |
| End Date | System.EndDate | enddate |
| Flag Color | System.FlagColor | - |
| Flag Status | System.FlagStatus | flagstatus |
| Importance | System.Importance | importance |
| Flag | System.IsFlagged | isflagged, hashflag |
| Is Completed | System.IsFlaggedComplete | iscompleted |
| Incomplete | System.IsIncomplete | incomplete |
| Read | System.IsRead | read, isread |
| Priority | System.Priority | priority |
| Sensitivity | System.Sensitivity | sensitivity |
| Size | System.Size | size |
| Start Date | System.StartDate | start |
| Subject | System.Subject | subject |
| Title | System.Title | title |
| Duration | System.Calendar.Duration | duration |
| Recurring | System.Calendar.IsRecurring | isrecurring, recurring |
| Location | System.Calendar.Location | location |
| Optional Attendee Addresses | System.Calendar.OptionalAttendeeAddresses | optionalattendees |
| Optional Attendees | System.Calendar.OptionalAttendeeNames | optionalattendees |
| Organizer Address | System.Calendar.OrganizerAddress | organizer |
| Organizer | System.Calendar.OrganizerName | organizer, by, from |
| Reminder Time | System.Calendar.ReminderTime | remindertime |
| Required Attendee Addresses | System.Calendar.RequiredAttendeeAddresses | requiredattendees |
| Required Attendees | System.Calendar.RequiredAttendeeNames | requiredattendees |
| Response Status | System.Calendar.ResponseStatus | meetingstatus |
| Show Time As | System.Calendar.ShowTimeAs | showtimeas |
| Assistant Name | System.Contact.AssistantName | assistantname |
| Assistant's Phone | System.Contact.AssistantTelephone | assistantphone |
| Birthday | System.Contact.Birthday | birthday |
| Business Address | System.Contact.BusinessAddress | businessaddress |
| Business Address City | System.Contact.BusinessAddressCity | businesscity |
| Business Address Country | System.Contact.BusinessAddressCountry | - |
| Business Address Postal Code | System.Contact.BusinessAddressPostalCode | businesspostalcode |
| Business Address Post Office Box | System.Contact.BusinessAddressPostOfficeBox | - |
| Business Address State | System.Contact.BusinessAddressState | - |
| Business Address Street | System.Contact.BusinessAddressStreet | street, businessstreet |
| Business Fax | System.Contact.BusinessFaxNumber | businessfax |
| Business Home Page | System.Contact.BusinessHomePage | businesshomepage |
| Business Phone | System.Contact.BusinessTelephone | businessphone |
| Callback Phone Number | System.Contact.CallbackTelephone | callbacknumber |
| Car Phone | System.Contact.CarTelephone | carphone |
| Children | System.Contact.Children | children |
| Company Main Telephone | System.Contact.CompanyMainTelephone | - |
| Department | System.Contact.Department | department |
| Email | System.Contact.EmailAddress | emailaddress |
| Email | System.Contact.EmailAddress2 | - |
| Email | System.Contact.EmailAddress3 | - |
| File As Name | System.Contact.FileAsName | - |
| First Name | System.Contact.FirstName | firstname |
| Full Name | System.Contact.FullName | fullname |
| Gender | System.Contact.Gender | - |
| Hobbies | System.Contact.Hobbies | - |
| Home Address | System.Contact.HomeAddress | homeaddress |
| Home Address City | System.Contact.HomeAddressCity | homecity |
| Home Address Country | System.Contact.HomeAddressCountry | - |
| Home Address Postal Code | System.Contact.HomeAddressPostalCode | homepostalcode |
| Home Address Post Office Box | System.Contact.HomeAddressPostOfficeBox | - |
| Home Address State | System.Contact.HomeAddressState | - |
| Home Address Street | System.Contact.HomeAddressStreet | homestreet |
| Home Fax | System.Contact.HomeFaxNumber | homefax |
| Home Phone | System.Contact.HomeTelephone | homephone |
| IM Address | System.Contact.IMAddress | imaddress |
| Initials | System.Contact.Initials | - |
| Job Title | System.Contact.JobTitle | jobtitle |
| Last Name | System.Contact.LastName | lastname |
| Mailing Address | System.Contact.MailingAddress | mailingaddress |
| Middle Name | System.Contact.MiddleName | - |
| Mobile Phone | System.Contact.MobileTelephone | mobilephone |
| Nickname | System.Contact.NickName | nickname |
| Office Location | System.Contact.OfficeLocation | officelocation |
| Other Address | System.Contact.OtherAddress | otheraddress |
| Other Address City | System.Contact.OtherAddressCity | othercity |
| Other Address Country | System.Contact.OtherAddressCountry | - |
| Other Address Postal Code | System.Contact.OtherAddressPostalCode | otherpostalcode |
| Other Address Post Office Box | System.Contact.OtherAddressPostOfficeBox | - |
| Other Address State | System.Contact.OtherAddressState | - |
| Other Address Street | System.Contact.OtherAddressStreet | otherstreet |
| Pager | System.Contact.PagerTelephone | pager |
| Title | System.Contact.PersonalTitle | title |
| Profession | System.Contact.Profession | profession |
| Spouse | System.Contact.SpouseName | spouse |
| Suffix | System.Contact.Suffix | - |
| Telex | System.Contact.TelexNumber | - |
| TTYTDD Number | System.Contact.TTYTDDTelephone | - |
| Webpage | System.Contact.WebPage | webpage |
| Attachment Contains | System.Message.AttachmentNames | attachments |
| Attachments | System.Message.HasAttachments | hasattachments |
| Bcc Address | System.Message.BccAddress | bcc, bccaddress |
| Bcc Name | System.Message.BccName | bcc, bccname |
| Cc Address | System.Message.CcAddress | cc, ccaddress |
| Cc Name | System.Message.CcName | cc, ccname |
| Conversation ID | System.Message.ConversationID | - |
| Received | System.Message.DateReceived | received |
| Sent | System.Message.DateSent | sent |
| From | System.Message.FromAddress | from |
| From | System.Message.FromName | from |
| Message Class | System.Message.MessageClass | - |
| Sender Address | System.Message.SenderAddress | from |
| Sender Name | System.Message.SenderName | from |
| To Address | System.Message.ToAddress | to, toaddress |
| To | System.Message.ToName | to |
| Color | System.Note.Color | color |
| Owner | System.Task.Owner | taskowner |
| Header | Veeam.Message.Header | - |

Search Parameters for Microsoft SharePoint and Microsoft OneDrive for Business Items

The following table contains parameters that can be used to search for Microsoft SharePoint and Microsoft OneDrive for Business items in backups created by Veeam Backup for Microsoft 365.

| Name | Canonical Name | Shortcut |
| --- | --- | --- |
| Created By | System.Author | - |
| Location | System.Calendar.Location | location |
| Category | System.Category | category |
| Comment | System.Comment | - |
| Expires | System.Communication.DateItemExpires | - |
| Task Status | System.Communication.TaskStatus | - |
| Company | System.Company | company |
| Anniversary | System.Contact.Anniversary | - |
| Assistants Name | System.Contact.AssistantName | assistantname |
| Assistant Number | System.Contact.AssistantTelephone | assistantphone |
| Birthday | System.Contact.Birthday | birthday |
| Work Address | System.Contact.BusinessAddress | businessaddress |
| Work City | System.Contact.BusinessAddressCity | businesscity |
| Work Country | System.Contact.BusinessAddressCountry | - |
| Work Zip | System.Contact.BusinessAddressPostalCode | businesspostalcode |
| Work State | System.Contact.BusinessAddressState | - |
| Work Fax | System.Contact.BusinessFaxNumber | businessfax |
| Business Telephone | System.Contact.BusinessTelephone | businessphone |
| Callback Number | System.Contact.CallbackTelephone | callbacknumber |
| Car Number | System.Contact.CarTelephone | carphone |
| Company Number | System.Contact.CompanyMainTelephone | - |
| Department | System.Contact.Department | department |
| Email Address | System.Contact.EmailAddress | emailaddress |
| Email Sender | System.Contact.EmailName | - |
| First Name | System.Contact.FirstName | firstname |
| Full Name | System.Contact.FullName | fullname |
| Gender | System.Contact.Gender | - |
| Hobbies | System.Contact.Hobbies | - |
| Home Address City | System.Contact.HomeAddressCity | homecity |
| Home Address Country | System.Contact.HomeAddressCountry | - |
| Home Address Postal Code | System.Contact.HomeAddressPostalCode | homepostalcode |
| Home Address State Or Province | System.Contact.HomeAddressState | - |
| Home Address Street | System.Contact.HomeAddressStreet | homestreet |
| Home Fax Number | System.Contact.HomeFaxNumber | homefax |
| Home Telephone | System.Contact.HomeTelephone | homephone |
| IM Address | System.Contact.IMAddress | imaddress |
| Initials | System.Contact.Initials | - |
| Company Phonetic | System.Contact.JA.CompanyNamePhonetic | - |
| First name pronounciation | System.Contact.JA.FirstNamePhonetic | - |
| Last Name Phonetic | System.Contact.JA.LastNamePhonetic | - |
| Middle Name | System.Contact.MiddleName | - |
| Mobile Telephone | System.Contact.MobileTelephone | mobilephone |
| Nick Name | System.Contact.NickName | nickname |
| Office Location | System.Contact.OfficeLocation | officelocation |
| Other Address City | System.Contact.OtherAddressCity | othercity |
| Other Address Country | System.Contact.OtherAddressCountry | - |
| Other Address Postal Code | System.Contact.OtherAddressPostalCode | otherpostalcode |
| Other Address State | System.Contact.OtherAddressState | - |
| Other Address Street | System.Contact.OtherAddressStreet | otherstreet |
| Pager Number | System.Contact.PagerTelephone | pager |
| Primary Number | System.Contact.PrimaryTelephone | - |
| Profession | System.Contact.Profession | profession |
| Spouse Name | System.Contact.SpouseName | spouse |
| Suffix | System.Contact.Suffix | - |
| Telex Number | System.Contact.TelexNumber | - |
| TTYTDD Number | System.Contact.TTYTDDTelephone | - |
| Copyright | System.Copyright | - |
| Date Completed | System.DateCompleted | completed |
| Date Created | System.DateCreated | datecreated |
| Date Modified | System.DateModified | datemodified |
| Computer Network Name | System.Devices.NetworkName | - |
| Contributor | System.Document.Contributor | - |
| Last Author | System.Document.LastAuthor | - |
| Revision | System.Document.RevisionNumber | - |
| Version | System.Document.Version | - |
| Due Date | System.DueDate | due, duedate |
| End Date | System.EndDate | enddate |
| Folder Child Count | System.FileCount | - |
| Description | System.FileDescription | - |
| File Extension | System.FileExtension | - |
| File Name | System.FileName | filename |
| User Name | System.Identity.UserName | - |
| Image Width | System.Image.HorizontalSize | - |
| Image Height | System.Image.VerticalSize | - |
| Deleted | System.IsDeleted | - |
| Mark As Read | System.IsRead | read, isread |
| Folder Path | System.ItemFolderPathDisplay | - |
| Item Path | System.ItemPathDisplay | - |
| Object Type | System.ItemTypeText | - |
| Item URL | System.ItemUrl | - |
| Language | System.Language | - |
| Link URL | System.Link.TargetUrl | - |
| Length (seconds) | System.Media.Duration | - |
| Publisher | System.Media.Publisher | - |
| Personal Website | System.Media.UserWebUrl | - |
| Email Cc | System.Message.CcAddress | cc, ccaddress |
| Email From | System.Message.FromAddress | from |
| Has Attachments | System.Message.HasAttachments | hasattachments |
| Email To | System.Message.ToName | to |
| Mileage | System.MileageInformation | - |
| Body | System.Search.Contents | body, content, contents |
| File Size | System.Size | size |
| Source | System.SourceItem | - |
| Start Date | System.StartDate | start |
| Status | System.Status | - |
| Subject | System.Subject | subject |
| Billing Information | System.Task.BillingInformation | - |
| Title | System.Title | title |

Search Parameters for Microsoft Teams Items

Search Parameters for Posts

The following table contains parameters that can be used to search for Microsoft Teams posts in backups created by Veeam Backup for Microsoft 365.

| Name | Canonical Name | Shortcut |
| --- | --- | --- |
| Attachment Name | System.Message.AttachmentNames | - |
| Attachment URL | System.Message.AttachmentContents | attachment |
| Author | System.Author | author |
| Created | System.DateCreated | datecreated, created |
| Date Modified | System.DateModified | datemodified, modified |
| Has Attachments | System.Message.HasAttachments | hasattachment |
| Important | System.Importance | - |
| Message | System.Search.Contents | body, contents, content |
| Subject | System.Subject | subject |

Search Parameters for Files

The following table contains parameters that can be used to search for Microsoft Teams files in backups created by Veeam Backup for Microsoft 365.

| Name | Canonical Name | Shortcut |
| --- | --- | --- |
| Created By | System.Author | author |
| Created | System.DateCreated | datecreated, created |
| Modified | System.DateModified | datemodified, modified |
| Modified By | System.Document.LastAuthor | - |
| Version | System.Document.Version | - |
| File Extension | System.FileExtension | ext |
| Name | System.FileName | filename |
| Size | System.Size | size |

Search Parameters for Tabs

The following table contains parameters that can be used to search for Microsoft Teams tabs in backups created by Veeam Backup for Microsoft 365.

| Name | Canonical Name | Shortcut |
| --- | --- | --- |
| Name | System.ItemNameDisplay | name |

Page updated 5/6/2025

Page content applies to build 8.3.0.2201
