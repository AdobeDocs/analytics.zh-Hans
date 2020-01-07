---
description: 适用于 Analysis Workspace 和区段生成器。
title: 具有 Experience Cloud ID 的访客
uuid: 47ebd3d6-a921-4e51-ac7a-b8d5fb9565e0
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 具有 Experience Cloud ID 的访客

适用于 Analysis Workspace 和区段生成器。

显示具有 Experience Cloud ID 的访客数量。通过该量度，您可以了解：哪些页面部署了 Identity Service，可以与其他 Experience Cloud 解决方案共享多少访客。此外，您还可以在那些共享到 Experience Cloud 的区段中使用该量度。

>[!IMPORTANT]
>
>要显示该量度，必须为报表包运行 [Identity Service](https://marketing.adobe.com/resources/help/zh_CN/mcvid/)。

## 调试您的 Experience Cloud ID 设置 {#section_679E62142A3E46548FF8FBDA46568005}

“[!UICONTROL 具有 Experience Cloud ID 的访客]”量度是 Adobe Analytics 中的一个有用量度，可帮助您查找并调试 [!UICONTROL Identity Service] 设置。该量度是报表包中对已从 Identity Service 分配 Experience Cloud ID 的访客的计数。该量度可用于诊断某些 Experience Cloud 集成为何没有被预期访客数共享，或用于识别您的网站上还没有部署 MCID 的区域。

要使用“具有 Experience Cloud ID 的访客”量度，只需将它拖到任何报表中作为一个量度，例如“[!UICONTROL 页面]”报表：

![](assets/metric-mcvid1.png)

在该示例中，请注意每个页面的独特访客与具有 Experience Cloud ID 的访客数相同。但是，独特访客的总数大于具有 Experience Cloud ID 的访客总数。要查找没有为所有访客设置 MCID 的页面，请通过此定义[创建一个计算量度](https://marketing.adobe.com/resources/help/zh_CN/analytics/calcmetrics/cm_build_metrics.html)：

![](assets/metric-mcvid2.png)

通过将计算量度添加到报表，您可以对页面报表进行排序，以便显现无 MCID 的访客数量最高的页面：

![](assets/metric-mcvid3.png)

现在，您可以很快发现“产品快速视图”页面没有妥善实施 Identity Service，应当尽快对其进行更新。可围绕任意维度类型（如浏览器类型、网站区域或内容类型）构建一个类似的报表。

在识别了页面的访客没有 MCID 的情况后，您应当能够将该情况报告给实施团队，以便他们能够修复这些页面。

在某些情况下，您可能发现有少量的 MCID 没有对某些访客进行设置，即使 MCID 服务已在该页面上实施时也是如此。在这些情况下，此问题极有可能是因 Analytics JavaScript 或 DTM 的常见错误配置导致 AppMeasurement 函数在提供报表包之前被调用所致。要避免此问题，请确保正确地[插入核心 AppMeasurement 代码](https://marketing.adobe.com/resources/help/en_US/sc/implement/dtm/t_appmeasurement-code.html)。

请注意，您与 Experience Cloud 共享的任何基于“产品快速视图”页面的区段（如上所示），有可能与其他 Experience Cloud 解决方案并不匹配。要检查任何区段的 MCID 覆盖情况，您可以构建如下报表：

![](assets/metric-mcvid4.png)

此表比较了“独特访客数”和“具有 Experience Cloud ID 的访客数”，很容易就可以看出“区段 1”没有 100% 覆盖 MCID，而“区段 2”则有。这意味着，如果我要与 Experience Cloud 共享区段 1，则在总共 3859 名访客中，只有 2186 名访客有共享资格。
