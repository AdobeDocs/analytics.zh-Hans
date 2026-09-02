---
title: 自定义链接
description: 自定义链接的名称。
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
TQID: https://experienceleague.adobe.com/x4IAGJjozPnLsft1e9xs68L6TNDJbHW0H4Z23p9EDNg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 21%

---

# 自定义链接

“自定义链接”[维度](overview.md)报告您的网站上实施的自定义链接的名称。 对于任何非文件下载或出站导航的交互，自定义链接是一种灵活的跟踪机制。 常见示例包括按钮单击、内部导航或表单交互。 当您想要了解访客在这些交互中与哪个交互的交互次数最多时，此维度很有价值。

## 使用数据填充此维度

此维度根据`pe`查询字符串中的值，从图像请求中的[`pev2`查询字符串](/help/implement/validate/query-parameters.md)收集数据。 `pe`查询字符串确定哪个链接维度接收`pev2`值：

* **自定义链接** （此页面）： `lnk_o`
* **[下载链接](download-link.md)**： `lnk_d`
* **[退出链接](exit-link.md)**： `lnk_e`

如果未提供`pev2`，则将链接URL (`pev1`)用作维度值。 显式提供链接名称时，最大长度为100字节。 从链接URL派生的值不受此限制约束。

要使用AppMeasurement填充此维度，请发送一个链接类型参数为`"o"`的[`tl()`](/help/implement/vars/functions/tl-method.md)图像请求。 将链接名称参数设置为所需的值：

```js
s.tl(true,"o","Example custom link");
```

## 维度项目

由于此变量基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。 Adobe 建议您根据报表需求将链接分组为有意义的类别。 如果未提供链接名称，则维度项目将显示为原始URL。 这些原始URL在报表中更难解释，因此请尽可能提供描述性链接名称。
