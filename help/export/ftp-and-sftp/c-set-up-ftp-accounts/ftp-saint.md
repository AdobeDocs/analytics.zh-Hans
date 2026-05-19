---
description: 分类 (SAINT) FTP 选项在上传较大的分类数据集方面具有更大的灵活性，包括能够将数据上传到多个报表包，并可上传大于 50,000 行的数据集。
keywords: ftp;sftp
title: 分类
feature: FTP Export
exl-id: fc783328-a70b-4af3-b3d3-c59ab79d6b8f
TQID: https://experienceleague.adobe.com/JdxiVF-HzQPiFzC6CH0yeIIPEulsacjl11-X8wLMrl4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 64%

---

# 分类

分类 FTP 选项在上传较大的分类数据集方面具有更大的灵活性，包括能够将数据上传到多个报表包，并可上传大于 50000 行的数据集。

系统导入这些文件所需的时间因多种因素而异。 如果上传的文件在 FTP 服务器上留存超过三天，请让贵组织的支持用户联系 Adobe 客户关怀部门。

成功的导入会立即显示导出中的相应更改，而浏览器导入的数据更改可能最多需要4小时，FTP导入的数据更改可能最多需要24小时。

有关FTP限制和数据保留的信息，请参阅[FTP限制和数据保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 关于分类和数据源上传时使用的 `.fin` 文件 {#section_1484719F8A134EAE91212DBD8F15174F}

在上传分类或数据Source文件（`.tab`或`.txt`）时，还要求您上传一个与正在导入的数据文件完全同名，但具有。`.fin`的空白文件 扩展。 此 `.fin` 文件是一个完成文件。 此文件的作用是告诉系统该数据文件已完全上传到 FTP 帐户。 `.fin` 文件可让 Adobe 知道您已完成导入。

在您提交源文件和 `.fin` 文件后，一定要从 FTP 站点注销。 原因是 Adobe Analytics 使用注销事件作为文件准备处理的触发器。 导入完成后，Adobe 会从 FTP 位置删除这两个文件。

完成文件：[!DNL Classifications.fin]

如果您在上传数据源或分类文件时没有提供 `.fin` 文件，Adobe 不会将它添加到待处理的队列。 该文件将保留在FTP上，不会应用于CX Enterprise中的数据。 只有在Analytics的[!UICONTROL 创建FTP帐户]窗口中输入您的电子邮件地址作为[!UICONTROL 通知收件人]时，才会通知您。 如果未在此字段中输入电子邮件地址，则不会发送任何通知。

如果您上传文件时含有 `.fin` 文件，但文件中存在错误，则在提交它进行处理时，该错误会导致处理停止，并将文件发送到错误文件夹。 如果发生这种情况，会向[!UICONTROL 创建 FTP 帐户]窗口的[!UICONTROL 通知收件人]字段中列出的电子邮件地址发送一个通知。 如果没有输入电子邮件地址，则不会发送通知。
