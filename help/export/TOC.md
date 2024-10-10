---
product: analytics
audience: end-user
user-guide-title: Analytics 导出指南
breadcrumb-title: 导出指南
user-guide-description: 了解如何使用数据馈送导出原始数据以及使用 Data Warehouse 检索数据的电子表格输出形式。了解如何使用 FTP 和 SFTP 传输文件。
source-git-commit: 1e1a26b8595ca026fb049322125a6f91d9d5513c
workflow-type: ht
source-wordcount: '279'
ht-degree: 100%

---


# Adobe Analytics 导出指南 {#export}

+ [Analytics 导出指南](home.md)
+ [Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
+ Analytics 数据馈送 {#analytics-data-feed}
   + [数据馈送概述](analytics-data-feed/data-feed-overview.md)
   + [创建数据馈送](analytics-data-feed/create-feed.md)
   + [管理数据馈送](analytics-data-feed/df-manage-feeds.md)
   + [管理数据馈送作业](analytics-data-feed/df-manage-jobs.md)
   + 数据馈送内容 {#data-feed-contents}
      + [数据馈送内容概述](analytics-data-feed/c-df-contents/datafeeds-contents.md)
      + [计算量度](analytics-data-feed/c-df-contents/datafeeds-calculate.md)
      + [数据列引用](analytics-data-feed/c-df-contents/datafeeds-reference.md)
      + [页面事件查找](analytics-data-feed/c-df-contents/datafeeds-page-event.md)
      + [动态查找](analytics-data-feed/c-df-contents/dynamic-lookups.md)
      + [促销 eVar 查找](analytics-data-feed/c-df-contents/merchandising-evar-lookup.md)
      + [特殊字符](analytics-data-feed/c-df-contents/datafeeds-spec-chars.md)
      + [迟到的点击量](analytics-data-feed/c-df-contents/late-arriving-hits.md)
   + [数据馈送常见问题解答](analytics-data-feed/df-faq.md)
   + [数据馈送最佳实践](analytics-data-feed/data-feeds-best-practices.md)
   + [数据馈送疑难解答](analytics-data-feed/troubleshooting.md)
+ Data Warehouse {#data-warehouse}
   + [Data Warehouse 概述](data-warehouse/data-warehouse.md)
   + [添加 Data Warehouse 用户组](data-warehouse/t-dw-group.md)
   + 创建 Data Warehouse 请求{#dw-create-request}
      + [创建 Data Warehouse 请求](/help/export/data-warehouse/create-request/t-dw-create-request.md)
      + [常规设置](/help/export/data-warehouse/create-request/dw-general-settings.md)
      + [生成您的报告](/help/export/data-warehouse/create-request/dw-request-build-report.md)
      + [报表目标](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
      + [报表选项](/help/export/data-warehouse/create-request/dw-request-report-options.md)
      + [计划选项](/help/export/data-warehouse/create-request/dw-request-scheduling.md)
      + [通知电子邮件](/help/export/data-warehouse/create-request/dw-request-email.md)
   + [请求发送时间](data-warehouse/delivery-time.md)
   + [表格数据文件](data-warehouse/t-tableau.md)
   + [按量度排序](data-warehouse/sorting-by-metric.md)
   + [管理 Data Warehouse 请求](data-warehouse/data-warehouse-requests-manage.md)
   + [Data Warehouse 中支持的组件](data-warehouse/component-support.md)
   + [Data Warehouse 最佳实践](data-warehouse/data-warehouse-bp.md)
+ FTP 和 SFTP {#ftp-and-sftp}
   + [将 FTP 和 SFTP 用于 Adobe Experience Cloud](ftp-and-sftp/ftp-overview.md)
   + 设置 Adobe 托管的 FTP 帐户 {#set-up-ftp-accounts}
      + [设置 FTP 帐户 — 概述](ftp-and-sftp/c-set-up-ftp-accounts/ftp-accounts.md)
      + [分类](ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)
      + [数据源](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)
      + [数据馈送](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)
      + [Data Warehouse 传送的报表](ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)
      + [Report Builder 传送的报表](ftp-and-sftp/c-set-up-ftp-accounts/ftp-arb-reports.md)
      + [通过 FTP 开展工程技术服务工作](ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md)
   + [FTP 限制和数据保留](ftp-and-sftp/ftp-limits.md)
   + [删除 FTP 数据和 FTP 帐户](ftp-and-sftp/ftp-delete.md)
   + [恢复已删除的 FTP 数据和 FTP 帐户](ftp-and-sftp/ftp-restore.md)
   + [升级 Adobe FTP 服务器](ftp-and-sftp/ftp-upgrade.md)
   + [使用被动 FTP 模式](ftp-and-sftp/ftp-passive.md)
   + [FTP 处理时间](ftp-and-sftp/ftp-processing.md)
   + 安全文件传输协议 {#secure-file-transfer-protocol}
      + [SFTP 服务升级 — 常见问题解答](ftp-and-sftp/c-sftp/sftp-upgrade.md)
      + [安全文件传输协议 — 概述](ftp-and-sftp/c-sftp/ftp-sftp.md)
      + [通过 SFTP 连接到 Adobe FTP 帐户](ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
      + [通过 SFTP 将 Adobe 数据发送到外部 FTP 帐户](ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)
      + [将 Data Warehouse 请求发送到 SFTP 服务器](ftp-and-sftp/c-sftp/ftp-sftp-dw.md)
      + [在无密码的情况下通过 SFTP 连接到 Adobe](ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
+ [Analysis Workspace 下载](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=zh-Hans)
+ [Adobe Analytics API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)
+ [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=zh-Hans)
