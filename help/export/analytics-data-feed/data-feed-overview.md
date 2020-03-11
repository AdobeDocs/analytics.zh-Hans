---
description: 在 Adobe Data Warehouse 中可处理和存储从网站、移动应用程序收集，或使用 Web 服务 API 或数据源上载的数据。该原始点击流数据形成 Adobe Analytics 使用的数据集。
keywords: clickstream;data feed;datafeed;Data Feed
title: Analytics 数据馈送概述
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
translation-type: ht
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Analytics 数据馈送概述

数据馈送是从 Adobe Analytics 中获取原始数据的有效方法。此原始数据可在 Adobe 以外的其他平台中使用，具体所用平台由您的组织自行决定。数据在每小时结束时以小时为单位分批发送，或者在每天结束时以天为单位分批发送。

## 先决条件

在使用数据馈送之前，请确保您满足以下所有要求。

* 有可用的 FTP 网站和凭据。数据馈送只能发送到服务器目标。您的组织通常会提供 FTP 凭据。Adobe 可以根据您的请求为 FTP 位置提供少量存储空间。联系客户关怀团队以请求获取数据馈送的 FTP 目标。
* 将数据发送到 Adobe 数据收集服务器的有效实施。请参阅实施用户指南中的[在 Launch 中验证和发布实施](/help/implement/launch/validate-publish-prod.md)。
* 您的帐户是 Analytics 产品管理员，或者属于有权访问数据馈送的产品配置文件。

## 入门步骤

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
3. 在顶部导航栏中，导航到“管理员”>“数据馈送”。
4. 单击[!UICONTROL 添加]。此时将显示一个新页面，该页面具有三个主要类别：“[!UICONTROL 馈送信息]”、“[!UICONTROL 目标]”和“[!UICONTROL 数据列定义]”。
5. 填写“[!UICONTROL 馈送信息]”字段。
   * 名称：任何所需的名称，如“测试数据馈送”。
   * 报表包：选择所需的报表包。
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
   * 在下拉菜单中选择最新的“所有 Adobe 列”模板。
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

* [创建数据馈送](create-feed.md)：有关创建数据馈送的技术详细信息，更加详细地阐述各个字段
* [管理数据馈送](df-manage-feeds.md)：了解有关导览数据馈送界面的更多信息
* [数据馈送内容](c-df-contents/datafeeds-contents.md)：了解压缩文件中包含的内容
* [数据列定义](c-df-contents/datafeeds-reference.md)：所有可用列的完整列表

## 其他资源

导览数据馈送界面的视频：

> [!VIDEO](https://www.youtube.com/watch?v=m_fb--gNtR4)
