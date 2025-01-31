---
description: 处理规则简化了数据收集，并在数据被发送到报表时对内容进行管理。
subtopic: Processing rules
title: 处理规则概述
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 97%

---

# 处理规则概述

处理规则简化了数据收集，并在数据被发送到报表时对内容进行管理。处理规则提供一个界面，可帮助简化 IT 团队和 Web 开发人员的交互，从而能够：

* 在产品概述页面设置事件
* 使用查询字符串参数填充促销活动
* 在一个 prop 中关联类别和页面名称，从而更方便地进行报告
* 将一个 eVar 复制到 prop 以查看路径
* 清除拼写错误的网站区域
* 将内部搜索词或促销活动 ID 从查询字符串提取到 eVar



>[!BEGINSHADEBOX]

有关演示视频，请参阅![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [处理规则概述](https://video.tv.adobe.com/v/26124/?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


## 处理规则权限 {#section_8A4846688050453784DAE4D89355169A}

管理员&#x200B;**在默认情况下**&#x200B;有权使用处理规则。管理员还可通过“管理工具”界面将这些权限授予非管理员用户。有关说明，请参阅 []

![处理规则](assets/processing-rules.png)

## 使用上下文数据简化数据收集 {#section_09EEA03612D24C15839631AA9E9668D8}

上下文数据变量是仅对处理规则可用的一种变量。为了使用上下文数据变量，将通过您的实施发送键/值数据对，并且处理规则用于捕获标准 Analytics 变量中的这些值。这样编程人员就不必确切了解哪个 prop 和/或 eVar 应包含哪个值。

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

在代码中设置后，即可设置处理规则以将值分配给变量。例如：

1. 将 `author` 映射到 `eVar2`
2. 将 `section` 映射到 `prop1` 和 `eVar3`
3. 如果存在 `author` 和 `section`，则设置 `event5`

有关详细信息，请参阅实施用户指南中的 [contextData](/help/implement/vars/page-vars/contextdata.md)。

## 使用处理规则转换点击数据和触发事件 {#section_8284E72E999244E091CD7FB1A22342B6}

处理规则可以监视传入值以转换常见拼写错误并基于报告数据设置事件。可以将 Prop 复制到 eVar，也可以关联报表的值以及设置事件。

## 在报表中使用上下文数据变量 {#section_BD098BC503024A0B8703596628071134}

在您的实施中定义上下文数据变量后，必须将这些变量复制到 eVar 等变量中，才能在报表中使用。

有关详细信息，请参阅[将上下文数据变量复制到 eVar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) 和[使用上下文数据变量设置事件](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)。

## 已知限制

**在处理规则中使用插入符号 (^)。**&#x200B;如果要在处理规则中使用插入符号作为分隔符或用于其他目的，则每个插入符号必须由两个插入符号表示。 例如，将一个插入符号表示为 ^^，将两个插入符号表示为 ^^^^，诸如此类。