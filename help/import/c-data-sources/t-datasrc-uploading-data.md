---
description: 描述如何上载数据源文件的步骤。
seo-description: 描述如何上载数据源文件的步骤。
seo-title: 上传数据源文件
solution: Analytics
subtopic: 数据源
title: 上传数据源文件
topic: 开发人员和实施
uuid: 5dde91-1297-47e5-9393-611b40413c17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 上传数据源文件

描述如何上载数据源文件的步骤。

在准备好一个数据源数据文件之后，可将其提交到数据源进行处理。Adobe 设有多个可用于上载数据源文件的数据源 FTP 服务器。请记住有关数据源 FTP 服务器的以下注意事项：

* 在“[!UICONTROL 数据源管理]”选项卡中选择数据源条目旁边的“FTP 信息”，可查看数据源 FTP 帐户的 FTP 主机、登录和密码信息。拥有此信息访问权限的任何人都可以将数据上载到您的报表包。
* 出于安全考虑，FTP 帐户闲置 30 天之后会被关闭。
* FTP 帐户特定于数据源。您无法使用一个 FTP 帐户将数据源文件上载到多个数据源。

**上载数据源文件**

1. 使用 FTP 客户端将数据发送到数据源 FTP 网站。

   （可在数据源管理器的“FTP 信息”链接中使用）。

1. Upload a [!DNL .fin] file to notify Adobe that the Data Sources file upload is complete.

   [!DNL .fin] 文件的名称必须与Data Sources文件的名称完全相同，但文件扩展名除外。Adobe does not queue the Data Sources file for processing until you upload the [!DNL .fin] file.

   请在所有数据源文件都上载完之后才上载该文件。否则，数据源可能尝试处理不完整的文件。
1. 请留意数据源文件处理期间出现的任何消息。

   数据源管理器会显示在文件处理期间发生的任何错误。

