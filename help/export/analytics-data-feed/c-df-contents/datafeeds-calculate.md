---
description: 介绍如何使用数据馈送计算常见量度。
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
title: 计算量度
topic: Reports and analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用数据服务计算常见指标

介绍如何使用数据馈送计算常见量度。

> [!IMPORTANT] 通常从Adobe Analytics中排除的点击会包含在数据源中。 使用 `exclude_hit > 0` 可删除原始数据查询中被排除的点击。 数据源数据也包含在数据馈送中。 如果要排除数据源，请排除所有包含的行 `hit_source = 5,7,8,9`。

## 页面查看

1. 计数值位于或中的行 `post_pagename` 数 `post_page_url`。

## 访问

1. 连接 `post_visid_high`、 `post_visid_low`、 `visit_num`和 `visit_start_time_gmt`。
1. 计算唯一值数。

> [!NOTE] Internet违规、系统违规或使用自定义访客ID很少对不同访问使 `visit_num` 用相同的值。 在计 `visit_start_time_gmt` 数访问时使用，以确保计数这些访问。

## 访客

Adobe用于识别唯一访客的所有方法（自定义访客ID、Experience Cloud ID服务等）都最终计算为和中的 `post_visid_high` 值 `post_visid_low`。 这两列的串连可用作标识唯一访客的标准，而不管这些访客是如何被标识为唯一访客的。 如果您想了解Adobe使用哪种方法来识别唯一访客，请使用该列 `post_visid_type`。

1. 连接 `post_visid_high` 和 `post_visid_low`。
2. 计算唯一值数。

## 自定义、下载或退出链接

1. 计算以下位置的行数：
   * `post_page_event = 100` 对于自定义链接
   * `post_page_event = 101` 用于下载链接
   * `post_page_event = 102` 对于退出链接

## 自定义事件

所有度量在列中以逗号 `post_event_list` 分隔的整数计数。 使用 `event.tsv` 将数字值与所需事件相匹配。 例如，指 `post_event_list = 1,200` 示点击包含购买事件和自定义事件1。

1. Count the number of times the event lookup value appears in `post_event_list`.

## 逗留时间

首先必须按访问对点击进行分组，然后根据访问中的点击编号进行排序。

1. 连接 `post_visid_high`、 `post_visid_low`、 `visit_num`和 `visit_start_time_gmt`。
2. 按此连接的值排序，然后按应用次排序 `visit_page_num`。
3. 如果点击不是访问中的最后一个，则从后 `post_cust_hit_time` 续点击的值中减去该 `post_cust_hit_time` 值。
4. 此数字是点击所花费的时间（以秒为单位）。 可应用筛选器以集中处理维值或事件。

## 订单、件数和收入

如果点击值 `currency` 与报表包的货币不匹配，则使用当天的兑换率换算。 该列使 `post_product_list` 用已转换的货币值，因此所有点击在此列中都使用相同的货币。

1. Exclude all rows where `duplicate_purchase = 1`.
2. 仅包含包含购 `event_list` 买事件的行。
3. 解析列 `post_product_list` 以提取所有价格数据。 列 `post_product_list` 的格式与变量相 `s.products` 同。
4. 计算所需的度量：
   * 计算行数以计算“订单”
   * 计算产品字符串 `quantity` 中的数量总和以计算单位
   * 总和产品字 `price` 符串中的数量以计算收入
