---
title: 收入
description: 所有订单中所购产品的货币金额。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---


# 收入

“收入”指标显示所有订单中所购买产品的货币金额。 此指标对于电子商务站点衡量转化率至关重要。 您可以将此指标与任何维度组合，以查看哪些维度项目贡献了收入。 例如，您可以看到顶部活动(使 [用跟踪代码](../dimensions/tracking-code.md) 维)或顶部内部搜索词(使 [用eVar](../dimensions/evar.md))。

## 如何计算此度量

对于变量中 `purchase` 存在的每 [`events`](/help/implement/vars/page-vars/events/event-purchase.md) 次点击，在变量中求和“价格” [`products`](/help/implement/vars/page-vars/products.md) 字段。

如果页面上的货 [币与报表包](/help/implement/vars/config-vars/currencycode.md) 的本机货币不同，则此度量依赖currencyCode变量。
