---
description: 使用动态标签管理部署 Adobe Analytics 时的字段描述和变量相关信息。
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: 全局变量
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: tm+mt
source-git-commit: e9820869d16b8656ebebe11e397a3d7d8123fbcf

---


# 全局变量

使用动态标签管理部署 Adobe Analytics 时的字段描述和变量相关信息。

这些变量在所有页面加载规则信标上触发。使用设置为在所有页面上触发的[页面加载规则](/help/implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md)，可以实现相同的效果。这些变量可能不会在[直接调用](/help/implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md)和[基于事件的](/help/implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md)规则中触发。

## 全局变量 - 字段描述 {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) **[!UICONTROL 编辑工具]** &gt; **[!UICONTROL 全局变量]**

| 元素 | 描述 |
|--- |--- |
| 服务器 | 该预定义变量填充 Adobe Analytics 中的“服务器”维度。请参阅[页面变量](/help/implement/js-implementation/page-variables/page-variables.md) |
| eVar | [eVar 变量](/help/implement/js-implementation/page-variables/evarn.md)用于构建自定义转化报表。 |
| Prop | [Prop 变量](/help/implement/js-implementation/page-variables/propn.md)用于生成自定义流量报表。 |
| 动态变量前缀 | 值开头的特殊前缀。默认前缀为 "D="。请参阅[动态变量](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/dynvars-overview.html) |
