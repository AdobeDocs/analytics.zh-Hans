---
title: 平均页面深度
description: 维度一般存在于多少个页面上。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 59%

---


# 平均页面深度

“平均页面深度”度量显示维度项目在给定访问中的距离。 例如，您的主页通常显示的平均页面深度比购买确认页面浅，后者通常在访问时会更深。当您想要了解给定维度项目中平均有多少页时，此度量非常有用。 如果页面平均深度较浅，则可以使用此信息来优化特定页面，以吸引新访客。

>[提示]：将此量度与其他量度（例如[访问次数](visits.md)）结合使用，可获得更优质的洞察信息。如果您自己使用此度量，您会得到包含异常页面深度的维度项目，这通常不值钱。

## 如何计算此量度

访问的第一个页面的页面深度为 `0`。下一页的页面深度为 1，并随着页面查看的深入而增加，直到访问结束。此量度会随着页面查看 ([`t()`](/help/implement/vars/functions/t-method.md)) 调用而增加，而不是随着链接跟踪 ([`tl()`](/help/implement/vars/functions/tl-method.md)) 调用而增加。

对于给定的维度项目，为该维度项目添加所有页面深度，并按访问量将其除以。 结果数字即为平均页面深度，四舍五入到最接近的整数。Dimension items with an average page depth of `0` means it was frequently on the first page of the visit.

例如，请考虑以下示例访问：

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

If we wanted average page depth for the dimension item `Page2`, it would be calculated as follows:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>如果要了解保留小数位的平均页面深度，请使用此量度作为公式中的唯一元素创建一个计算量度。将计算度量中的小数位数增加到所需的小数。

## 百分比高于 100%

此量度通常包含高于 100% 的百分比。分母是整个维的平均页面深度，分子是维项的平均页面深度。 如果整个维度的平均页面深度低于给定维度项目的平均页面深度，您将看到高于100%的百分比。 按此量度对排名报表进行排序，会显示网站平均深度的异常值，该值通常没什么价值。Adobe 建议在排名报表中按其他量度（例如[访问次数](visits.md)）来排序。