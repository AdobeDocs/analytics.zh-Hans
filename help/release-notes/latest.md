---
title: 当前 Adobe Analytics 发行说明
description: 查看当前 Adobe Analytics 发行说明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2: id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8bfb44d4eeb1812ec9b91a68bd37c2b660eae76e
workflow-type: tm+mt
source-wordcount: 573
ht-degree: 91%

---

# 当前 Adobe Analytics 发行说明（2026 年 5 月）

**上次更新时间**：2026年6月22日

这些发行说明涵盖2026年6月发行期。 Adobe Analytics 发布采用[持续交付模型](releases.md)，这样即可用一种更具可扩展性、分阶段的方法部署各项功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或增强功能 {#features}

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ---- |
| **Adobe Analytics 中的历程画布** <br/>历程画布是 Analysis Workspace 中的一种可视化工具，它通过分析人们如何完成或退出某个已定义的用户历程，帮助您深入了解这个历程。 它允许您创建灵活的节点和箭头图，用于表示历程中包含的各种事件、维度项和区段的任意组合。 当您将节点拖到画布上或重新排列历程中的事件和条件时，数据就会更新。<p>历程画布以前仅适用于 Customer Journey Analytics。</p><p>要了解有关 Adobe Analytics 中的历程画布的更多信息，请参阅[历程画布概述](/help/analyze/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)。 </p><p>要了解如何构建 Adobe Analytics 中的可视化历程画布，请参阅[配置历程画布](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。</p> | 2026 年 5 月 18 日 | 2026 年 6 月 5 日 |

### Adobe Analytics 中的修复

**Activity Map**：
**Analysis Workspace**： AN-452009、AN-450375、AN-449870、AN-450814、AN-450698
**分类**：
**数据馈送和Data Warehouse**：
**迁移**：
**导出**：
**Report Builder**： AN-440912
**报告**： AN-423516
**报表包**： AN-455684
**计划报告**：
**分段**：
**其他**：


### 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **旧版 Report Builder** | 2025 年 6 月 18 日 | 旧版 Report Builder 插件将于 2026 年 6 月停用。 所有用户都应开始将其旧工作簿升级到[新的 Report Builder](/help/analyze/report-builder/rb-overview.md)。 新的 Report Builder 可供 Adobe Analytics 和 Customer Journey Analytics 客户使用。 它具有[几乎相同的功能](/help/analyze/report-builder/convert-workbooks.md#unsupported)以及许多新的便捷功能和 UI 增强功能。 要促进升级过程，新的 Report Builder 包含一个简单的工作簿转化功能。 新的 Report Builder 仅通过 Microsoft Store 作为插件提供。 许多组织要求在向用户提供加载项之前进行内部审批流程。 请留出时间完成此流程并立即开始与您的组织合作，以确保有足够的时间在 EOL 日期之前升级您的工作簿。 |
| **Adobe Analytics API（版本 1.4）** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 旧版 API 服务将终止使用并关闭，使用这些服务构建的当前集成也将停止工作：<ul><li>Adobe Analytics API（版本 1.4）</li><li>Adobe Analytics WSSE 身份验证</li></ul><p>使用 Adobe Analytics API（版本 1.4）的集成必须迁移到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 集成必须迁移到 [Adobe Developer Console](https://developer.adobe.com/console) 中基于 OAuth 的身份验证协议。</p><p>请参阅  [Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) ，获取常见问题的解答和进一步的指导。</p> |


## AppMeasurement

有关 AppMeasurement 版本的最新更新，请参阅 [AppMeasurement 发行说明](https://github.com/adobe/appmeasurement/releases)。


>[!MORELIKETHIS]
>
>* [以前的2026年发行说明](/help/release-notes/2026.md)
>* [Customer Journey Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
>* [流媒体服务发行说明](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/release-notes/release-notes)
>* [Adobe CX Enterprise 产品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新发布更新
