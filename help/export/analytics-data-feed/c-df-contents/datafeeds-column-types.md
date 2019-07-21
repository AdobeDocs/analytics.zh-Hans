---
description: 预处理列包含发送到数据收集的数据。后处理列包含处理后的值。
keywords: 数据馈送；工作；pre column；post column；区分大小写
seo-description: 预处理列包含发送到数据收集的数据。后处理列包含处理后的值。
seo-title: 预发布列和帖子列
solution: Analytics
title: 预发布列和帖子列
topic: Reports & Analytics
uuid: a415327b-6151-4d08-b8 b9-5aa2348 eb0 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 预发布列和帖子列

预处理列包含发送到数据收集的数据。后处理列包含处理后的值。

例如，变量持久性、处理规则、VISTA 规则和货币转化可能会更改后处理列中出现的为变量记录的最终值。对于大多数计算，您需要使用后处理列，除非应用自定义业务逻辑（例如，应用自定义公式以确定属性）。

如果某列不包含预处理或后处理版本（例如 `visit_num`），则可能会将该列视为后处理列。Columns prefixed with " `pre_`" typically contain data that was populated by Adobe and not sent by your implementation. For example, `pre_browser` is populated by Adobe, but `evar1` is populated by your implementation. Both of these columns have a " `post_`" column ( `post_browser`, `post_evar1`), which contains the value used by reporting.

## 值中区分大小写的情况 {#section_F979E099BFAB4AFEBEA2D7E228963CE8}

大部分 Analytics 变量在出于报告目时不区分大小写，这意味着不同的大小写变体都被视为相同的值（例如，“snow”、“Snow”、“SNOW”和“sNow”都被视为同一个值）。但是为了便于显示，还是保留了区分大小写，因为大部分客户都希望能够发送夹杂大小写字符的报表。

在处理数据馈送时，您可以为了便于比较而采用纯小写值，即使您可能出于显示目的而希望保留大小写。

如果您发现同一个值在预处理列和后处理列之间存在不同的大小写变体（例如，预处理列中显示“snow”，后处理列中则显示“Snow”），这表示您正在您的网站中同时传递同一个值的大写和小写版本。后处理列中的不同大小写是在之前传递的，并被存储在虚拟 Cookie 中，或者是在大致相同的时间针对该报表包处理的。例如：

点击 1：s.list1="Tabby,Persian,Siamese”;

点击 2：s.list1=“tabby,persian,siamese”;

当点击 2 在数据馈送中报告时，预处理列将包含传递的准确大小写 (tabby,persian,siamese)，但是点击 1 中的值可能持续存在于该访问，并且将在后处理列中报告（将为 Tabby,Persian,Siamese），因为在执行不区分大小写比较时，点击 1 和点击 2 包含完全相同的值。
