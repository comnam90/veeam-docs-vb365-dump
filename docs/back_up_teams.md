---
title: "back_up_teams"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/back_up_teams.html"
last_updated: "10/7/2025"
product_version: "8.3.0.2201"
---


In this article

|  |
| --- |
| Tip |
| Consider the following:   * To switch between objects of different types, you can click the buttons in the upper-right corner.  * To refresh the objects list, you can click Refresh.  * To quickly find necessary objects, you can use the search field at the bottom. |

To configure Teams backup, do the following:

1. In the Add Objects window, select check boxes next to the teams that you want to back up.

[![Adding Objects](images/add_teams_bj.webp)](images/add_teams_bj.webp "Adding Objects")

1. Click Add.

The selected objects appear in the list of objects to back up.

1. If you want to specify processing options, select the necessary Team type object and click Edit.

|  |
| --- |
| Note |
| You can edit processing options for the Team type objects only if you have selected the Teams chats check box when you added a Microsoft 365 organization to Veeam Backup for Microsoft 365. |

[![Selecting Objects to Back Up](images/teams_backup_edit.webp)](images/teams_backup_edit.webp "Selecting Objects to Back Up")

1. In the Edit Processing Options window, select check boxes next to the processing options that you want to apply, and click OK.

For more information about the Team type and its processing options, see [Organization Object Types](vbo_object_types.md#teams).

Keep in mind that the Chats check box is available for editing only if you have selected the Teams chats check box when you added a Microsoft 365 organization to Veeam Backup for Microsoft 365.

[![Editing Processing Options](images/teams_processing_options.webp)](images/teams_processing_options.webp "Editing Processing Options")

Page updated 10/7/2025

Page content applies to build 8.3.0.2201
