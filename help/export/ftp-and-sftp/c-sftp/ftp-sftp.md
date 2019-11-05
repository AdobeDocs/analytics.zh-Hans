---
description: SFTP是一种用于传输数据的安全协议，可确保除您之外没有人能够看到您的数据。 Adobe工程服务可以设置SFTP帐户以安全保留您的数据。
keywords: ftp;sftp
seo-description: SFTP是一种用于传输数据的安全协议，可确保除您之外没有人能够看到您的数据。 Adobe工程服务可以设置SFTP帐户以安全保留您的数据。
seo-title: 安全文件传输协议 - 概述
solution: Analytics
title: 安全文件传输协议 - 概述
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: tm+mt
source-git-commit: 2fc1a01aced4cf2b165b46353418fbee9b83bee5

---


# 安全文件传输协议 - 概述

SFTP是一种用于传输数据的安全协议，可确保除您之外没有人能够看到您的数据。 Adobe工程服务可以设置SFTP帐户以安全保留您的数据。

## 推送传送 {#section_A47831BB1DCA490BB57F0940617AA506}

这表示 Adobe 的服务器将文件“推送”到您的服务器。我们实质上是将它传送到您的端点。

[数据仓库](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) 和 [Analytics数据馈送](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) ，可通过SFTP推送数据。

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Report Builder

## 提取传送 {#section_FA29FAEF02FE40B8B32452146A036F48}

这表示文件是使用普通 FTP 传送到 Adobe 的其中一个服务器。如果您希望将文件放在服务器上，则必须使用SFTP将其从Adobe的服务器上从您的服务器拉到Adobe的FTP服务器。 您可以使用以下三种方法之一完成这项工作：

* [在无密码的情况下通过 SFTP 连接到 Adobe.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [使用SFTP连接到Adobe FTP帐户。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* 您可以将任何需要的报表推送到 Adobe 的 FTP 式数据馈送/报告与分析/临时分析等，然后再提取它们。Adobe无法将这些报告传送到您设置的SFTP服务器。

