---
description: 处理规则可以触发基于上下文数据变量的事件。
subtopic: Processing rules
title: 使用上下文数据变量设置事件
topic: Admin tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# 使用上下文数据变量设置事件

处理规则可以触发基于上下文数据变量的事件。

在 AppMeasurement 中可按以下格式指定上下文数据变量：

```
 s.contextData['search_term']
```

The [!UICONTROL Context Variables] list contains all variables that were sent to the report suite in the previous 30 days. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

以下规则定义对[将上下文数据变量复制到 eVar](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) 规则进行了扩展，以便在包含特定上下文数据变量的每个点击上设置事件：

| 规则集 | 值 |
|---|---|
| 条件 | 设置了“搜索词”上下文数据时 |
| 操作 | 设置事件“搜索” |

例如：

![](assets/processing_rule_set_event.png)

请参阅实施帮助中的[上下文数据变量](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html)。
