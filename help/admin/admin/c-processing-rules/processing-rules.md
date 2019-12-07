---
description: 处理规则简化了数据收集，并在数据被发送到报表时对内容进行管理。
subtopic: Processing rules
title: 处理规则概述
topic: Admin tools
uuid: 6b4ee7c9-2b86-47a6-b64c-c8d644fff67d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 处理规则概述

处理规则简化了数据收集，并在数据被发送到报表时对内容进行管理。处理规则提供一个界面，可帮助简化 IT 团队和 Web 开发人员的交互，从而能够：

* 在产品概述页面设置事件
* 使用查询字符串参数填充促销活动
* 在一个 prop 中关联类别和页面名称，从而更方便地进行报告
* 将一个 eVar 复制到 prop 以查看路径
* 清除拼写错误的网站区域
* 将内部搜索词或促销活动 ID 从查询字符串提取到 eVar

>[!VIDEO](https://tv.adobe.com/embed/1181/16506/)

*观看来自 Adobe 峰会的处理规则概述和培训，以了解为何要使用处理规则的理由。*

## 获得使用处理规则的授权 {#section_8A4846688050453784DAE4D89355169A}

在 2017 年 4 月 20 日之前，所有用户（包括管理员）都必须通过测验，然后才能获得 Adobe 客户关怀赋予的使用处理规则的授权。

当前，管理员&#x200B;**默认**&#x200B;拥有使用处理规则的权限。不再需要进行测验。管理员还可以通过管理工具界面将这些权限授予非管理员用户。以下是具体操作方法：

1. 如果您还没有这么做，[请创建一个群组](/help/admin/user-management2/c-user-groups/groups.md)，其中只包含那些应当有权使用处理规则的非管理员。
1. [将非管理员添加到该组](/help/admin/user-management2/c-user-management/t-add-user-to-group.md)。
1. 然后转到 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理员]** &gt; **[!UICONTROL 用户管理]** &gt; **[!UICONTROL 群组]** &gt; **[!UICONTROL [群组名称]]** &gt; **[!UICONTROL 编辑]** &gt; **[!UICONTROL 报表访问]** &gt; **[!UICONTROL 报表包工具]** &gt; **[!UICONTROL 自定义]** &gt; **[!UICONTROL 报表包管理]**。
1. 选中[!UICONTROL 处理规则]旁边的框，然后单击&#x200B;**[!UICONTROL 确定]**。

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>由于处理规则会永久影响 Analytics 数据，我们强烈建议处理规则的管理员参加 Adobe Analytics 的认证培训，并熟悉报表包的所有数据源（标准网站、移动设备网站、移动设备应用程序、数据插入 API 等）。了解有关在各种平台内填充的上下文数据变量和标准变量的知识，将有助于防止数据被意外删除或更改。

## 使用上下文数据简化数据收集 {#section_09EEA03612D24C15839631AA9E9668D8}

上下文数据变量是一种只可用于处理规则的新型变量。为了使用上下文数据变量，将通过您的实施发送键/值数据对，并且处理规则用于捕获标准 Analytics 变量中的这些值。这样编程人员就不必确切了解哪个 prop 和/或 eVar 应包含哪个值。

![](assets/evar-context-map.png)

请参阅实施帮助中的[上下文数据变量](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html)。

## 使用处理规则转换点击数据和触发事件 {#section_8284E72E999244E091CD7FB1A22342B6}

处理规则可以监视传入值以转换常见拼写错误并基于报告数据设置事件。可以将 Prop 复制到 eVar，也可以关联报表的值以及设置事件。

## 在报表中使用上下文数据变量 {#section_BD098BC503024A0B8703596628071134}

在您的实施中定义上下文数据变量后，必须将这些变量复制到 eVar 等变量中，才能在报表中使用。

有关详细信息，请访问[此处](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)和[此处](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)。
