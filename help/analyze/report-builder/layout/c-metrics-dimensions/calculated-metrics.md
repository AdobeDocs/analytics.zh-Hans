---
description: Report Builder 5.2支持Adobe Analytics统一计算指标。 作为诸多创新中的一种，目前所有计算量度都拥有一个全局 ID - 不再局限于单一的报表包之中。
title: 计算量度
uuid: c9814894-cda6-40ff-8ec4-3ab2c1908ebc
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 计算量度

Report Builder 5.2支持Adobe Analytics统一计算指标。 作为诸多创新中的一种，目前所有计算量度都拥有一个全局 ID - 不再局限于单一的报表包之中。

>[!NOTE] 现有的工作簿可能会指向包含旧量度 ID 的请求。使用Report Builder 5.2时，这些旧版度量ID将转换为新的全局ID。 如果您与Report Builder v5.1或更早版本的用户共享此工作簿，则该用户将无法看到计算的度量。

要进一步了解如何使用新的计算量度生成器和管理器创建和管理计算量度，请参阅“计算量 [度指南](https://marketing.adobe.com/resources/help/zh_CN/analytics/calcmetrics) ”。

在请求向导的步骤2中，您可以过滤和应用计算的度量。

## 过滤计算量度 {#section_376E986D3E684999A7CDB08E53854159}

单击“过滤器”图标 ![](assets/segment_filter.png) 可以&#x200B;**过滤**&#x200B;计算量度

。“高级过滤器”对话框中同时填充标准和计算量度。

可用过滤器包括：

![](assets/advanced_filters_(2).png)

| 过滤器名称 | 描述 |
|---|---|
| 标记 | 允许您使用特定标记过滤计算的量度。 请注意，标记过滤器使用AND运算符。 如果选中两个标记，右侧窗格将显示已用这两个标记标记的 **量度** 。 |
| 报表包 | 如果在 *的计算量度生成器中应用“仅*&#x200B;报表包名称[!DNL Reports & Analytics]”过滤器，然后在 [!DNL Report Builder] 中显示“高级过滤器”，则“高级过滤器”将仅显示选定报表包的计算量度。 |
| 所有者 | 允许您按所有者筛选指标。 请注意，所有者过滤器使用OR运算符。 如果选中两个所有者，则右侧窗格将显示其中一个所有者拥有的 **量度** 。 |
| 其他过滤器>已批准 | 显示所有正式批准的指标。 |
| 其他过滤器>收藏夹 | 显示标记为“收藏夹”的所有指标。 |
| 其他过滤器 > 我的 | 显示您拥有的所有指标。 |
| 其他过滤器 > 与我共享 | 显示其他人与您共享的所有指标。 |

## 应用计算量度 {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

选择过滤器后，单击以 **[!UICONTROL Apply]** 将其应用于您的请求。 选定的量度现已添加到报表布局。

![](assets/filtering_for_metric.png)

