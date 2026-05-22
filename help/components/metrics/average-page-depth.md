---
title: 平均页面深度
description: 维度一般存在于多少个页面上。
feature: Metrics
exl-id: 6625405a-bda5-4723-8d22-4bc5b7e44d4e
TQID: https://experienceleague.adobe.com/Pm2WxRPqn9M-7IdrFQ2Tkj9t-L8ug3nZGr6ncpZg7lg
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
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 365
ht-degree: 55%

---

# 平均页面深度

“平均页面深度”[量度](overview.md)显示维度项目平均延伸到给定访问中的深度。 例如，主页（页面维度的维度项目）显示的平均页面深度通常比购买确认页面浅，后者可能会进一步扩展到访问中。 如果页面平均深度较浅，则可以使用此信息来优化特定页面，以吸引新访客。

>[!TIP]
>
>将此量度与其他量度（如[访问次数](visits.md)）一起使用以获取更好的见解。 如果您单独使用此量度，则可能会获得包含异常页面深度的维度项目，该维度项目通常不是很有价值的insight。

## 如何计算此指标

访问的第一个页面的页面深度为 `0`。 下一页的页面深度为 1，并随着页面查看的深入而增加，直到访问结束。 此量度只随着页面查看([`t()`](/help/implement/vars/functions/t-method.md))调用而增加，而不会随着链接跟踪([`tl()`](/help/implement/vars/functions/tl-method.md))调用而增加。

对于给定的维度项目，为该维度项目添加所有页面深度，然后除以访问量。 结果数字即为平均页面深度，四舍五入到最接近的整数。 如果维度项目的平均页面深度为 `0`，则意味着它经常出现在访问的第一个页面。

例如，请考虑以下示例访问：

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

如果我们想要了解维度项目 `Page2` 的平均页面深度，其计算方式如下：

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>如果要了解保留小数位的平均页面深度，请使用此指标作为公式中的唯一元素创建一个计算指标。 将计算指标中的小数位数增加到所需的小数。

## 百分比高于 100%

此指标通常包含高于 100% 的百分比。 分母是整个维度的平均页面深度，分子是维度项目的平均页面深度。

如果整个维度的平均页面深度低于给定维度项目的平均页面深度，您将看到高于100%的百分比。 按此指标对排名报表进行排序，会显示网站平均深度的异常值，该值通常没什么价值。 Adobe 建议在排名报表中按其他量度（例如[访问次数](visits.md)）来排序。
