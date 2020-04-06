---
description: 参与率量度将成功事件的全部信用分配给访问期间传递的所有 eVar 值。参与量度有助于确定哪些页面、活动或其他自定义变量值对网站成功的贡献最大。 参与基于访问。 在事件发生之前（包括点击时）的访问中的所有eVar值都会收到参与信用，而不管过期设置如何。
title: 参与率
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 参与率

参与率量度将成功事件的全部信用分配给访问期间传递的所有 eVar 值。参与量度有助于确定哪些页面、活动或其他自定义变量值对网站成功的贡献最大。 参与基于访问。 在事件发生之前（包括点击时）的访问中的所有eVar值都会收到参与信用，而不管过期设置如何。

请参阅[访客参与 - Ad Hoc Analysis](/help/components/c-variables/c-metrics/metrics-visitor-participation.md)，了解 Ad Hoc Analysis 如何使用参与率的详细信息。

参与量度对于每个转化事件有两个设置：

* **禁用**:每个转换事件的默认状态。 不会为此事件收集参与数据。
* **已启用**:会收集此事件的参与数据。

>[!NOTE] 您最多可以为 100 个自定义事件启用参与率。除此之外，您还可以在[计算量度](https://marketing.adobe.com/resources/help/zh_CN/analytics/calcmetrics/participation_metric.html)生成器中创建参与率量度。

启用后，参与量度将自动在所有转化报告中可用。 但是，也可以根据您的请求在特定流量报告中查看参与率指标。 您可以选择请求某些自定义流量报告中提供的参与量度。

## 收入参与示例 {#section_DAB6C348201B454BB4ED01313AA777AF}

假定以下序列：

1. 用户导航到您的站点并搜索“shoes”。
1. 然后，用户搜索“网球鞋”。
1. 用户单击产品页面的链接，将物品添加到购物车，并购买120美元。

在“内部搜索词报表”中显示收入时，您会根据选定的分配看到以下内容：

* **第一**:“鞋子”将获得120美元的信用。 “网球鞋”可以拿到0美元。
* **最后**:“网球鞋”将获得120美元的奖励。 “鞋子”可以拿到0美元。
* **线性**:每个活动将获得60美元的信用。

   参与与线性分配类似，只是所有值都会获得完全信用。 如果您使用收入（参与）作为度量，则忽略分配。 此示例中的收入（参与）将报告两个搜索词的$120。

>[!MORELIKETHIS]
>
>* [量度计算](/help/components/c-variables/c-metrics/metrics-calculations.md)

