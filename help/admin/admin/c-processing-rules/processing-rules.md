---
description: 处理规则简化了数据收集，并在数据被发送到报表时对内容进行管理。
subtopic: Processing rules
title: 处理规则概述
topic: 管理工具
uuid: 6b4ee7c9-2b86-47a6-b64c-c8d644fff67d
translation-type: tm+mt
source-git-commit: a42fdbf2938f08ab09f9be7e0e3e89bab4f50eae
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 68%

---


# 处理规则概述

处理规则简化了数据收集，并在数据被发送到报表时对内容进行管理。处理规则提供一个界面，可帮助简化 IT 团队和 Web 开发人员的交互，从而能够：

* 在产品概述页面设置事件
* 使用查询字符串参数填充促销活动
* 在一个 prop 中关联类别和页面名称，从而更方便地进行报告
* 将一个 eVar 复制到 prop 以查看路径
* 清除拼写错误的网站区域
* 将内部搜索词或促销活动 ID 从查询字符串提取到 eVar

>[!VIDEO](https://video.tv.adobe.com/v/26124/?quality=12&learn=on)

## 处理规则权限{#section_8A4846688050453784DAE4D89355169A}

默认情况下，管理员有权使用处理规则&#x200B;****。 管理员还可以通过管理工具界面将这些权限授予非管理员用户。有关说明，请参阅 []

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>由于处理规则会永久影响Analytics数据，Adobe强烈建议处理规则管理员在Adobe Analytics中接受认证培训，并熟悉报表包的所有数据源（标准网站、移动站点、移动应用、数据插入API等）。 了解有关在各种平台内填充的上下文数据变量和标准变量的知识，将有助于防止数据被意外删除或更改。

## 使用上下文数据简化数据收集  {#section_09EEA03612D24C15839631AA9E9668D8}

上下文数据变量是仅可用于处理规则的变量类型。 为了使用上下文数据变量，将通过您的实施发送键/值数据对，并且处理规则用于捕获标准 Analytics 变量中的这些值。这样编程人员就不必确切了解哪个 prop 和/或 eVar 应包含哪个值。

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

在代码中设置后，您可以设置处理规则以将值分配给变量。 例如：

1. 将`author`映射到`eVar2`
2. 将`section`映射到`prop1`和`eVar3`
3. 如果存在`author`和`section`，请设置`event5`

有关详细信息，请参阅《实施用户指南》中的[contextData](/help/implement/vars/page-vars/contextdata.md)。

## 使用处理规则转换点击数据和触发事件 {#section_8284E72E999244E091CD7FB1A22342B6}

处理规则可以监视传入值以转换常见拼写错误并基于报告数据设置事件。可以将 Prop 复制到 eVar，也可以关联报表的值以及设置事件。

## 在报表中使用上下文数据变量  {#section_BD098BC503024A0B8703596628071134}

在您的实施中定义上下文数据变量后，必须将这些变量复制到 eVar 等变量中，才能在报表中使用。

有关详细信息，请参阅[将上下文数据变量复制到eVar](processing-rules-examples/processing-rules-copy-context-data.md)和[使用上下文数据变量](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)设置事件。
