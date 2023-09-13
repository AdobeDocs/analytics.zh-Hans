---
title: Data Warehouse 中的组件支持
description: 了解 Data Warehouse 中有哪些其他维度和指标可用以及不支持哪些维度和指标。
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 65%

---

# Data Warehouse 中的组件支持

Data Warehouse架构中的独特处理允许使用某些在Adobe Analytics的其他功能中通常不可用的组件。 由于其独特的架构，某些组件无法用于报表或区段。使用此页面可了解哪些组件可以使用，哪些组件不可使用。

## Data Warehouse 的特有组件

在Adobe Analytics中使用其他功能时，某些可在Data Warehouse中使用的维度和量度不可用。

### 专门支持的维度

* **EXPERIENCE CLOUDID**：对于使用Experience CloudID服务(ECID)的实施，由两个64位数字拼接而成的128位数字，占据了19位数。
* **页面URL**：点击发生的页面URL。
* **购买ID**：购买的唯一标识符，使用purchaseID变量设置。
* **访客ID**：提供访客的唯一标识符。 此值与数据馈送中的 `visid_high` 和 `visid_low` 列的拼接值相同。有关更多信息，请参阅“数据馈送”下的[数据列引用](../analytics-data-feed/c-df-contents/datafeeds-reference.md)。

### 专门支持的指标

* **访问**：在Data Warehouse上下文中，此指标不包括非永久性Cookie访问。
* **访问数 — 所有访客**：在Data Warehouse上下文中，此指标与Adobe Analytics内其他工具中的“访问次数”指标更接近。

## Data Warehouse 中不支持的组件

Data Warehouse 不支持某些维度和指标。

>[!NOTE]
>
>如果 Data Warehouse 不支持某个维度或指标，则也不支持使用这些维度或指标的区段。在创建或编辑区段时，请务必检查产品兼容性。

### 不支持的维度

* 一些基于时间的维度，包括：
   * 上午/下午
   * 月中几号
   * 每周时间
   * 年中哪天
   * 每天时间
   * 分钟
   * 月份
   * 季度
   * 工作日/周末
   * 年
* 一些基于路径的维度，包括：
   * 除“登入页面”之外的所有登入维度
   * 除“退出页面”和“退出链接”之外的所有退出维度
   * 点击深度
   * 回访频度
   * 发生事件之前逗留的时间
   * 页面逗留时间 — 分段统计
   * 每次访问逗留时间 — 分段统计
   * 访问深度
* 所有搜索页面排名
* 层次结构变量
* 点击类型
* 页面未找到（可用作维度；不支持分段）
* 付费搜索
* 单页面访问量
* 跟踪选择退出的原因
* 美国各州

### 不支持的指标

* 一些基于路径的指标，包括：
   * 跳出次数
   * 登录
   * 退出
   * 重新载入
   * 单次存取
   * “逗留时间”指标
