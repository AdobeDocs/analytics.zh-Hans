---
title: 将标记数据元素映射到 Analytics 变量
description: 将数据元素分配给 Analytics 变量，以便在 Analysis Workspace 中可以将这些变量用作维度。
feature: Tags
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
source-git-commit: 2aef8de290399f234921b09cf094485fc06f1c24
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 96%

---


# 将标记数据元素映射到 Analytics 变量

一旦您拥有标记数据元素的存储库，就可以将它们分配给 Analytics 维度。

## 先决条件

[将数据层对象映射到数据元素](layer-to-elements.md)：确保您了解标记数据元素，并且拥有可使用的若干标记数据元素。

[创建解决方案设计文档](../prepare/solution-design.md)：解决方案设计文档是保持有条不紊的关键。遵循解决方案设计文档可简化将数据元素分配给 Analytics 变量的流程。

## 将数据元素分配给 Analytics 变量

按照这些步骤发布标记库后，您可以在 Analysis Workspace 中使用自定义维度。您可以在全局范围内设置 Analytics 变量，也可以在单个规则中设置。

### 设置全局变量

如果您希望在数据元素所在的所有页面上设置变量值，理想的做法是设置全局变量。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 单击[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 扩展下的[!UICONTROL 配置]。
1. 单击[!UICONTROL 全局变量]折叠图标，这会显示用于分配全局变量的界面。

### 在规则中设置变量

如果您不希望在每个页面上设置变量，理想的做法是在规则中设置变量。在规则中定义条件。请参阅 Adobe Experience Platform 标记文档中的[规则](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=zh-Hans)。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 单击[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建一个规则）。
1. 单击[!UICONTROL 操作]下的[!UICONTROL 添加]按钮。
1. 设置 [!UICONTROL 扩展名] Adobe Analytics的下拉列表，以及 [!UICONTROL 操作类型] 设置变量。
1. 单击所需 Analytics 变量右侧的 ![数据元素](assets/data-element.png) 图标。贵组织的[解决方案设计文档](../prepare/solution-design.md)规定了要使用的 Analytics 变量。
1. 在模式窗口中选择所需的数据元素。单击[!UICONTROL 选择]。
1. 数据元素名称将添加到被 `%` 符号包围的文本字段中。例如，如果将数据元素命名为“页面名称”，则在将数据元素分配给变量时，会看到字符串 `%Page name%`。

>[!TIP]
>
>可以在同一变量中将数据元素连接在一起。例如，如果您有“Hostname”数据元素和“Pathname”数据元素，则可以使用 `%Hostname%%Pathname%` 将这两个元素组合到单个变量中。

## 后续步骤

[页面变量](../vars/page-vars/page-variables.md)：了解在实施中可以使用哪些页面级变量，以便进一步挖掘 Analysis Workspace 中的维度价值。

[配置变量](../vars/config-vars/configuration-variables.md)：了解在实施中可以使用哪些配置变量来解锁 Adobe Analytics 中的更多功能。
