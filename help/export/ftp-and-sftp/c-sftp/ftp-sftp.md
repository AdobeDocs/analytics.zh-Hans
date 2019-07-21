---
description: SFTP是一个安全的协议，用于传输数据，确保无人能看到您的数据，而是您的数据。Adobe工程服务可设置SFTP帐户以安全地保留您的数据。
keywords: ftp；sftp
seo-description: SFTP是一个安全的协议，用于传输数据，确保无人能看到您的数据，而是您的数据。Adobe工程服务可设置SFTP帐户以安全地保留您的数据。
seo-title: 安全文件传输协议-概述
solution: Analytics
title: 安全文件传输协议-概述
uuid: 7dd1a867-e828-4c7 b-bf11-75a81 d4 c149 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 安全文件传输协议-概述

SFTP是一个安全的协议，用于传输数据，确保无人能看到您的数据，而是您的数据。Adobe工程服务可设置SFTP帐户以安全地保留您的数据。

## 推送传送 {#section_A47831BB1DCA490BB57F0940617AA506}

这表示 Adobe 的服务器将文件“推送”到您的服务器。我们实质上是将它传送到您的端点。

[数据仓库](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md#concept_904ADB7B4FE04DCCB90EFDB6D0DB1076) 和 [分析数据馈送](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) 可通过SFTP推送数据。

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Report Builder

## 提取传送 {#section_FA29FAEF02FE40B8B32452146A036F48}

这表示文件是使用普通 FTP 传送到 Adobe 的其中一个服务器。如果您需要服务器上的文件，则必须将使用SFTP的服务器从服务器上传到Adobe的FTP服务器。您可以使用以下三种方法之一完成这项工作：

* [无需口令即可通过SFTP连接到Adobe。](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846)
* [使用SFTP连接到Adobe FTP帐户。](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md#concept_01176600188441C6AFB28F5E264D89F8)
* 您可以将任何需要的报表推送到 Adobe 的 FTP 式数据馈送/报告与分析/临时分析等，然后再提取它们。Adobe无法将这些报告发送到您设置的SFTP服务器。

