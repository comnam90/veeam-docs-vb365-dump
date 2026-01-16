---
title: "permissions_linux"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/permissions_linux.html"
last_updated: "12/6/2024"
product_version: "8.3.0.2201"
---


In this article

This section contains permissions required by Veeam Backup for Microsoft 365 for a service account that is used to run Veeam Backup for Microsoft 365 Proxy Service on a Linux-based backup proxy server. By default, Veeam Backup for Microsoft 365 creates and uses the veeam365backup service account, but you can use a service account of your own.

A service account must be added to the sudoers file to start, stop and register services.

The following are required permissions for a service account on a Linux-based backup proxy server:

|  |
| --- |
| #!/usr/bin/env bash    accountName=$1    certDirectory="/etc/veeam/certs"  globalConfigDirectory="/etc/veeam/backup365"  logDirectory="/var/log"  serviceDirectory="/opt/veeamvboproxy"    echo "Define permissions"  chown :$accountName /etc/shadow  chmod g+rw /etc/shadow    chown -R :$accountName $certDirectory  chmod -R g+rw $certDirectory    chown -R $accountName: $globalConfigDirectory  chmod -R u+rw $globalConfigDirectory    chown -R :$accountName $logDirectory  chmod -R g+rw $logDirectory    chown -R $accountName:$accountName $serviceDirectory  chown $accountName:$accountName $serviceDirectory  chmod u+rwx,g+rwx $serviceDirectory  chmod -R u+rwx,g+rwx "$serviceDirectory/PSModules"  chmod -R u+rwx,g+rwx "$serviceDirectory/Packages"  chmod -R u+rwx,g+rw "$serviceDirectory/Xml"  chmod -R u+rwx,g+rwx "$serviceDirectory/libraries"  chmod -R u+rwx,g+rwx "$serviceDirectory/UpdateServices"  chmod u+rwx,g+rwx "$serviceDirectory/Veeam.Archiver.Proxy"  chmod u+rwx,g+rwx "$serviceDirectory/UpdateServices/Veeam.Tools.UpdateWarden"  chmod u+rwx,g+rwx "$serviceDirectory/UpdateServices/Service/Veeam.Tools.UpdateWarden.Service"    chmod 600 "$serviceDirectory/Proxy.ini"    setcap "CAP\_WAKE\_ALARM+ep" "$serviceDirectory/Veeam.Archiver.Proxy" |

Related Topics

[Adding Linux-Based Backup Proxy Server](add_linux_proxy.md)

Page updated 12/6/2024

Page content applies to build 8.3.0.2201
