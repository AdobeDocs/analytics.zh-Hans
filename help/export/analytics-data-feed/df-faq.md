---
description: 有关数据馈送的常见问题解答
keywords: Data Feed;job;pre column;post column;case sensitivity
solution: Analytics
title: 数据源常见问题解答
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# 数据源常见问题解答

有关数据馈送的常见问题解答。

## 带前缀的列和不带前缀 `post_` 的列之间有何差 `post_` 异？

没有前缀 `post_` 的列包含的数据与发送到数据收集时完全相同。 带前缀 `post_` 的列包含处理后的值。 可以更改值的示例包括变量持久性、处理规则、VISTA规则、货币兑换或Adobe应用的其他服务器端逻辑。 Adobe建议尽可能 `post_` 使用列的版本。

If a column does not contain a `post_` version (for example, `visit_num`), then the column can be considered a post column.

## 数据服务如何处理区分大小写的问题？

在Adobe Analytics中，大多数变量在报告时都会被视为不区分大小写。 例如，“snow”、“Snow”、“SNOW”和“sNow”都被视为相同的值。 在数据源中保留区分大小写。

如果您看到非帖子和帖子列之间相同值的不同大小写变体（例如，前列中的“snow”，后列中的“Snow”），则您的实施将在整个站点中同时使用大小写值。 后处理列中的不同大小写是在之前传递的，并被存储在虚拟 Cookie 中，或者是在大致相同的时间针对该报表包处理的。