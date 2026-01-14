---
title: "vbo_threads_and_limit"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/vbo_threads_and_limit.html"
last_updated: "7/16/2024"
product_version: "8.3.0.2201"
---


In this article

Veeam Backup for Microsoft 365 allows you to limit download speed.

To limit download speed, do the following:

1. On the General tab, select the Throttle network traffic to check box and specify the average download speed.

For example, if you have set this value to 10 Mbps and have downloaded 100 Mb in 8 seconds, Veeam Backup for Microsoft 365 will stop retrieving new data for approximately 2 minutes after which download will be resumed automatically. The exact time for which Veeam Backup for Microsoft 365 stops getting data is calculated by predefined algorithms and depends upon the value that you specify as traffic throttling, the amount of downloaded data and the amount of time it took to get this data.

1. Click OK.

[![Modifying Backup Proxy Server Properties](images/proxy_limit.webp)](images/proxy_limit.webp "Modifying Backup Proxy Server Properties")

Page updated 7/16/2024

Page content applies to build 8.3.0.2201
