---
description: Advertising Analytics 工作流程概述。
title: 工作流程概述
feature: Advertising Analytics
exl-id: 00993c19-1e74-4a97-b16a-967feab13b32
TQID: 'https://experienceleague.adobe.com/Xrm-gn59uSRzBKtwY1Z6O40b7d0MS-LH-Y96hLjbJKQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: fe0a7292-80bc-407a-b456-64170267d1cc
    internal-label: Advertising integration
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
    internal-label: Advertising Analytics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 42%
---
# 工作流程概述

配置Advertising Analytics的工作流包含以下步骤：

<!--
>[!VIDEO](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/integrations/ad-cloud/configuring-advertising-analytics)
-->

1. [为每个报表包启用 Advertising Analytics 报告功能](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)。 为启用了 Experience Cloud 的报表包启用 [!UICONTROL Advertising Analytics] 报告。
2. [设置 Advertising Analytics 帐户](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)。 在 Analytics 管理员工具中进行设置。
3. [在 Analytics 中报告广告数据](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md)。 您所在Adobe Analytics数据中心时区的上午6点(06:00)左右，系统会从搜索引擎中提取搜索数据。 Adobe Advertising数据会被收集并插入到报表包中。 然后在将数据插入Analytics的过程中转换为报表包时区。 报表在Analysis Workspace（付费搜索性能模板）、Report Builder和Analytics报表API中可用。
4. [管理广告帐户](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md)。 您可以检查帐户状态，以及编辑/暂停帐户。
