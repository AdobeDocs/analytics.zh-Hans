---
description: 处理规则可以触发基于上下文数据变量的事件。
seo-description: 处理规则可以触发基于上下文数据变量的事件。
seo-title: 使用上下文数据变量设置事件
solution: Analytics
subtopic: 处理规则
title: 使用上下文数据变量设置事件
topic: 管理工具
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: tm+mt
source-git-commit: 45e3330adb562ec795d287ae1c1fa6b03a2b2a31

---


# 使用上下文数据变量设置事件

处理规则可以触发基于上下文数据变量的事件。

在 AppMeasurement 中可按以下格式指定上下文数据变量：

```
 s.contextData['search_term']
```

[!UICONTROL 上下文变量]列表包含在之前 30 天发送到报表包中的所有变量。If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

以下规则定义在将上下文数据变量复制到eVar规则上展开，以便在每次点击时都设置一个事件，该事件包含特定的上下文数据变量： [](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)

| 规则集 | 数值 |
|---|---|
| 条件 | 设置了“搜索词”上下文数据时 |
| 操作 | 设置事件“搜索” |

例如：

![](assets/processing_rule_set_event.png)

请参阅实施帮助中的[上下文数据变量](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html)。
