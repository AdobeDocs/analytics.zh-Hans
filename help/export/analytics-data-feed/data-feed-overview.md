---
description: 在 Adobe Data Warehouse 中可处理和存储从网站、移动应用程序收集，或使用 Web 服务 API 或数据源上载的数据。该原始点击流数据形成 Adobe Analytics 使用的数据集。
keywords: 点击流;数据馈送;数据馈送;数据馈送
title: Analytics 数据馈送概述
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 0916ef4ddc2ca65f01721f4d79d7af825dcf50e3
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 83%

---

# Analytics 数据馈送概述

>[!AVAILABILITY]
>
>此页面上描述的某些目标类型处于版本的有限测试阶段，可能尚未在您的环境中提供。 当该功能正式发布时，将删除此说明。有关 Analytics 发布流程的信息，请参阅 [Adobe Analytics 功能发布](/help/release-notes/releases.md)。

数据馈送是从 Adobe Analytics 中获取原始数据的有效方法。此原始数据可在 Adobe 以外的其他平台中使用，具体所用平台由您的组织自行决定。数据在每小时结束时以小时为单位分批发送，或者在每天结束时以天为单位分批发送。

## 先决条件

在使用数据馈送之前，请确保您满足以下所有要求。

* 将数据发送到 Adobe 数据收集服务器的有效实施。参见 [验证和发布实施](/help/implement/launch/validate-publish-prod.md) 实施指南中的。
* 您的帐户是 Analytics 产品管理员，或者属于有权访问数据馈送的产品配置文件。
* 在Amazon S3、Google Cloud Platform、Azure RBAC或Azure SAS上配置的存储桶。
* （旧版：仅旧版FTP和SFTP目标类型需要）便于使用FTP站点和凭据（由您的组织提供的FTP凭据）。

## 推荐的数据馈送资源

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
3. 在顶部导航栏中，导航到“管理员”>“数据馈送”。
4. 单击[!UICONTROL 添加]。此时将显示一个新页面，该页面具有三个主要类别：“[!UICONTROL 馈送信息]”、“[!UICONTROL 目标]”和“[!UICONTROL 数据列定义]”。
5. 填写“[!UICONTROL 馈送信息]”字段。
   * 名称：任何所需的名称，如“测试数据馈送”。
   * 报告包：选择所需的报告包。
   * 完成时发送电子邮件：输入您的电子邮件。
   * 馈送间隔：选择所需的间隔（每小时或每天）。
   * 延迟处理：可保留为“[!UICONTROL 无延迟]”。
   * 开始和结束日期：将几天前的某个日期选为开始日期，将当天选为结束日期。
6. 填写“[!UICONTROL 目标]”字段。
   * 类型：FTP
   * 主机：输入所需的 FTP 目标 URL。例如：`ftp://ftp.omniture.com`。
   * 路径：可留空
   * 用户名：输入用户名以登录 FTP 网站。
   * 密码和确认密码：输入登录 FTP 网站的密码。
7. 填写“[!UICONTROL 数据列定义]”。
   * 在下拉列表中选择最新的“所有Adobe Columns”模板。
   * 压缩格式：Gzip
   * 包装类型：多个文件
   * 清单：无文件
8. 单击右上方的“[!UICONTROL 保存]”。
9. 保存后，即会开始历史数据处理。完成一天的数据处理后，文件会放在 FTP 网站上。
10. 使用 Windows 资源管理器或专用 FTP 客户端登录到 FTP 网站。
11. 将压缩的数据馈送文件下载到本地计算机。
12. 使用支持 `.tar.gz` 文件扩展名的程序解压已压缩文件。
13. 在您选择的电子表格或数据库应用程序中打开 `hit_data.tsv` 文件，以查看当天的原始数据。

## 后续步骤

了解获取数据馈送的基本工作流程后，您可以与组织内的团队合作，将原始数据存储或纳入到数据库中。

* [数据馈送最佳实践](/help/export/analytics-data-feed/data-feeds-best-practices.md)：创建和管理数据馈送的最佳实践。
* [创建数据馈送](create-feed.md)：有关创建数据馈送的技术详细信息，更加详细地阐述各个字段
* [管理数据馈送](df-manage-feeds.md)：了解有关导览数据馈送界面的更多信息
* [数据馈送内容](c-df-contents/datafeeds-contents.md)：了解压缩文件中包含的内容 <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [数据列定义](c-df-contents/datafeeds-reference.md)：所有可用列的完整列表.
* 导览数据馈送界面的视频：

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* 有关如何查找数据馈送 ID 的视频：

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)