---
title: 将启动项数据元素映射到Analytics变量
description: 将数据元素分配给Analytics变量，以便在分析工作区中将其用作维。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 将启动项数据元素映射到Analytics变量

在Adobe Experience Platform Launch中拥有数据元素存储库后，您可以将其分配到Analytics维。

## 先决条件

[将数据层对象映射到数据元素](layer-to-elements.md):确保您了解Launch中的数据元素，并且有几个要处理的元素。

[创建解决方案设计文档](../prepare/solution-design.md):解决方案设计文档对于保持有组织性至关重要。 遵循解决方案设计文档可简化数据元素到Analytics变量的分配。

## 为Analytics变量分配数据元素

按照以下步骤在Launch中发布库后，您可以在分析工作区中使用自定义维。 您可以全局设置Analytics变量，也可以在单个规则中设置。

### 设置全局变量

全局变量是理想情况，当您希望在数据元素所在的所有页面上设置变量值时。

1. 转到 [Adobe Experience Platform Launch](https://launch.adobe.com)，并在出现提示时登录。
1. 单击所需的启动项属性。
1. 单击 [!UICONTROL Extensions tab]，然后单击 [!UICONTROL Configure] Adobe Analytics扩展下的。
1. 单击accordion [!UICONTROL Global variables] ，该面板显示用于分配全局变量的界面。

### 在规则中设置变量

在不希望在每页设置变量的情况下，规则中设置的变量是理想的。 您可以在规则中定义条件。 See [Rules](https://docs.adobe.com/content/help/zh-Hans/launch/using/reference/manage-resources/rules.html) in the Adobe Experience Platform Launch user guide.

1. 转到 [Adobe Experience Platform Launch](https://launch.adobe.com)，并在出现提示时登录。
1. 单击所需的启动项属性。
1. 单击选 [!UICONTROL Rules] 项卡，然后单击所需的规则（或创建一个）。
1. 单击下 [!UICONTROL Add] 面的按钮 [!UICONTROL Actions]。
1. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Set Variables.
1. 单击所 ![需Analytics变量右侧的](assets/data-element.png) “数据”元素图标。 贵组织的解决方案 [设计文档规定](../prepare/solution-design.md) ,Analytics变量应使用哪些内容。
1. 在模态窗口中选择所需的数据元素。 单击 [!UICONTROL Select].
1. 数据元素名称将添加到由符号环绕的文本字 `%` 段。 例如，如果将数据元素命名为“页面名称”，则在将数据元素分配到变 `%Page name%` 量时将看到该字符串。

>[!TIP] 您可以在同一变量中连接数据元素。 例如，如果您有“主机名”数据元素和“路径名”数据元素，则可以使用将这两个元素组合到单个变量中 `%Hostname%%Pathname%`。

## 后续步骤

[页面变量](../vars/page-vars/page-variables.md):了解在实施中可以使用哪些页面级变量，以便在分析工作区中进一步挖掘维度。

[配置变量](../vars/config-vars/configuration-variables.md):了解在实施中可以使用哪些配置变量来释放Adobe Analytics中的更多功能。
