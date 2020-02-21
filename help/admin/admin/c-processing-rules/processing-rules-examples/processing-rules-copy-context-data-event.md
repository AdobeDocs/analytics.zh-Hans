---
description: 处理规则可以触发基于上下文数据变量的事件。
subtopic: Processing rules
title: 使用上下文数据变量设置事件
topic: Admin tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用上下文数据变量设置事件

处理规则可以触发基于上下文数据变量的事件。

在 AppMeasurement 中可按以下格式指定上下文数据变量：

```
 s.contextData['search_term']
```

[!UICONTROL 上下文变量]列表包含在之前 30 天发送到报表包中的所有变量。如果您知道上下文数据变量名称，但尚未将其发送到当前报表包，则可通过键入变量名称并单击&#x200B;**[!UICONTROL 添加变量名称上下文数据]**&#x200B;来添加值：

![](assets/add-context-variable.png)

以下规则定义对[将上下文数据变量复制到 eVar](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) 规则进行了扩展，以便在包含特定上下文数据变量的每个点击上设置事件：

| 规则集 | 数值 |
|---|---|
| 条件 | 设置了“搜索词”上下文数据时 |
| 操作 | 设置事件“搜索” |

例如：

![](assets/processing_rule_set_event.png)

请参阅实施帮助中的[上下文数据变量](https://marketing.adobe.com/resources/help/zh_CN/sc/implement/context_data_variables.html)。
