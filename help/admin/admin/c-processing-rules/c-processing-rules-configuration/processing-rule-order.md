---
description: 处理规则位于主要Analytics数据管道中的位置。
subtopic: Processing rules
title: 处理顺序
feature: Processing Rules
exl-id: c7143527-017c-4550-b55e-09ea437d7c85
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 49%

---

# 处理顺序

要有效地使用处理规则，必须了解在数据收集期间何时应用这些规则。

![处理顺序](assets/analytics_processing_order.png)

下表列出了在应用处理规则之前和之后通常可用的数据。

## 应用处理规则之前

| 维度 | 描述 |
|--- |--- |
| [动态变量](/help/implement/vars/page-vars/dynamic-variables.md) | 通过从HTTP标头或其他变量中提取信息来动态填充的变量。 |
| [AppMeasurement](/help/implement/home.md) | AppMeasurement库中使用的函数和插件将在浏览器或客户端应用程序中执行。 |
| [标记实施](/help/implement/launch/overview.md) | 在Adobe Experience Platform数据收集的Adobe Analytics扩展中定义的规则。 |
| [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/analytics-overview.html) | 通过Web SDK收集的数据会发送到Adobe Experience Edge，然后转发到所需的报表包。 |
| [机器人规则](/help/admin/admin/bot-removal/bot-rules.md) | 允许您删除已知蜘蛛程序和机器人程序生成的流量。 |

## 应用处理规则之后

| 维度 | 描述 |
|--- |--- |
| 由 VISTA 添加的数据 | 处理规则先于 VISTA 应用。 |
| 访问页面编号 | 处理规则只会感知当前点击中包含的数据。 访问页面编号将在应用处理规则之后编译。 |
| 如果未设置页面名称，将添加简洁 URL 作为页面名称 | 在应用处理规则和 VISTA 之后，如果未设置页面名称，将添加简洁 URL 作为页面名称。由于此逻辑在应用处理规则后发生，因此Adobe建议添加条件以检查页面名称是否为空。  如果您运行 **[!UICONTROL 网站内容]** > **[!UICONTROL 页面]** 报表时，您会看到页面名称的URL值，页面名称变量可能为空。  您可以设置一个条件来测试空的页面名称，或者测试以查看页面名称或页面URL是否包含特定值。 然后可以根据需要设置页面名称。 |
| 营销渠道处理规则 | 您可以使用处理规则来准备由[营销渠道处理规则](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html)处理的数据。 |
| 地域查找 | 包括“访客所在州”和“访客ZIP/邮政编码”值。 |
| eVars 持久性 | 在规则处理过程中，上次点击中包含的 eVar 不会持久用于每个点击。只有在当前正在处理的点击上设置的 eVar 可用。 |

## 使用 VISTA 复制点击量时如何应用处理规则

如果配置了 VISTA 规则以将点击次数复制到另一报表包，则将通过在该报表包中定义的任何处理规则发送点击次数。

如果您在原始报表包上定义了处理规则，则这些规则可能会应用，也可能不会应用，具体取决于工程服务部门配置VISTA规则的方式。 若要确定是否应用了这些规则，您可以询问实施专家 VISTA 规则是将“pre”值还是“post”值复制到了其他报表包中。如果复制的是“pre”值，则不会应用初始报表包中定义的处理规则。如果复制的是“post”值，则会在复制点击量前应用处理规则。
