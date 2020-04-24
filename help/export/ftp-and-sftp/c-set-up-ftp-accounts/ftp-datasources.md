---
description: 您可以使用 Analytics 创建和管理基于 FTP 的数据源，它可以利用 FTP 文件传输将离线数据或历史数据导入 Experience Cloud。
keywords: ftp;sftp
title: 数据源
uuid: 41ba2de7-d33d-4394-b7d8-04a116f45419
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 数据源

您可以使用 Analytics 创建和管理基于 FTP 的数据源，它可以利用 FTP 文件传输将离线数据或历史数据导入 Experience Cloud。

在创建数据源实例后，该工具会提供一个可用来上载数据源文件的 FTP 位置。上载完成之后，Data Sources 可自动查找并处理这些数据源文件。在文件经过处理后，该数据即可用于 Analytics 报表。

The [!UICONTROL Create] tab in the Data Sources Manager lets you configure a new Data Sources instance for the selected report suite. The [!UICONTROL Data Sources Wizard] guides you through the process of creating a Data Sources template, and creates an FTP location for uploading data.

In the [!UICONTROL Manage Data Sources] window, find your data source and select the FTP Info link. 您的FTP登录信息将显示在 [!UICONTROL Activate a Data Source] 该部分的窗 [!UICONTROL Upload/FTP Information] 口中。

有关FTP限制和数据保留的信息，请参阅 [FTP限制和数据保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 关于分类和数据源上传时使用的 .fin 文件 {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. 此 [!DNL .fin] 文件是一个完成文件。此文件的作用是告诉系统该数据文件已完全上传到 FTP 帐户。[!DNL .fin] 文件可让 Adobe 知道您已完成导入。在提交之后，Adobe 会从 FTP 上删除这两个文件，并开始处理导入。导入文件: [!DNL Classifications.tab]

完成文件：[!DNL Classifications.fin]

如果您在上传数据源或 SAINT 文件时没有提供 [!DNL .fin] 文件，Adobe 不会将它添加到待处理的队列。该文件将保留在 FTP 上，并且不会被应用到 [!UICONTROL Experience Cloud] 中的数据。You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of reporting. 如果没有在此字段中输入电子邮件地址，则不会发送通知。

如果您上传文件时含有 [!DNL .fin] 文件，但文件中存在错误，则在提交它进行处理时，该错误会导致处理停止，并将文件发送到错误文件夹。If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. 如果没有输入电子邮件地址，则不会发送通知。
