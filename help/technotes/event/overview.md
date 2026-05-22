---
title: 分析受事件影响的数据
description: 了解受事件影响的数据会如何影响整体数据质量。
exl-id: 8d81a432-42d6-4f5d-b66a-bb3af7fc4857
feature: Curate and Share
TQID: https://experienceleague.adobe.com/DJoJwtp9CkgrCfA1DwW8rKX2x3ssfzLCo7vCfhdLusg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 404
ht-degree: 91%

---

# 分析受事件影响的数据

有时，某个事件可能会影响组织中的数据质量。 示例包括：

* 机器人发送异常数据，例如数百万美元的收入
* 贵组织向您的网站推送更新，该更新对您的 Analytics 实施产生负面影响
* 影响数据质量或完整性的其他问题

如果您的网站遇到任何类型的数据质量问题，您可能希望将此类数据从报表中排除，以防止根据这些数据做出业务决策。 可运用这些部分的内容来衡量事件对数据的影响，并确定后续操作方式。

## 确定事件原因

如果您不确定为什么会出现数据激增或骤减，请参阅[数据激增/骤减故障诊断](spikes-drops.md)。

## 使用分段分析和排除数据

Adobe Analytics 提供了一种简单可靠的方法，来使用分段重点关注或排除数据。 您可以使用区段中的“日期范围”维度过滤掉或重点关注那些特定日期。 请参阅[在分析中排除特定日期](segments.md)。

## 比较事件与先前的日期范围

如果您想要了解更多有关事件在一段时间内对数据有何影响的信息，可以使用 Analysis Workspace 中的日期比较。 利用此功能，您可以逐日、逐周或逐月比较数据，了解数据与先前范围的对比情况。 然后，您可以使用此比较信息来确定事件对趋势的影响程度。 请参阅[比较受事件影响的日期与先前的日期范围](compare-dates.md)。

## 使用计算量度获取数据

创建区段并使用日期比较后，您可以结合这两个概念，使用计算量度来更正趋势数据。 将区段包含在计算量度中，然后将受影响的天数乘以比较日期时得出的偏移量。 请参阅[获取受事件影响的数据](calcmetrics.md)。

## 将影响告知组织中的用户

准备好处理事件的方式后，您便可以[将影响告知组织中的用户](communicate.md)。 Adobe 在 Analytics 中提供了多个位置供您放置文本，以便将发生的事件和可使用的组件告知用户。

## 视频

>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [分析和传输数据中的变体](https://video.tv.adobe.com/v/33316?quality=12&learn=on){target="_blank"}。

* **0:27**：使用分段排除数据
* **2:55**：将事件与先前的范围进行比较
* **8:42**：使用计算量度获取数据
* **11:46**：将影响告知用户

>[!ENDSHADEBOX]


