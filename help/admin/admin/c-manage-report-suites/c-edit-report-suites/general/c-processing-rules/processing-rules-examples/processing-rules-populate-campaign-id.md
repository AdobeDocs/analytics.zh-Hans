---
description: 您可以使用查询字符串参数填充变量。
subtopic: Processing rules
title: 通过查询字符串参数填充促销活动 ID
feature: Admin Tools
role: Admin
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
source-git-commit: e912f29a712269203643318a687831d68c9bfeb5
workflow-type: ht
source-wordcount: '112'
ht-degree: 100%

---

# 通过查询字符串参数填充促销活动 ID

您可以使用查询字符串参数填充变量。

在大多数情况下，您可以使用插件从查询字符串填充变量。如果发生拼写错误或类似问题妨碍了填充值，则可以使用处理规则填充变量。

在覆盖之前，应始终检查值是否为空或包含所需的值。

| 规则集 | 值 |
|---|---|
| 条件 | 促销活动未设置 |
| 操作 | 将促销活动的值覆盖为查询字符串参数 cpid |

例如：

![](assets/set-campaign-conditionally.png)
