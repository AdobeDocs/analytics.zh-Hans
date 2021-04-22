---
title: Data Warehouse 常见问题解答
description: Data Warehouse 的常见问题解答。
exl-id: 51c3ba17-a8b2-4030-9521-355ebbbfcd0d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '131'
ht-degree: 100%

---

# Data Warehouse 常见问题解答

Data Warehouse 的常见问题解答。

## 如果在创建请求时使用粒度下拉菜单，日期将会使用什么格式？

在 Data Warehouse 请求中应用粒度时，报表中将添加“日期”列。根据所选粒度，日期格式会发生变化。

| 粒度 | 格式 | 示例 |
| --- | --- | --- |
| 每小时 | `mmmm d, yyyy` 小时 `H` | 20xx 年 1 月 1 日，第 0 小时 |
| 每日 | `mmmm d, yyyy` | 20xx 年 1 月 1 日 |
| 每周 | 周 `w, yyyy` | 20xx 年第 1 周  |
| 每月 | `mmmm yyyy` | 20xx 年 1 月 |
| 每季 | `q` 季度 `yyyy` | 20xx 年 1 季度 |
| 每年 | `yyyy` | 20XX |

## 在 Data Warehouse 中，区段如何作为维度使用？

在 Data Warehouse 中使用区段作为维度时，报表返回包含 `"0"` 或 `"1"` 的列：

* **`"0"`**：维度项不符合区段的标准。
* **`"1"`**：维度项符合区段的标准。
