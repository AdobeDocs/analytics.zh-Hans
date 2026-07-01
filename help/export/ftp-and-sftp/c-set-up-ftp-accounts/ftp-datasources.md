---
description: 您可以使用Analytics创建和管理基于FTP的数据源，它可以利用FTP文件传输将离线数据或历史数据导入CX Enterprise。
keywords: ftp;sftp
title: 数据源概述
feature: FTP Export
exl-id: 777917bd-bd11-4360-a149-e4fd0bb2f99e
TQID: 'https://experienceleague.adobe.com/3i-ms9Q49CUmEwXiQLek15S3-Kvvh0IIv19-hm01EN0'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: e681610c8238aa4940053a28ee60ea54492cba8b
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 42%

---

# 基于FTP的数据源

您可以使用Analytics创建和管理基于FTP的数据源，它可以利用FTP文件传输将离线数据或历史数据导入CX Enterprise。

在创建数据源实例后，该工具会提供一个可用来上传数据源文件的 FTP 位置。 上传完成之后，Data Sources 可自动查找并处理这些数据源文件。 处理完文件后，数据可用于Analytics报表。

数据源管理器中的[!UICONTROL 创建]选项卡允许您为所选报表包配置新的数据源实例。 数据源向导将指导您完成创建数据源模板的过程，并创建用于上传数据的FTP位置。

在[!UICONTROL 管理数据源]窗口中，找到您的数据源并选择“FTP信息”链接。 您的FTP登录信息显示在[!UICONTROL 上传/FTP信息]部分的[!UICONTROL 激活数据Source]窗口中。

有关FTP限制和数据保留的信息，请参阅[FTP限制和数据保留](/help/export/ftp-and-sftp/ftp-limits.md)。

## 关于用于分类和上传数据源的 .fin 文件 {#section_1484719F8A134EAE91212DBD8F15174F}

在上传分类或数据源文件（`.tab`或`.txt`）时，还要求您上传一个与正在导入的数据文件完全同名，但具有`.fin`扩展名的空白文件。 此 `.fin` 文件是一个完成文件。 此文件的作用是告诉系统该数据文件已完全上传到 FTP 帐户。 `.fin` 文件可让 Adobe 知道您已完成导入。 在提交之后，Adobe 会从 FTP 上删除这两个文件，并开始处理导入。

导入文件: `Classifications.tab`

完成文件：`Classifications.fin`

如果您在上传数据源或 SAINT 文件时没有提供 `.fin` 文件，Adobe 不会将它添加到待处理的队列。 该文件将保留在FTP上，不会应用于CX Enterprise中的数据。 仅当在报告的[!UICONTROL 创建FTP帐户]窗口中输入您的电子邮件地址作为[!UICONTROL 通知收件人]时，才会通知您。 如果未在此字段中输入电子邮件地址，则不会发送任何通知。

如果您上传文件时含有 `.fin` 文件，但文件中存在错误，则在提交它进行处理时，该错误会导致处理停止，并将文件发送到错误文件夹。 如果发生这种情况，会向[!UICONTROL 创建 FTP 帐户]窗口的[!UICONTROL 通知收件人]字段中列出的电子邮件地址发送一个通知。 如果未输入电子邮件地址，则不会发送通知。
