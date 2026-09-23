---
title: 退出链接
description: 退出链接的名称。
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
TQID: https://experienceleague.adobe.com/lGKBkR5e2arJxGmfIE4qN84oGtYJ2zkfn6luqxEUJ-w
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 22%
---
# 退出链接

“退出链接”[维度](overview.md)报告您的网站上实施的退出链接的名称。 退出链接跟踪将访客导航离开当前域的出站点击。 当您想要了解哪些出站链接的点击频率最高时，此维度很有价值。

## 使用数据填充此维度

此维度由[链接跟踪调用(`tl()`)](/help/implement/vars/functions/tl-method.md)填充。 没有要设置的专用变量。 请改为发送链接类型参数为`"e"`的`tl()`图像请求，并将链接名称参数设置为所需的值。 `pe`查询字符串将链接名称路由到正确的链接维度（[自定义链接](custom-link.md)的`lnk_o`、[下载链接](download-link.md)的`lnk_d`和[退出链接](exit-link.md)的`lnk_e`）。 如果未提供链接名称，则将使用链接URL作为维度值，并且URL派生的值不受字节限制的约束。

```js
s.tl(true,"e","Example exit link");
```

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | [`tl()`](/help/implement/vars/functions/tl-method.md) |
| **Web SDK / XDM字段** | 无 |
| **查询参数** | [`pev2`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML标记** | [`<linkName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **字节限制** | 100字节 |
| **持久性** | 点击 |

## 维度项目

由于此变量基于实施中的自定义字符串，因此，由您的组织来确定这些维度项目。 Adobe 建议您根据报表需求将链接分组为有意义的类别。 如果未提供链接名称，则维度项目将显示为原始URL。 这些原始URL在报表中更难解释，因此请尽可能提供描述性链接名称。
