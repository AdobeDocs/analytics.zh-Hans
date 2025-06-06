---
description: 介绍如何使用数据馈送计算常见量度。
keywords: 数据馈送;作业;量度;前处理列;后处理列;机器人;日期过滤;事件字符串;常见;公式
title: 计算量度
feature: Data Feeds
exl-id: f9b0d637-7a6e-416a-adff-3c7e533bfac7
source-git-commit: adee2f1013cfd2ae231e3133b5a5327b8792bd16
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 76%

---

# 使用数据馈送计算常用量度

介绍如何使用数据馈送计算常见量度。

>[!NOTE]
>
>通常会从Analysis Workspace中排除的点击将包含在数据馈送中。 如果查询相关，请考虑添加以下条件：
>
>* **`exclude_hit`**： Analysis Workspace仅包含`exclude_hit = 0`的数据。
>* **`customer_perspective`**： Analysis Workspace仅包含`customer_perspective = 0`的数据，除非您使用的虚拟报表包包含移动设备后台点击量。
>* **`hit_source`**：数据源中的数据可能包含原始数据与Analysis Workspace之间的差异。 如果要从数据源排除点击，请排除`hit_source = 5,7,8,9`的所有行。

## 页面查看

1. 计数值在 `post_pagename` 或 `post_page_url` 中的行数。

## 发生次数

1. 计算总行数。

## 访问

1. 拼接 `post_visid_high`、`post_visid_low`、`visit_num` 和 `visit_start_time_gmt`。
1. 计算唯一值的数量。

>[!TIP]
>
>Internet 违规、系统违规或使用自定义访客 ID 极少数情况下会将相同的 `visit_num` 值用于不同的访问。虽然可选，但在计算访问次数时使用`visit_start_time_gmt`以确保计算这些访问次数。

## 访客

Adobe用于识别独特访客的所有方法(自定义访客ID、Experience Cloud ID服务等)最终都会计算为`post_visid_high`和`post_visid_low`中的值。 无论以何种方式标识为独特访客，均可使用这两列的拼接来作为标识独特访客的标准。如果您想了解 Adobe 使用哪种方法来识别独特访客，请使用列 `post_visid_type`。

1. 拼接 `post_visid_high` 和 `post_visid_low`。
2. 计算唯一值的数量。

## 自定义、下载或退出链接

1. 计算符合以下条件的行数：
   * `post_page_event = 100`（自定义链接）
   * `post_page_event = 101`（下载链接）
   * `post_page_event = 102`（退出链接）

## 自定义事件

所有量度将作为以逗号分隔的整数计入 `post_event_list` 列中。使用 `event.tsv` 可将这些数值与所需事件进行匹配。例如，`post_event_list = 1,200` 表示点击包含购买事件和自定义事件 1。

1. 计算事件查询值在 `post_event_list` 中出现的次数。

## 逗留时间

首先，必须按访问对点击进行分组，然后按照访问中的点击数进行排序。

1. 拼接 `post_visid_high`、`post_visid_low`、`visit_num` 和 `visit_start_time_gmt`。
2. 按此拼接值排序，然后按 `visit_page_num` 进行二级排序。
3. 如果某个点击不是某次访问中的最后一个点击，则从后续点击的 `post_cust_hit_time` 值中减去 `post_cust_hit_time` 值。
4. 此数字是该次点击的逗留时间（以秒为单位）。可应用过滤器来重点关注维度项目或事件。

## 订单数、件数和收入

如果点击的 `currency` 值与报表包的货币不匹配，则使用当天的兑换率换算。`post_product_list` 列会使用已转换的货币值，因此该列中的所有点击将使用相同的货币。

1. 排除 `duplicate_purchase = 1` 的所有行。
2. 仅包括 `event_list` 包含购买事件的行。
3. 解析 `post_product_list` 列以提取所有价格数据。`post_product_list` 列的格式与 `s.products` 变量相同。
4. 计算所需的量度：
   * 计算行数以计算“订单数”
   * 计算产品字符串中 `quantity` 数量的总和以计算“件数”
   * 计算产品字符串中 `price` 数量的总和以计算“收入”
