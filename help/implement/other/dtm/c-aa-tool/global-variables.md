---
description: 使用动态标签管理部署 Adobe Analytics 时的字段描述和变量相关信息。
keywords: Dynamic Tag Management;全局变量;服务器变量;eVar;prop;动态变量前缀;动态变量
solution: Experience Cloud,Analytics
title: 全局变量
uuid: d759320a-96ee-4073-b5fd-5257b7033003
exl-id: e78e9ff4-bfce-4fa0-8d53-fd33ed3052fd
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '150'
ht-degree: 100%

---

# 全局变量

使用动态标签管理部署 Adobe Analytics 时的字段描述和变量相关信息。

这些变量在所有页面加载规则信标上触发。使用设置为在所有页面上触发的[页面加载规则](/help/implement/other/dtm/c-rules/t-rules-page-conditions.md)，可以实现相同的效果。这些变量可能不会在[直接调用](/help/implement/other/dtm/c-rules/t-rules-direct-conditions.md)和[基于事件的](/help/implement/other/dtm/c-rules/t-rules-event-conditions.md)规则中触发。

## 全局变量 - 字段描述 {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]**> ![](assets/settings_gear.png)**[!UICONTROL &#x200B;编辑工具&#x200B;]**>**[!UICONTROL &#x200B;全局变量&#x200B;]**

| 元素 | 描述 |
|--- |--- |
| Server | 该预定义变量填充 Adobe Analytics 中的“服务器”维度。请参阅[服务器](../../../vars/page-vars/server.md)。 |
| eVar | [eVar 变量](../../../vars/page-vars/evar.md)用于构建自定义转化报表。 |
| Prop | [Prop 变量](../../../vars/page-vars/prop.md)用于生成自定义流量报表。 |
| 动态变量前缀 | 值开头的特殊前缀。默认前缀为 &quot;D=&quot;。请参阅[动态变量](../../../vars/page-vars/dynamic-variables.md) |
