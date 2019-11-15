---
description: 描述如何上载数据源文件的步骤。
solution: Analytics
subtopic: Data sources
title: 上载数据源文件
topic: Developer and implementation
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 上载数据源文件

描述如何上载数据源文件的步骤。

在准备好一个数据源数据文件之后，可将其提交到数据源进行处理。Adobe 设有多个可用于上载数据源文件的数据源 FTP 服务器。请记住有关数据源 FTP 服务器的以下注意事项：

* Select FTP Info next to the Data Source entry in the [!UICONTROL Data Sources Manage] tab to see the FTP Host, Login, and Password information for the data source's FTP account. 拥有此信息访问权限的任何人都可以将数据上载到您的报表包。
* 出于安全考虑，FTP 帐户闲置 30 天之后会被关闭。
* FTP 帐户特定于数据源。您无法使用一个 FTP 帐户将数据源文件上载到多个数据源。

**上载数据源文件**

1. 使用 FTP 客户端将数据发送到数据源 FTP 网站。

   （可在数据源管理器的“FTP 信息”链接中使用）。

1. Upload a [!DNL .fin] file to notify Adobe that the Data Sources file upload is complete.

   The [!DNL .fin] file must have the exact same name as the Data Sources file, except for the file extension. Adobe does not queue the Data Sources file for processing until you upload the [!DNL .fin] file.

   请在所有数据源文件都上载完之后才上载该文件。否则，数据源可能尝试处理不完整的文件。
1. 请留意数据源文件处理期间出现的任何消息。

   数据源管理器会显示在文件处理期间发生的任何错误。

