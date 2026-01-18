---
title: "VBOJobStatistics"
product: "vb365"
doc_type: "powershell"
source_url: "https://helpcenter.veeam.com/docs/vbo365/powershell/vbojobstatistics.html"
last_updated: "1/14/2026"
product_version: "8.3.0.2201"
---

# VBOJobStatistics


Contains statistics on a backup or a backup copy job. See also [VBOJobSession](vbojobsession.md).

| Property | Type | Description |
| --- | --- | --- |
| ProcessingRate | String | Average speed of data processing. |
| ReadRate | String | Average speed of reading data from the backup repository. |
| WriteRate | String | Average speed of writing data to the backup repository. |
| TransferredData | String | Amount of data transferred from source to target before applying compression and deduplication. |
| ProcessedObjects | Long | Number of items processed by the backup or backup copy job. |
| Bottleneck | VBOJobBottleneck | Bottleneck in the data transmission process. Possible values:   * NA * Detecting * Source * Target |


