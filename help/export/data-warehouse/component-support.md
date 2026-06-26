---
title: Data Warehouse中的组件支持
description: 了解在构建Data Warehouse请求时哪些维度和量度可用、哪些维度和量度不可用，以及哪些维度和量度的行为方式不同。
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
TQID: https://experienceleague.adobe.com/NhSEyPN3093B9M0SngJluJdZScI2lXvRyHkXQd8gg-4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 11%

---

# Data Warehouse 中的组件支持

本页介绍在构建Data Warehouse请求时可以使用的维度和量度。 部分包含哪些组件可用、哪些组件不可用，以及哪些组件的行为与其他Adobe Analytics工具中的行为不同。

## Data Warehouse专有的维度

以下维度可以在Data Warehouse中使用，但在其他Adobe Analytics功能中不可用。

* [[!UICONTROL Experience Cloud访客ID]](/help/components/dimensions/experience-cloud-visitor-id.md)
* [[!UICONTROL IP地址]](/help/components/dimensions/ip-address.md)
* [[!UICONTROL 页面 URL]](/help/components/dimensions/page-url.md)
* [[!UICONTROL 购买ID]](/help/components/dimensions/purchase-id.md)
* [[!UICONTROL 访客 ID]](/help/components/dimensions/visitor-id.md)

## 不支持的维度

以下维度在Data Warehouse报表或区段中不可用：

* [[!UICONTROL 上午/下午]](/help/components/dimensions/am-pm.md)
* 除[[!UICONTROL 登录页面]](/help/components/dimensions/entry-dimensions.md)和[[!UICONTROL 原始登录页面]](/help/components/dimensions/entry-dimensions.md)之外允许的所有登录维度
* 除允许的[[!UICONTROL 退出页面]](/help/components/dimensions/exit-dimensions.md)和[[!UICONTROL 退出链接]](/help/components/dimensions/exit-link.md)之外的所有退出维度
* [[!UICONTROL 点击深度]](/help/components/dimensions/hit-depth.md)
* [[!UICONTROL 回访频率]](/help/components/dimensions/return-frequency.md)
* [[!UICONTROL 发生事件之前逗留的时间]](/help/components/dimensions/time-prior-to-event.md)
* [[!UICONTROL 页面逗留时间 — 分段统计]](/help/components/dimensions/time-spent-on-page.md)
* [[!UICONTROL 每次访问逗留时间 — 分段统计]](/help/components/dimensions/time-spent-per-visit.md)
* [[!UICONTROL 所有搜索页面排名]](/help/components/dimensions/all-search-page-rank.md)
* [[!UICONTROL 层次结构]](/help/components/dimensions/overview.md#retired-dimensions)变量
* [[!UICONTROL 点击类型]](/help/components/dimensions/hit-type.md)
* [[!UICONTROL 付费搜索]](/help/components/dimensions/paid-search.md)
* [[!UICONTROL 单页面访问量]](/help/components/dimensions/single-page-visits.md)
* [[!UICONTROL 跟踪选择退出的原因]](/help/components/dimensions/tracking-opt-out-reason.md)
* [[!UICONTROL 美国各州]](/help/components/dimensions/us-states.md)

某些维度在Data Warehouse请求中可用，但无法在区段中使用。 有关详细信息，请参阅[Data Warehouse区段兼容性](segment-compatibility.md)。

## 具有非标准日期格式的维度

Data Warehouse报表支持以下基于时间的维度，但其输出使用非标准格式：

* [[!UICONTROL 年]](/help/components/dimensions/year.md)
* [[!UICONTROL 季度]](/help/components/dimensions/quarter.md)
* [[!UICONTROL 月]](/help/components/dimensions/month.md)
* [[!UICONTROL 周]](/help/components/dimensions/week.md)
* [[!UICONTROL 日]](/help/components/dimensions/day.md)
* [[!UICONTROL 小时]](/help/components/dimensions/hour.md)
* [[!UICONTROL 分钟]](/help/components/dimensions/minute.md)

日期值以`1YYMMDDHHMM`格式输出：

* **年(YY)**：由1900偏移。 将`1900`添加到前三位。 例如，`125` =年&#x200B;**2025**。
* **月**：从零开始。 一月= `00`，二月= `01`， ...，十二月= `11`。

例如，如果“日期范围周”字段显示`1260901`，则年份为1900 + 126 = **2026**，而月份为09 = **10月**。

## Data Warehouse中定义不同的量度

* **[[!UICONTROL 访问次数]](/help/components/metrics/visits.md)**：不包括非永久性Cookie访问次数，这与其他Adobe Analytics工具中的“访问次数”量度不同。
* **[[!UICONTROL 访问 — 所有访客]](/help/components/metrics/visits.md)**：计算所有访客，包括那些具有非永久性Cookie的访客，使其更接近Adobe Analytics其他位置使用的标准[!UICONTROL 访问]指标。

## 不支持的指标

以下指标在Data Warehouse中不可用：

* [[!UICONTROL 退回]](/help/components/metrics/bounces.md)
* [[!UICONTROL 登录]](/help/components/metrics/entries.md)
* [[!UICONTROL 退出]](/help/components/metrics/exits.md)
* [[!UICONTROL 重新载入]](/help/components/metrics/reloads.md)
* [[!UICONTROL 单次存取]](/help/components/metrics/single-access.md)
* 任何[[!UICONTROL 逗留时间]](/help/components/metrics/time-spent.md)指标
* 任何使用[参与率](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md)归因模型的量度
