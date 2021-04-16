---
description: 有关数据馈送的常见问题解答
keywords: 数据馈送；作业；预列；后列；区分大小写
title: 数据馈送常见问题解答
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
translation-type: tm+mt
source-git-commit: c6d4095fdf86be52c7921aed84b9229ac3b27f82
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 58%

---

# 数据馈送常见问题解答

有关数据馈送的常见问题解答。

## 带 `post_` 前缀的列和不带 `post_` 前缀的列之间有何差异？

不带 `post_` 前缀的列所包含的数据与发送到数据收集的数据完全相同。而带 `post_` 前缀的列包含的是处理后的值。可更改值的示例包括变量持久性、处理规则、VISTA 规则、货币转换或 Adobe 应用的其他服务器端逻辑。Adobe 建议尽可能使用带 `post_` 前缀的列。

如果某列不带 `post_` 前缀（例如 `visit_num`），则可能会将该列视为后处理列。

## 数据馈送如何处理大小写问题？

在 Adobe Analytics 中，大多数变量在用于报告时都会被视为不区分大小写。例如，“snow”、“Snow”、“SNOW”和“sNow”全都会被视为相同的值。在数据馈送中会保留区分大小写。

如果您在非后处理列和后处理列中看到同一个值的不同大小写（例如，前处理列中的“snow”与后处理列中的“Snow”），则您的实施将在整个网站中同时使用大写值和小写值。后处理列中的不同大小写是在之前传递的，并被存储在虚拟 Cookie 中，或者是在大致相同的时间针对该报表包处理的。

## 数据馈送中是否包含按 Admin Console 机器人规则过滤的机器人？

数据馈送中不包含按 [Admin Console 机器人规则](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/admin-tools/bot-removal/bot-removal.html)过滤的机器人。

## 为什么在`event_list`或`post_event_list`数据馈送列中看到多个`000`值？

某些电子表格编辑器（尤其是Microsoft Excel）会自动舍入大数字。 `event_list`列包含许多逗号分隔的数字，有时会导致Excel将其视为大数字。 它将最后几位数字舍入为`000`。

Adobe建议不要在Microsoft Excel中自动打开`hit_data.tsv`文件。 请改用Excel的“导入数据”对话框，并确保所有字段都被视为文本。

## 为什么无法从超过7天的数据中提取“每小时”文件？

对于超过7天的数据，将一天的“每小时”文件合并为一个“每日”文件。

示例：将在2021年3月9日创建新的数据馈送，2021年1月1日至3月9日的数据将以“每小时”的形式提供。 但是，2021年3月2日之前的“每小时”文件将合并为一个“每日”文件。 您只能从创建日期后不到7天的数据中提取“每小时”文件。 在这种情况下，从3月2日到3月9日。
