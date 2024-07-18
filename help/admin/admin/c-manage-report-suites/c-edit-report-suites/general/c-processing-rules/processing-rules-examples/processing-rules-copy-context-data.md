---
description: 处理规则用于将上下文数据变量的值迁移到 prop 和 eVar。
subtopic: Processing rules
title: 将上下文数据变量复制到 eVar
feature: Admin Tools
role: Admin
exl-id: f52c2c6c-da3d-43d6-be13-92d0820c93b4
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 100%

---

# 将上下文数据变量复制到 eVar

处理规则用于将上下文数据变量的值迁移到 prop 和 eVar。如果没有处理规则，上下文数据变量将毫无意义，并且不会在 Analytics 中填充任何报表。

[!UICONTROL 上下文变量]列表包含在之前 30 天发送到报表包中的所有变量。如果您知道上下文数据变量名称，但尚未将其发送到当前报表包，则可通过键入变量名称并单击&#x200B;**[!UICONTROL 添加变量名称上下文数据]**&#x200B;来添加值：

![添加](assets/add-context-variable.png)

以下示例采用 `search_term` 上下文数据变量并将其值放入 `eVar3` 中：

![已设置](assets/set-context-data.png)

当要填充的 eVar 只有几个时，以上示例非常有用。如果贵组织有数百个上下文数据变量，而每个变量都需要自己的 eVar，则可以使用条件语句。一条处理规则中可以包含数十个条件语句，这使您的组织能够在报表包中填充所有 eVar，而不会遇到 150 条规则的处理规则限制。

以下示例使用上下文数据变量 `testhierarchy` 填充 `prop7`，但前提是已设置 `testhierarchy`：

![视情况而定](assets/add-conditional.png)

有关实施上下文数据变量的更多信息，请参阅“实施”用户指南中的[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)。
