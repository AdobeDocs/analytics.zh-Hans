---
description: 处理规则可以触发基于上下文数据变量的事件。
subtopic: Processing rules
title: 使用上下文数据变量设置事件
feature: Admin Tools
role: Admin
exl-id: f0af0e23-c08a-4f82-85b4-25064eeaa3c6
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 100%

---

# 使用上下文数据变量设置事件

处理规则可以触发基于上下文数据变量的事件。

在 AppMeasurement 中可按以下格式指定上下文数据变量：

```
 s.contextData['search_term']
```

[!UICONTROL 上下文变量]列表包含在之前 30 天发送到报表包中的所有变量。如果您知道上下文数据变量名称，但尚未将其发送到当前报表包，则可通过键入变量名称并单击&#x200B;**[!UICONTROL 添加变量名称上下文数据]**&#x200B;来添加值：

![](assets/add-context-variable.png)

以下规则定义对[将上下文数据变量复制到 eVar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) 规则进行了扩展，以便在包含特定上下文数据变量的每个点击上设置事件：

| 规则集 | 值 |
|---|---|
| 条件 | 设置了“搜索词”上下文数据时 |
| 操作 | 设置事件“搜索” |

例如：

![](assets/processing_rule_set_event.png)

请参阅实施帮助中的[上下文数据变量](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/contextdata.html?lang=zh-Hans)。
