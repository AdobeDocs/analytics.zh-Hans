---
description: 分类 (SAINT) FTP 选项在上传较大的分类数据集方面具有更大的灵活性，包括能够将数据上传到多个报表包，并可上传大于 50000 行的数据集。
keywords: ftp;sftp
title: 分类
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 7a70a5185b768dbc09deca5c8989693501af0cca
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 68%

---


# 分类

分类 FTP 选项在上传较大的分类数据集方面具有更大的灵活性，包括能够将数据上传到多个报表包，并可上传大于 50000 行的数据集。

请参阅[分类](https://docs.adobe.com/content/help/zh-Hans/analytics/components/classifications/classifications-importer/c-working-with-saint.html)，以了解有关如何通过 FTP 下载分类数据，以及如何通过 FTP 上传数据文件的步骤（包括创建 FTP 帐户的步骤）。

系统导入这些文件所需的时间长短取决于多种因素。如果FTP服务器上存在已上载文件超过三天，请与组织受支持用户联系Adobe客户服务中心。

虽然 Analytics 中的数据更改在通过浏览器导入时可能需要花费 4 个小时，而在通过 FTP 导入时可能需花费多达 24 个小时，但成功导入后会立即在导出中显示相应的更改。

有关 FTP 限制和数据保留的信息，请参阅 [FTP 限制和数据保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## About the `.fin` file for Classifications and Data Sources Uploads {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a Classification or Data Source file (`.tab` or `.txt`), the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a .`.fin` extension. 此 `.fin` 文件是一个完成文件。此文件的作用是告诉系统该数据文件已完全上传到 FTP 帐户。`.fin` 文件可让 Adobe 知道您已完成导入。

提交源文件和文 `.fin` 件后，请务必从FTP站点注销。 原因是Adobe Analytics使用注销事件作为触发器，文件已准备好进行处理。 完成导入后，Adobe会从FTP位置删除这两个文件。

完成文件：[!DNL Classifications.fin]

If you upload your Data Sources or Classification file without an accompanying `.fin` file, Adobe does not add it to the queue for processing. 该文件将保留在 FTP 上，并且不会被应用到 [!UICONTROL Experience Cloud] 中的数据。只有您在 Analytics 的“[!UICONTROL 创建 FTP 帐户]”窗口的“[!UICONTROL 通知收件人]”中输入了您的电子邮件地址，才会向您发出通知。如果没有在此字段中输入电子邮件地址，则不会发送通知。

如果您上传文件时含有 `.fin` 文件，但文件中存在错误，则在提交它进行处理时，该错误会导致处理停止，并将文件发送到错误文件夹。如果发生这种情况，会向“[!UICONTROL 创建 FTP 帐户]”窗口的“[!UICONTROL 通知收件人]”字段中列出的电子邮件地址发送一个通知。如果未输入电子邮件地址，则不会发送通知。
