---
title: 点击类型
description: 确定点击是前台还是后台点击。
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: 'https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
    internal-label: Mobile SDK
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 31%
---
# 点击类型

“点击类型”[维度](overview.md)可确定将点击发送到Adobe数据收集服务器时，移动设备应用程序是处于前台还是后台。 此维度仅与包含移动应用程序数据的报告包相关。 通过AppMeasurement收集的浏览器数据始终将点击报告为`"Foreground"`。

## 使用数据填充此维度

移动设备SDK设置[`customerPerspective`](/help/implement/vars/page-vars/customerperspective.md)变量以指示每次点击是在前台还是后台发生。 此维度可开箱即用于版本 4.13.6 或更高版本上的所有 Mobile SDK 实施。 如果您不使用移动设备SDK，则所有点击都将列在`"Foreground"`下。 如果在配置[虚拟报表包](../vrs/vrs-mobile-visit-processing.md)时选择了&#x200B;**[!UICONTROL 避免将后台点击计算为一次新的访问]**，则后台点击不会使[[!UICONTROL 访问]](../metrics/visits.md)和[[!UICONTROL 独特访客]](../metrics/unique-visitors.md)虚增。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | [`customerPerspective`](/help/implement/vars/page-vars/customerperspective.md) |
| **Web SDK / XDM字段** | 无 |
| **查询参数** | [`cp`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<customerPerspective>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 不适用 |
| **持久性** | 不适用 |

## 维度项目

维度项目包括 `"Foreground"` 和 `"Background"`。 后台点击仅发生在跟踪的应用程序处于后台的移动设备上。
