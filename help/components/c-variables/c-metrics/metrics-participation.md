---
description: 参与率量度将成功事件的所有点数分配给访问期间传递的所有 eVar 值。参与率量度可帮助确定哪些页面、促销活动或其他自定义变量值对站点的成功贡献最大。参与率是基于访问的。当事件发生时，点击之前以及包含此点击的访问的所有 eVar 值均会收到参与率信用，无论过期设置如何。
seo-description: 参与率量度将成功事件的全部信用分配给访问期间传递的所有 eVar 值。参与率量度可帮助确定哪些页面、促销活动或其他自定义变量值对站点的成功贡献最大。参与率是基于访问的。当事件发生时，点击之前以及包含此点击的访问的所有 eVar 值均会收到参与率信用，无论过期设置如何。
seo-title: 参与度
solution: Analytics
title: 参与度
topic: 量度
uuid: a7fa791d -a77-429e-808e-4f97bb9ae5fc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 参与率

参与率量度将成功事件的全部信用分配给访问期间传递的所有 eVar 值。参与率量度可帮助确定哪些页面、促销活动或其他自定义变量值对站点的成功贡献最大。参与率是基于访问的。当事件发生时，点击之前以及包含此点击的访问的所有 eVar 值均会收到参与率信用，无论过期设置如何。

See [Visitor Participation - Ad Hoc Analysis](../../../components/c-variables/c-metrics/metrics-visitor-participation.md#concept_ACBAE3626B224D9683257B5F73E0FB4A) for more information about how Ad Hoc Analysis uses participation.

对于参与率量度，每个转化事件均有两个设置：

* **禁用**：每个转化事件的默认状态。将不收集此事件的参与率数据。
* **启用**：收集此事件的参与率数据。

>[!NOTE]
>
>最多可为100个自定义事件启用参与。除此之外，您还可以在[计算量度](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/participation_metric.html)生成器中创建参与率量度。

启用后，参与率量度即在所有转化报表中自动提供。但是，参与率量度也可根据您的请求在特定流量报表中查看。您可以选择性地请求在某些自定义流量报表中提供参与率量度。

## 收入参与率示例 {#section_DAB6C348201B454BB4ED01313AA777AF}

假设以下顺序：

1. 用户导航到您的网站并搜索“鞋”。
1. 然后用户搜索“网球鞋”。
1. 用户点击到产品页面的链接，将项目添加到购物车，并完成 120 美元的购买。

当在“内部搜索词报表”中显示“收入”时，根据选择的分配方案，您将看到如下内容：

* **首个**：“鞋”将获得 120 美元的信用。“网球鞋”将获得 0 美元的信用。
* **最近**：“网球鞋”将获得 120 美元的信用。“鞋”将获得 0 美元的信用。
* **线性**：每个促销活动将获得 60 美元的信用。

   参与率与线性分配相似，除了对所有值给予完全信用之外。如果您使用收入（参与率）作为量度，则忽略分配。此示例中的收入（参与率）会对两个搜索词都报告 120 美元。

>[!MORE_LIKE_THIS]
>
>* [量度计算](/help/components/c-variables/c-metrics/metrics-calculations.md)

