---
title: 点击类型
description: 确定点击是前台还是后台点击。
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c77ba355-6681-41fe-b719-563d3f507fdbid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 84%

---

# 点击类型

“点击类型”[维度](overview.md)可确定将点击发送到Adobe数据收集服务器时，移动设备应用程序是处于前台还是后台。 此维度仅与包含移动设备应用程序数据的报表包相关。 通过 AppMeasurement 收集的浏览器数据始终将点击报告为“前台”。

## 使用数据填充此维度

此维度可开箱即用于版本 4.13.6 或更高版本上的所有 Mobile SDK 实施。 如果您不使用 Mobile SDK，则所有点击均列在“前台”维度项目下。 如果选中“禁用计算后台点击量的旧版报告和归因”，则后台点击量将仅显示在[虚拟报表包](../vrs/vrs-mobile-visit-processing.md)中。

## 维度项目

维度项目包括 `"Foreground"` 和 `"Background"`。 不是在移动设备应用程序后台发送的任何点击属于 `"Foreground"` 维度项目。 在移动设备应用程序处于后台时发送的任何点击属于 `"Background"` 维度项目。
