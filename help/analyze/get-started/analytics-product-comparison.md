---
description: Analysis Workspace、Report Builder、Data Warehouse 和 Data Workbench 的系统要求和比较
title: Analytics 产品比较和要求
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
TQID: https://experienceleague.adobe.com/VQgK6DUSlz-UA3zk-Q18-QOAI5M6xfK7KqBYwW56j6w
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: af53ada8-1b7d-4929-ac91-ac971dd20ec7
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e9cb007b-c8b7-4975-bc81-11a788c535fa
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 67%

---

# Analytics 产品比较和要求

此页面包含各种 Adobe Analytics 产品的比较：Analysis Workspace、Report Builder、Data Warehouse、数据馈送和 Analytics API 2.0。

有关使用哪种 Adobe Analytics 产品的信息，请参阅[我应该使用哪种 Adobe Analytics 工具？](/help/analyze/get-started/which-analytics-tool.md)。

| 产品名称和帮助链接 | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [数据馈送](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **访问方法** | [浏览器](/help/analyze/get-started/sys-reqs.md) | [Windows 版 MS Excel](/help/analyze/legacy-report-builder/setup/system-requirements.md) | 通过浏览器进行安装。 [了解详情](/help/analyze/get-started/sys-reqs.md) | 通过浏览器进行安装。 [了解详情](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API 工具。 使用 Adobe Developer 凭据登录。 [了解详情](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **数据粒度** | 汇总 | 汇总 | 汇总 | 点击 | 汇总 |
| **Experience Cloud ID (ECID) 可用** | 否 | 否 | 是 | 是 | 否 |
| **时间戳可用** | 否 | 否 | 否 | 是 | 否 |
| **处理级别** | 完全处理 | 完全处理，具有单独的[实时报告](/help/admin/tools/manage-rs/edit-settings/realtime/realtime.md) | 完全处理 | 完全处理 | 完全处理 |
| **包含管理员机器人过滤器数据**<br> [了解详情](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) | 否 | 是 - 单独的机器人报告 | 否 | 否 | 否 |
| **显示低流量（超出唯一值）**<br> [了解详情](/help/technotes/low-traffic.md) | 是 | 是 | 否 | 否 | 是 |
| **可见的行限制（分页前）** | 400 | 50000 | 无限制 | 无限制 | 50000 |
| **多个报告包** | [是](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | 是 | 否 | 是 | 否 |
| **划分数** | 无限制 | 最高 2 | 无限制 | 无限制 | 无限制，跨多个查询运行 |
| **区段划分** <br> [了解详情](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | 是 | 是 | 是，具有[限制](/help/export/data-warehouse/segment-compatibility.md) | 否 | 是 |
| **计算指标** <br> [了解详情](/help/components/calculated-metrics/cm-overview.md) | 是，具有[归因](/help/analyze/analysis-workspace/attribution/overview.md) | 是，具有归因 | 是 | 否 | 是，具有[归因](/help/analyze/analysis-workspace/attribution/overview.md) |
| **营销渠道** <br> [了解详情](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | 是 | 是 | 是 | 是 - [va_finder、va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | 是 |
| **同类群组分析** | [是](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 是 | 否 | 否 | 否 |
| **归因** | 是，具有[归因](/help/analyze/analysis-workspace/attribution/overview.md) | 有限制 | 否 | 否 | 是，具有[归因](/help/analyze/analysis-workspace/attribution/overview.md) |
| **策划**<br> [了解详情](/help/analyze/analysis-workspace/curate-share/curate.md) | 是 - 项目和虚拟报告包 | 否 | 否 | 否 | 是 - 仅限虚拟报告包 |
| **项目共享**<br> [了解详情](/help/analyze/analysis-workspace/curate-share/share-projects.md) | 是，具有项目角色 | 是 | 否 | 否 | 否 |
| **计划提交** | 是 | 是 | 是 | 是 | 否 |
| **提交目标** | 电子邮件 | 电子邮件、FTP、SFTP、[发布到 Microsoft PowerBI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3、Google Cloud Platform、Azure SAS、Azure RBAC 和电子邮件 | Amazon S3、Azure RBAC、Azure SAS 和 Google Cloud Platform | - |
| **虚拟报告包报告时间处理**<br> [了解详情](/help/components/vrs/vrs-report-time-processing.md) | 是 | 否 | 否 | 否 | 是 |
| **地理和技术报表** | 是 <p>使用中间值而不是post字段。 访问首次点击逻辑基于`post_cust_hit_time_gmt`而不是`visit_page_num=1`。 如果IP在访问期间更改、点击无序到达或访问跨越月份边界，则结果可能与其他工具不同。</p> | 是 <p>使用中间值而不是post字段。 访问首次点击逻辑基于`post_cust_hit_time_gmt`而不是`visit_page_num=1`。 如果IP在访问期间更改、点击无序到达或访问跨越月份边界，则结果可能与其他工具不同。</p> | 是 <p>使用post值和`visit_page_num=1`确定访问的首次点击。 将第一次点击的值应用于这些维度在访问中的所有点击。</p> | 是 <p>使用post值和`visit_page_num=1`确定访问的首次点击。 将第一次点击的值应用于这些维度在访问中的所有点击。</p> | 是 <p>使用中间值而不是post字段。 访问首次点击逻辑基于`post_cust_hit_time_gmt`而不是`visit_page_num=1`。 如果IP在访问期间更改、点击无序到达或访问跨越月份边界，则结果可能与其他工具不同。</p> |
