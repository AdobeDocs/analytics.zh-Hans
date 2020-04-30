---
description: 分类 (SAINT) FTP 选项在上传较大的分类数据集方面具有更大的灵活性，包括能够将数据上传到多个报表包，并可上传大于 50000 行的数据集。
keywords: ftp;sftp
title: 分类
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 分类

分类 FTP 选项在上传较大的分类数据集方面具有更大的灵活性，包括能够将数据上传到多个报表包，并可上传大于 50000 行的数据集。

请参阅[分类](https://docs.adobe.com/content/help/en/analytics/components/classifications/classifications-importer/c-working-with-saint.html)，以了解有关如何通过 FTP 下载分类数据，以及如何通过 FTP 上传数据文件的步骤（包括创建 FTP 帐户的步骤）。

系统导入这些文件所需的时间长短取决于多种因素。如果已上传的文件在六小时后仍留存在 FTP 服务器上，请让贵组织的支持用户联系 Adobe 客户关怀。

虽然 Analytics 中的数据更改在通过浏览器导入时可能需要花费 4 个小时，而在通过 FTP 导入时可能需花费多达 24 个小时，但成功导入后会立即在导出中显示相应的更改。

有关 FTP 限制和数据保留的信息，请参阅 [FTP 限制和数据保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 关于分类和数据源上传时使用的 .fin 文件 {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. 此 [!DNL .fin] 文件是一个完成文件。此文件的作用是告诉系统该数据文件已完全上传到 FTP 帐户。[!DNL .fin] 文件可让 Adobe 知道您已完成导入。在提交之后，Adobe 会从 FTP 上删除这两个文件，并开始处理导入。导入文件: [!DNL Classifications.tab]

完成文件：[!DNL Classifications.fin]

如果您在上传数据源或分类文件时没有提供 [!DNL .fin] 文件，Adobe 不会将它添加到待处理的队列。该文件将保留在 FTP 上，并且不会被应用到 [!UICONTROL Experience Cloud] 中的数据。You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of Analytics. 如果没有在此字段中输入电子邮件地址，则不会发送通知。

如果您上传文件时含有 [!DNL .fin] 文件，但文件中存在错误，则在提交它进行处理时，该错误会导致处理停止，并将文件发送到错误文件夹。If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. 如果没有输入电子邮件地址，则不会发送通知。
