---
description: 有关数据馈送的常见问题解答
keywords: Data Feed;job;pre column;post column;case sensitivity
title: 数据馈送常见问题解答
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 66%

---


# 数据馈送常见问题解答

有关数据馈送的常见问题解答。

## 带 `post_` 前缀的列和不带 `post_` 前缀的列之间有何差异？

不带 `post_` 前缀的列所包含的数据与发送到数据收集的数据完全相同。而带 `post_` 前缀的列包含的是处理后的值。可更改值的示例包括变量持久性、处理规则、VISTA 规则、货币转换或 Adobe 应用的其他服务器端逻辑。Adobe 建议尽可能使用带 `post_` 前缀的列。

如果某列不带 `post_` 前缀（例如 `visit_num`），则可能会将该列视为后处理列。

## 数据馈送如何处理大小写问题？

在 Adobe Analytics 中，大多数变量在用于报告时都会被视为不区分大小写。例如，“snow”、“Snow”、“SNOW”和“sNow”全都会被视为相同的值。在数据馈送中会保留区分大小写。

如果您在非后处理列和后处理列中看到同一个值的不同大小写（例如，前处理列中的“snow”与后处理列中的“Snow”），则您的实施将在整个网站中同时使用大写值和小写值。后处理列中的不同大小写是在之前传递的，并被存储在虚拟 Cookie 中，或者是在大致相同的时间针对该报表包处理的。

## 数据馈送中是否包含按管理控制台机器规则过滤的机器人程序？

数据馈送不包括按Admin Console机器规则筛 [选的机器人程序](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html)。

## 为什么在或数 `000` 据馈送列 `event_list` 中 `post_event_list` 看到多个值？

某些电子表格编辑器，特别是Microsoft Excel自动舍入大数字。 该 `event_list` 列包含许多以逗号分隔的数字，有时会导致Excel将其视为大数字。 它将最后几个数字舍入为 `000`。

Adobe建议不要在Microsoft `hit_data.tsv` Excel中自动打开文件。 请改用Excel的“导入数据”对话框，并确保所有字段均被视为文本。
