---
title: Data Warehouse 中的组件支持
description: 了解 Data Warehouse 中有哪些其他维度和量度可用，以及哪些维度和量度不受支持。
translation-type: ht
source-git-commit: 00d4d59cb4c922b54a97ef7000e294ef3bf61f20

---


# Data Warehouse 中的组件支持

Data Warehouse 的独特处理架构，可支持某些通常情况下在 Adobe Analytics 的其他功能中不可用的组件。由于其独特的架构，某些组件无法用于报表或区段。使用此页面可了解哪些组件可以使用，哪些组件不可使用。

## Data Warehouse 的特有组件

某些维度和量度在 Data Warehouse 中可用，但无法用于 Adobe Analytics 中的其他功能。

### 专门支持的维度

* Experience Cloud ID：对于使用 Experience Cloud ID 服务 (ECID) 的实施，由两个 64 位数字拼接而成的 128 位数字，占据了 19 位数。
* 页面 URL：点击发生的页面 URL。
* 购买 ID：购买的唯一标识符，使用 purchaseID 变量设置。
* 访客 ID：提供访客的唯一标识符。此值与数据馈送中的 `visid_high` 和 `visid_low` 列的拼接值相同。有关更多信息，请参阅“数据馈送”下的[数据列引用](../analytics-data-feed/c-df-contents/datafeeds-reference.md)。

### 专门支持的量度

* 访问次数：在 Data Warehouse 上下文中，此量度不包括非永久性 Cookie 访问。
* 访问 - 所有访客数：在 Data Warehouse 上下文中，此量度与 Adobe Analytics 内其他工具中的“访问次数”量度更接近。

## Data Warehouse 中不支持的组件

Data Warehouse 不支持某些维度和量度。

> [!NOTE]如果 Data Warehouse 不支持某个维度或量度，则也不支持使用这些维度或量度的区段。在创建或编辑区段时，请务必检查产品兼容性。

### 不支持的维度

* 一些基于时间的维度，包括：
   * 上午/下午
   * 日期
   * 每周时间
   * 每年的某一天
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
   * 页面逗留时间 - 分段统计
   * 每次访问逗留时间 - 分段统计
   * 访问深度
* 所有搜索页面排名
* 层次结构变量
* 点击类型
* 找不到页面（可用作维度；不支持分段）
* 付费搜索
* 单页面访问量
* 跟踪选择退出的原因
* 美国各州

### 不支持的量度

* 一些基于路径的指标，包括：
   * 跳出次数
   * 登录
   * 退出
   * 重新载入
   * 单次存取
   * “逗留时间”量度
