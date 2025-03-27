---
title: Data Warehouse中的组件支持
description: 了解 Data Warehouse 中有哪些其他维度和指标可用以及不支持哪些维度和指标。
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
source-git-commit: 527a9d5cdcb1ceb32073e2d444b892c0183394c1
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 45%

---

# Data Warehouse 中的组件支持

Data Warehouse架构中的独特处理允许使用某些在Adobe Analytics的其他功能中通常不可用的组件。 由于其独特的架构，某些组件无法用于报表或区段。使用此页面可了解哪些组件可以使用，哪些组件不可使用。

## Data Warehouse 的特有组件

在Adobe Analytics中使用其他功能时，某些可在Data Warehouse中使用的维度和量度不可用。

### 专门支持的维度

* **Experience Cloud ID**：对于使用Experience Cloud ID服务(ECID)的实施，由两个64位数字拼接而成的128位数字，填充到19位数。
* **页面URL**：点击发生的页面URL。
* **购买ID**：购买的唯一标识符，使用purchaseID变量设置。
* **访客ID**：提供访客的唯一标识符。 此值与数据馈送中的 `visid_high` 和 `visid_low` 列的拼接值相同。有关更多信息，请参阅“数据馈送”下的[数据列引用](../analytics-data-feed/c-df-contents/datafeeds-reference.md)。

### 专门支持的指标

* **访问次数**：在Data Warehouse上下文中，此量度不包括非永久性Cookie访问。
* **访问次数 — 所有访客**：在Data Warehouse上下文中，此指标与Adobe Analytics内其他工具中的“访问次数”指标更接近。

## Data Warehouse 中不支持的组件

Data Warehouse 不支持某些维度和指标。

>[!NOTE]
>
>如果 Data Warehouse 不支持某个维度或指标，则也不支持使用这些维度或指标的区段。在创建或编辑区段时，请务必检查产品兼容性。

### 不支持的维度

* 上午/下午
* 一些基于路径的维度，包括：
   * 除“登入页面”之外的所有登入维度
   * 除“退出页面”和“退出链接”之外的所有退出维度
   * 点击深度
   * 回访频度
   * 发生事件之前逗留的时间
   * 页面逗留时间 — 分段统计
   * 每次访问逗留时间 — 分段统计
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
* 参与率量度（如[构建“参与率”量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md)中所述）

### 以不同方式支持的维度（非标准日期格式）

支持以下基于时间的维度：

* 年
* 季度
* 月
* 周
* 日
* 小时
* 分钟

但是，使用这些维度时，日期输出不是标准输出。

在Data Warehouse中计算日期输出时，请考虑以下事项：

* 日期维度以下列格式显示： `1YYMMDDHHMM`

* 年(YY)被1900所抵消。 这意味着您将`1900`添加到日期字段的前3个值。

  例如，如果Data Warehouse中“日期范围周”字段的值为`1250901`，您应添加1900到125，这会导致2025年。

* 所有月份都从零开始，1月份由00表示，2月份由01表示，依此类推，如下所示：

   * 00:1月
   * 01:2月
   * 02:3月
   * 03:4月
   * 04： 5月
   * 05:6月
   * 06:7月
   * 07:8月
   * 08:9月
   * 09:10月
   * 10日：11月
   * 11日：12月

  例如，如果Data Warehouse中“日期范围周”字段的值为`1250901`，则月份表示为09，表示为10月。




## Data Warehouse中的区段作为维度

在 Data Warehouse 中使用区段作为维度时，报表返回包含 `"0"` 或 `"1"` 的列：

* **`"0"`**：维度项不符合区段的标准。
* **`"1"`**：维度项符合区段的标准。
