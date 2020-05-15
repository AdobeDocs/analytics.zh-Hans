---
description: SFTP 是一种用于传输数据的安全协议，它可确保除你之外，没有人能看到您的数据。Adobe 工程技术服务可设置一个 SFTP 帐户，以安全保留您的数据。
keywords: ftp;sftp
title: 安全文件传输协议 - 概述
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: ht
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# 安全文件传输协议 - 概述

SFTP 是一种用于传输数据的安全协议，它可确保除你之外，没有人能看到您的数据。Adobe 工程技术服务可设置一个 SFTP 帐户，以安全保留您的数据。

## 推送传送 {#section_A47831BB1DCA490BB57F0940617AA506}

这表示 Adobe 的服务器将文件“推送”到您的服务器。我们实质上是将它传送到您的端点。

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) 和 [Analytics 数据馈送](https://docs.adobe.com/content/help/zh-Hans/analytics/export/analytics-data-feed/data-feed-overview.html)可通过 SFTP 推送数据。

以下 Analytics 工具&#x200B;**不能**&#x200B;通过 SFTP 推送数据。

* Reports &amp; Analytics
* Ad Hoc Analysis
* Report Builder

## 提取传送 {#section_FA29FAEF02FE40B8B32452146A036F48}

这表示文件是使用普通 FTP 传送到 Adobe 的其中一个服务器。如果您需要您服务器上的文件，则必须使用 Adobe 服务器上的 SFTP 将它从您的服务器提取到 Adobe 的 FTP 服务器。您可以使用以下三种方法之一完成这项工作：

* [在无密码的情况下通过 SFTP 连接到 Adobe。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [通过 SFTP 连接到 Adobe FTP 帐户。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* 您可以将任何需要的报表推送到 Adobe 的 FTP 式数据馈送/报告与分析/临时分析等，然后再提取它们。Adobe 无法将这些报表传送到您所设置的 SFTP 服务器。

