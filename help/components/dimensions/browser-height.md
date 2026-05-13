---
title: 浏览器高度 - 分段统计
description: 以像素为单位的浏览器窗口的高度。
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 273
ht-degree: 87%

---

# 浏览器高度

“浏览器高度 — 分段统计”维度[维度](overview.md)显示浏览器窗口的高度，并将其归类到预定义的组中。 当您想要了解网站上的“折”对访客的位置时，此维度很有用。 了解折的位置可让您优化内容以便于查看。

此维度与屏幕高度不同。 浏览器高度是可查看的浏览器空间中的像素数，而屏幕高度是以像素为单位的整个显示器的高度。 如果您想在自己的计算机上查看这两个变量之间的差异，请打开浏览器控制台（在大多数浏览器上是按 F12），然后将以下代码复制并粘贴到控制台中：

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

浏览器高度始终小于或等于屏幕高度，因为浏览器高度不包括浏览器导航或边框。

## 使用数据填充此维度

此维度从图像请求中的 [`bh` 查询字符串](/help/implement/validate/query-parameters.md)检索数据。 AppMeasurement 使用浏览器中的 JavaScript 变量 `window.innerHeight` 收集此数据。 如果您使用 AppMeasurement 库（例如，通过 Adobe Experience Platform 中的标记），则此维度可开箱即用。 如果您使用非 AppMeasurement 的数据收集方法（例如通过 API），请确保在每个访问的首次点击时包含 `bh` 查询字符串参数。

Adobe 会在访问期间保持浏览器高度。 如果在访问中调整了浏览器高度，则不会记录此调整。

## 维度项目

Dimension项目包括所有收集的浏览器高度，它们被分类为预定义的组。 例如，如果点击的浏览器高度为 `720`，则会将其分组到维度项目 `700 to 799`。
