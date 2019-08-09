---
description: '在谈论与DFA集成相关的指标时，Adobe使用以下条款 '
keywords: DFA
seo-description: '在谈论与DFA集成相关的指标时，Adobe使用以下条款 '
seo-title: 量度定义
solution: Analytics
title: 量度定义
topic: Data connectors
uuid: 062f6863-3daa-4e8a-b6 ea-84279d49 c388
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 量度定义{#metric-definitions}

Adobe 使用以下术语谈论与 DFA 集成相关的量度：

**展示次数：**&#x200B;展示次数是指广告被查看的次数。展示次数是基于每个广告逐一报告的，但也可以汇总为广告组或其他多广告分组。Analytics 中的展示次数量度是通过夜间数据源导入从 DFA 导入的。

**点击量**：点击量是指由 DFA 报告的广告被点击的次数。在访客登陆客户网站之前，在 DFA 重定向页面上进行点击量登记。与展示次数一样，Analytics 中的点击量量度也是通过夜间数据源导入从 DFA 导入的。

**点进次数**：点进次数是指用户在单击某广告后到达登陆页面的次数。此量度可能与点击量存在细微的差别。

**显示到达次数**：显示到达次数是指访客在查看某广告后并未单击它，但最终到达客户网站的次数。访客必须在显示到达时间范围之内前往该网站，默认设置为 30 天。展示发生的时间必须晚于上次点击。显示到达次数针对每个促销活动、每次访问登记一次，并在集成使用 DFA 促销活动 ID 填充显示到达 eVar 时且设置了显示到达事件的情况下进行计数。
