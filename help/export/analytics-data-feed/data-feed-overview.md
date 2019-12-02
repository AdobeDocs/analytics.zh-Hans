---
description: 在 Adobe Data Warehouse 中可处理和存储从网站、移动应用程序收集，或使用 Web 服务 API 或数据源上载的数据。该原始点击流数据形成 Adobe Analytics 使用的数据集。
keywords: clickstream;data feed;datafeed;Data Feed
solution: Analytics
title: Analytics 数据馈送概述
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Analytics 数据馈送概述

数据馈送是从Adobe Analytics中获取原始数据的强大方式。 此原始数据可在Adobe以外的其他平台中使用，由您的组织自行决定。 数据在每小时结束时以每小时的批次发送，或在每天结束时以每日的批次发送。

## 先决条件

在使用数据源之前，请确保满足以下所有要求。

* 方便地使用FTP站点和凭据。 数据馈送只能发送到服务器目标。 您的组织通常提供FTP凭据。 Adobe可以根据您的请求为FTP位置提供少量存储。 联系客户关怀以请求数据馈送的FTP目标。
* 向Adobe数据收集服务器发送数据的有效实施。 请参 [阅实施用户指南中的启动项](../../implement/implement-with-launch/validate-publish-prod.md) ，验证和发布实施。
* 您的帐户是Analytics产品管理员，或您的帐户属于有权访问数据馈送的产品配置。

## 入门步骤

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
3. 在顶部导航栏中，导航到管理员&gt;数据源。
4. 单击[!UICONTROL 添加]。将显示一个新页面，其中包括三个主要类别：源信 [!UICONTROL 息]、 [!UICONTROL 目标]和 [!UICONTROL 数据列定义]。
5. 填写“信 [!UICONTROL 息源信息] ”字段。
   * 名称：任何所需的名称，如“测试数据源”。
   * 报告套件：选择所需的报表包。
   * 完成时发送电子邮件：输入您的电子邮件。
   * 源间隔：选择所需的间隔（每小时或每天）。
   * 延迟处理：可保留为“无 [!UICONTROL 延迟”]。
   * 开始和结束日期：选择开始日期（从几天前到今天）作为结束日期。
6. 填写“目 [!UICONTROL 标] ”字段。
   * 类型：FTP
   * 主持人：输入所需的FTP目标URL。 例如：`ftp://ftp.omniture.com`。
   * 路径：可留空
   * 用户名：输入用户名以登录FTP站点。
   * 密码和确认密码：输入登录FTP站点的口令。
7. 填写数 [!UICONTROL 据列定义]。
   * 在下拉菜单中选择最新的“所有Adobe列”模板。
   * 压缩格式：Gzip
   * 打包类型：多个文件
   * 清单：无文件
8. 单击 [!UICONTROL 右上] “保存”。
9. 保存后，历史数据处理即开始。 数据完成一天的处理后，文件会放在FTP站点上。
10. 使用Windows资源管理器或专用FTP客户端登录到FTP站点。
11. 将压缩的数据馈送文件下载到本地计算机。
12. 使用支持文件扩展名的程序解压缩压 `.tar.gz` 缩文件。
13. 在您选 `hit_data.tsv` 择的电子表格或数据库应用程序中打开文件，查看当天的原始数据。

## 后续步骤

了解获取数据馈送的基本工作流程后，您可以与组织内的团队合作，将原始数据存储或摄取到数据库中。

[创建数据源](create-feed.md):有关创建数据源的技术详细信息，请详细说明各个字段[管理数据源](df-manage-feeds.md):了解有关导航数据馈送界面的更多信息[数据馈送内容](c-df-contents/datafeeds-contents.md):了解压缩文件“数据”列定义[中包含的内容](c-df-contents/datafeeds-reference.md):所有可用列的完整列表

## 其他资源

导航数据馈送界面的视频：

> [!VIDEO](https://www.youtube.com/watch?v=m_fb--gNtR4)
