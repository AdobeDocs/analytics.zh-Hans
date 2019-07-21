---
description: 使用动态标签管理部署 Adobe Analytics 时的字段描述和变量相关信息。
keywords: 动态标签管理；全局变量；server变量；evar；props；动态变量前缀；动态变量
seo-description: 使用动态标签管理部署 Adobe Analytics 时的字段描述和变量相关信息。
seo-title: 全局变量
solution: Marketing Cloud、Analytics、动态标签管理
title: 全局变量
uuid: d759320a-96ee-4073-b5 fd-5257b7033003
translation-type: tm+mt
source-git-commit: 3489f00bd7dddefda0420fc361056416f6f10d3f

---


# 全局变量

使用动态标签管理部署 Adobe Analytics 时的字段描述和变量相关信息。

这些变量在所有页面加载规则信标上触发。使用设置为在所有页面上触发的[页面加载规则](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706)可达到相同的效果。These variables might not fire in [Direct-Call](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09) and [Event-Based](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC) rules.

## 全局变量 - 字段描述 {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png)**[!UICONTROL 编辑工具]** &gt; **[!UICONTROL 全局变量]**

| 元素 | 描述 |
|--- |--- |
| 服务器 | 预定义变量填充Adobe Analytics中的服务器维度。See [Page Variables](/help/implement/js-implementation/c-variables/page-variables.md) |
| eVar | [eVar变量](/help/implement/js-implementation/c-variables/page-variables.md) 用于构建自定义转化报表。 |
| Prop | [Prop变量](/help/implement/js-implementation/c-variables/page-variables.md) 用于构建自定义流量报表。 |
| 动态变量前缀 | 值开头的特殊前缀。默认前缀为 "D="。See [Dynamic Variables](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
