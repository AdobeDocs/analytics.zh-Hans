---
description: 您可以使用 Analytics 创建和管理基于 FTP 的数据源，它可以利用 FTP 文件传输将离线数据或历史数据导入 Experience Cloud。
keywords: ftp；sftp
seo-description: 您可以使用 Analytics 创建和管理基于 FTP 的数据源，它可以利用 FTP 文件传输将离线数据或历史数据导入 Experience Cloud。
seo-title: 数据源
solution: Analytics
title: 数据源
uuid: 41ba2de7-d33 d-4394-b7 d8-04a116 f45419
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 数据源

您可以使用 Analytics 创建和管理基于 FTP 的数据源，它可以利用 FTP 文件传输将离线数据或历史数据导入 Experience Cloud。

在创建数据源实例后，该工具会提供一个可用来上载数据源文件的 FTP 位置。上载完成之后，Data Sources 可自动查找并处理这些数据源文件。在文件经过处理后，该数据即可用于 Analytics 报表。

您可以通过数据源管理器中的“[!UICONTROL 创建]”选项卡为选定报表包配置新的数据源实例。“[!UICONTROL 数据源向导]”可引导您完成创建数据源模板的过程，然后为上传数据创建一个 FTP 位置。

在“[!UICONTROL 管理数据源]”窗口中，查找您的数据源并选择“FTP 信息”链接。您的 FTP 登录信息会在“[!UICONTROL 上传/FTP 信息]”部分的“[!UICONTROL 激活数据源]”窗口中显示。

有关 FTP 限制和数据保留的信息，请参阅[FTP 限制和数据保留](../../../export/ftp-and-sftp/ftp-limits.md#concept_8CAA1D8F27B3411AB902520AD6C9A70E)。

## 关于分类和数据源上传时使用的 .fin 文件 {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. 此文件的作用是告诉系统该数据文件已完全上传到 FTP 帐户。[!DNL .fin] 该文件可让Adobe识别您已完成导入。在提交之后，Adobe 会从 FTP 上删除这两个文件，并开始处理导入。导入文件: [!DNL Classifications.tab]

Finish File: [!DNL Classifications.fin]

If you upload your Data Sources or SAINT file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. 只有您在报表的“[!UICONTROL 创建 FTP 帐户]”窗口的“[!UICONTROL 通知收件人]”中输入了您的电子邮件地址，才会向您发出通知。如果没有在此字段中输入电子邮件地址，则不会发送通知。

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. 如果发生这种情况，会向“[!UICONTROL 创建 FTP 帐户]”窗口的“[!UICONTROL 通知收件人]”字段中列出的电子邮件地址发送一个通知。如果没有输入电子邮件地址，则不会发送通知。
