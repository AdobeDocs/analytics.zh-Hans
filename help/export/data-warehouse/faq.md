---
title: data warehouse常见问题解答
description: data warehouse的常见问题解答。
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 9%

---


# data warehouse常见问题解答

data warehouse的常见问题解答。

## 当我在创建请求时使用粒度下拉列表时，我希望日期采用什么格式？

在Data warehouse请求中应用粒度时，“日期”列将添加到报表。 日期格式会根据所选的粒度发生变化。

| 粒度 | 格式 | 示例 |
| --- | --- | --- |
| 每小时 | `mmmm d, yyyy` 小时 `H` | 1月1日， 20XX，小时0 |
| 每日 | `mmmm d, yyyy` | 2020年1月1日 |
| 每周 | 周 `w, yyyy` | 第1周， 20XX |
| 每月 | `mmmm yyyy` | 1月20日XX |
| 每季 | `q` 季度 `yyyy` | 第1季度20XX |
| 每年 | `yyyy` | 20XX |

## 作为维的细分如何在Data warehouse中工作？

在Data warehouse中将区段用作维时，报表会返回包含或 `"0"` 以下列 `"1"`:

* **`"0"`**:维项目不符合区段的条件。
* **`"1"`**:维项目符合区段的条件。
