---
description: 适用于 Analysis Workspace 和区段生成器。
seo-description: 适用于 Analysis Workspace 和区段生成器。
seo-title: 具有 Experience Cloud ID 的访客
title: 具有 Experience Cloud ID 的访客
uuid: 47ebd3d6-a921-4e51-ac7a-b8d5fb9565e0
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 具有 Experience Cloud ID 的访客

适用于 Analysis Workspace 和区段生成器。

显示具有 Experience Cloud ID 的访客数量。您可以了解哪些页面已部署了Identity Service，并可以了解与其他Experience cloud解决方案共享的访客数。 此外，您还可以在那些共享到 Experience Cloud 的区段中使用该量度。

>[!IMPORTANT]
>
>For this metric to appear, you have to have the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) running for the report suite.

## 调试您的 Experience Cloud ID 设置 {#section_679E62142A3E46548FF8FBDA46568005}

The [!UICONTROL Visitors with Experience Cloud ID] metric is a useful metric in Adobe Analytics intended to help you find and debug your [!UICONTROL Identity Service]setup. 该量度是从标识服务中分配了Experience Cloud ID的报表包中的访客数的计数。 该量度可用于诊断某些 Experience Cloud 集成为何没有被预期访客数共享，或用于识别您的网站上还没有部署 MCID 的区域。

要使用“具有 Experience Cloud ID 的访客”量度，只需将它拖到任何报表中作为一个量度，例如“[!UICONTROL 页面]”报表：

![](assets/metric-mcvid1.png)

在该示例中，请注意每个页面的独特访客与具有 Experience Cloud ID 的访客数相同。但是，独特访客的总数大于具有 Experience Cloud ID 的访客总数。要查找没有为所有访客设置 MCID 的页面，请通过此定义[创建一个计算量度](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_build_metrics.html)：

![](assets/metric-mcvid2.png)

通过将计算量度添加到报表，您可以对页面报表进行排序，以便显现无 MCID 的访客数量最高的页面：

![](assets/metric-mcvid3.png)

现在，您可以快速看到“产品概览”页面未通过Identity service正确实施，应尽快更新。 可围绕任意维度类型（如浏览器类型、网站区域或内容类型）构建一个类似的报表。

一旦您识别出具有没有MCID的访客的页面，您应该能够将该页面带回您的实施团队，以便他们能够修复这些页面。

在某些情况下，您可能发现有少量的 MCID 没有对某些访客进行设置，即使 MCID 服务已在该页面上实施时也是如此。在这些情况下，此问题极有可能是因 Analytics JavaScript 或 DTM 的常见错误配置导致 AppMeasurement 函数在提供报表包之前被调用所致。要避免此问题，请确保正确地[插入核心 AppMeasurement 代码](https://marketing.adobe.com/resources/help/en_US/sc/implement/dtm/t_appmeasurement-code.html)。

请注意，您与Experience cloud共享的基于“产品概览”页面（如上所示）的任何细分，都可能与其他Experience cloud解决方案的匹配率极低。 要检查任何区段的 MCID 覆盖情况，您可以构建如下报表：

![](assets/metric-mcvid4.png)

从此表中（将唯一访客数与具有Experience Cloud ID的访客数进行比较），可轻松看到“区段1”没有100%的MCID覆盖，而“区段2”有。 这意味着，如果我要与 Experience Cloud 共享区段 1，则在总共 3859 名访客中，只有 2186 名访客有共享资格。
