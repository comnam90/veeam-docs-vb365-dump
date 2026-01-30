---
title: "Exchange Restore"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/ssp_exchange_restore.html"
last_updated: "3/13/2025"
product_version: "8.3.0.2201"
---

# Exchange Restore


To restore Exchange items, do the following:

1. Open the Explore tab.
2. Select a restore point from which you want to explore and restore data. For more information, see [Selecting Restore Point](ssp_selecting_restore_point.md).
3. In the navigation pane, browse through the hierarchy of folders with backed-up data.
4. Select a folder that contains data you want to restore.
5. In the preview pane, select check boxes next to the necessary Exchange items.

|  |
| --- |
| Note |
| Consider the following:   * Restore Portal displays up to 2000 items, so search for specific items. * You can narrow your search results by specifying various search criteria using the criteria:value format. For more information about search parameters, see [Appendix A. Item Search Parameters](appendix_search.md). * You can also use logical upper-cased operators such as AND, OR and NOT along with wildcard characters such as \* and ?. * To search items by a specific date/time, specify the time in the UTC format. You can hover over the date in the Received column to view the UTC value. |

1. Click Restore.

[![Selecting Exchange Items to Restore](images/ssp_select_exchange_items_restore.webp)](images/ssp_select_exchange_items_restore.webp "Selecting Exchange Items to Restore")

The Exchange Restore wizard runs to configure the restore operation options.

1. At the Items step, specify items that you want to restore. If you no longer want to restore an item, select it and click Remove.

[![Exchange Restore](images/exchange_items.webp)](images/exchange_items.webp "Exchange Restore")

1. At the Restore mode step, select where you want to restore the selected items:

* Restore to the original location. Select this option if you want to restore the selected items to their original location.
* Restore to a new location. Select this option if you want to restore the selected items to another location and specify the folder name in the Restore to the following folder field. If the specified folder does not exist, it will be created automatically.

[![Exchange Restore](images/exchange_restore_mode.webp)](images/exchange_restore_mode.webp "Exchange Restore")

1. Click Advanced options to open the Restore options dialog.
2. In the Restore options dialog, select check boxes next to the additional options that you want to apply during the restore operation and then click Apply:

* Restore changed items. Select this check box if you want to restore items that have been changed.

* Restore missing items. Select this check box if you want to restore items that are missing in the target folder.

* Mark restored items as unread. Select this check box if you want to mark each restored item as unread.

[![Exchange Restore](images/exchange_restore_options.webp)](images/exchange_restore_options.webp "Exchange Restore")

1. [Optional] At the Reason step, specify a restore reason. This information will be available in the Reason column on the Restore Sessions tab and you will be able to reference it later.

[![Exchange Restore](images/exchange_reason.webp)](images/exchange_reason.webp "Exchange Restore")

1. At the Summary step, review details of the restore operation and click Finish.

Restore Portal runs the restore operation immediately and opens the [Restore Sessions](ssp_ui.md#restore_sessions) tab, where you view details about restore session progress and results.


