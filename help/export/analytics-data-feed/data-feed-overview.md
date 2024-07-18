---
description: 在 Adobe Data Warehouse 中可处理和存储从网站、移动应用程序收集，或使用 Web 服务 API 或数据源上载的数据。该原始点击流数据形成 Adobe Analytics 使用的数据集。
keywords: 点击流;数据馈送;数据馈送;数据馈送
title: Analytics 数据馈送概述
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 84bdeb5d502e46c922fc5123fcdd5b6819426c0e
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 96%

---

# Analytics 数据馈送概述

数据馈送是从 Adobe Analytics 中获取原始数据的有效方法。此原始数据可在 Adobe 以外的其他平台中使用，具体所用平台由您的组织自行决定。数据在每小时结束时以小时为单位分批发送，或者在每天结束时以天为单位分批发送。

## 先决条件

在使用数据馈送之前，请确保您满足以下所有要求。

* 将数据发送到 Adobe 数据收集服务器的有效实施。请参阅《实施指南》中的[验证和发布实施](/help/implement/launch/validate-publish-prod.md)。
* 您的帐户是 Analytics 产品管理员，或者属于有权访问数据馈送的产品配置文件。
* 在 Amazon S3、Google Cloud Platform、Azure RBAC 或 Azure SAS 上配置的分段。
* （旧版：仅对旧版 FTP 和 SFTP 目标类型是必需的）准备好 FTP 站点和凭据（由您的组织提供的 FTP 凭据。）

## 后续步骤

以下资源可帮助您了解获取数据馈送的基本工作流。了解基本工作流后，您可以与组织内的团队合作，将原始数据存储或纳入到数据库中。

* [数据馈送最佳实践](/help/export/analytics-data-feed/data-feeds-best-practices.md)：有关创建和管理数据馈送的最佳实践。
* [创建数据馈送](create-feed.md)：有关创建数据馈送的技术详细信息，更加详细地阐述各个字段
* [管理数据馈送](df-manage-feeds.md)：了解有关导览数据馈送界面的更多信息
* [数据馈送内容](c-df-contents/datafeeds-contents.md)：了解压缩文件<!-- Is this still the output users can download from the destination? I aske Jun. -->中的内容
* [数据列定义](c-df-contents/datafeeds-reference.md)：所有可用列的完整列表。
* 导览数据馈送界面的视频：

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* 有关如何查找数据馈送 ID 的视频：

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)