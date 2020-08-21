---
title: 上午/下午
description: 确定点击是否发生在上午或下午时刻。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 70%

---


# 上午/下午

“AM/PM”维度提供关于点击是发生在上午还是下午时刻的洞察信息。点击时间基于[报表包所在时区](/help/admin/admin/general-acct-settings-admin.md)。

## 使用数据填充此维度

此维度可开箱即用。它没有任何要更改的设置。它的唯一依赖项是报表包中的时区，时区决定着哪些时刻是上午以及哪些时刻是下午。

## Dimension项

This dimension always contains exactly two dimension items: `"AM"` and `"PM"`. The dimension item `"AM"` applies to all hits from 12:00 AM to 11:59 AM, while the dimension item `"PM"` applies to all hits from 12:00 PM to 11:59 PM.
