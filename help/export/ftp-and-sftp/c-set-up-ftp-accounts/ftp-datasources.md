---
description: 您可以使用 Analytics 创建和管理基于 FTP 的数据源，它可以利用 FTP 文件传输将离线数据或历史数据导入 Experience Cloud。
keywords: ftp;sftp
title: 数据源概述
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
source-git-commit: 7dc97ad5225baf56c829efc8c21b07154bdd8ff9
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 96%

---

# 基于FTP的数据源

您可以使用 Analytics 创建和管理基于 FTP 的数据源，它可以利用 FTP 文件传输将离线数据或历史数据导入 Experience Cloud。

在创建数据源实例后，该工具会提供一个可用来上传数据源文件的 FTP 位置。上传完成之后，Data Sources 可自动查找并处理这些数据源文件。在文件经过处理后，该数据即可用于 Analytics 报表。

您可以通过数据源管理器中的“[!UICONTROL 创建]”选项卡为选定报表包配置新的数据源实例。“[!UICONTROL 数据源向导]”可引导您完成创建数据源模板的过程，然后为上传数据创建一个 FTP 位置。

在“[!UICONTROL 管理数据源]”窗口中，查找您的数据源并选择“FTP 信息”链接。您的 FTP 登录信息会在“[!UICONTROL 上传/FTP 信息]”部分的“[!UICONTROL 激活数据源]”窗口中显示。

有关FTP限制和数据保留的信息，请参阅[FTP限制和数据保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 关于用于分类和上传数据源的 .fin 文件 {#section_1484719F8A134EAE91212DBD8F15174F}

在上传分类或[!UICONTROL 数据源]文件（[!DNL .tab] 或 [!DNL .txt]）时，还要求您上传一个与正在导入的数据文件完全同名，但具有 [!DNL .fin] 扩展名的空白文件。此 [!DNL .fin] 文件是一个完成文件。此文件的作用是告诉系统该数据文件已完全上传到 FTP 帐户。[!DNL .fin] 文件可让 Adobe 知道您已完成导入。在提交之后，Adobe 会从 FTP 上删除这两个文件，并开始处理导入。导入文件: [!DNL Classifications.tab]

完成文件：[!DNL Classifications.fin]

如果您在上传数据源或 SAINT 文件时没有提供 [!DNL .fin] 文件，Adobe 不会将它添加到待处理的队列。该文件将保留在 FTP 上，并且不会被应用到 [!UICONTROL Experience Cloud] 中的数据。只有您在报表的“[!UICONTROL 创建 FTP 帐户]”窗口的“[!UICONTROL 通知收件人]”中输入了您的电子邮件地址，才会向您发出通知。如果没有在此字段中输入电子邮件地址，则不会发送通知。

如果您上传文件时含有 [!DNL .fin] 文件，但文件中存在错误，则在提交它进行处理时，该错误会导致处理停止，并将文件发送到错误文件夹。如果发生这种情况，会向[!UICONTROL 创建 FTP 帐户]窗口的[!UICONTROL 通知收件人]字段中列出的电子邮件地址发送一个通知。如果没有输入电子邮件地址，则不会发送通知。
