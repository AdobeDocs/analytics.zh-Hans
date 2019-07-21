---
description: 分类 (SAINT) FTP 选项在上传较大的分类数据集方面具有更大的灵活性，包括能够将数据上传到多个报表包，并可上传大于 50000 行的数据集。
keywords: ftp；sftp
seo-description: 分类 (SAINT) FTP 选项在上传较大的分类数据集方面具有更大的灵活性，包括能够将数据上传到多个报表包，并可上传大于 50000 行的数据集。
seo-title: 分类
solution: Analytics
title: 分类
uuid: 35936c98-b785-43eb-89f4-ab42 a10 db256
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 分类

分类FTP选项在上传大型分类数据集方面提供了更大的灵活性，包括将数据上载到多个报表包以及上传大于50,000行的数据集的能力。

请参阅[分类](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html)，以了解有关如何通过 FTP 下载分类数据，以及如何通过 FTP 上传数据文件的步骤（包括创建 FTP 帐户的步骤）。

系统导入这些文件所需的时间长短取决于多种因素。如果已上传的文件在六小时后仍留存在 FTP 服务器上，请让贵组织的支持用户联系 Adobe 客户关怀。

虽然 Analytics 中的数据更改在通过浏览器导入时可能需要花费 4 个小时，而在通过 FTP 导入时可能需花费多达 24 个小时，但成功导入后会立即在导出中显示相应的更改。

有关 FTP 限制和数据保留的信息，请参阅[FTP 限制和数据保留](../../../export/ftp-and-sftp/ftp-limits.md#concept_8CAA1D8F27B3411AB902520AD6C9A70E)。

## 关于分类和数据源上传时使用的 .fin 文件 {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. 此文件的作用是告诉系统该数据文件已完全上传到 FTP 帐户。[!DNL .fin] 该文件可让Adobe识别您已完成导入。在提交之后，Adobe 会从 FTP 上删除这两个文件，并开始处理导入。导入文件: [!DNL Classifications.tab]

Finish File: [!DNL Classifications.fin]

If you upload your Data Sources or classification file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. 只有您在 Analytics 的“[!UICONTROL 创建 FTP 帐户]”窗口的“[!UICONTROL 通知收件人]”中输入了您的电子邮件地址，才会向您发出通知。如果没有在此字段中输入电子邮件地址，则不会发送通知。

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. 如果发生这种情况，会向“[!UICONTROL 创建 FTP 帐户]”窗口的“[!UICONTROL 通知收件人]”字段中列出的电子邮件地址发送一个通知。如果没有输入电子邮件地址，则不会发送通知。
