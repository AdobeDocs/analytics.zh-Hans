---
title: 上午/下午
description: 确定点击是否发生在上午或下午时刻。
translation-type: ht
source-git-commit: cd2225ec00190af6b616f313b419935c4f8dfafd
workflow-type: ht
source-wordcount: '117'
ht-degree: 100%

---


# 上午/下午

“AM/PM”维度提供关于点击是发生在上午还是下午时刻的洞察信息。点击时间基于[报表包所在时区](/help/admin/admin/general-acct-settings-admin.md)。

## 使用数据填充此维度

此维度可开箱即用。它没有任何要更改的设置。它的唯一依赖项是报表包中的时区，时区决定着哪些时刻是上午以及哪些时刻是下午。

## 维度项目

此维度始终只包含两个维度项目：`"AM"` 和 `"PM"`。维度项目 `"AM"` 适用于从午夜 12:00 到上午 11:59 的所有点击，而维度项目 `"PM"` 则适用于从中午 12:00 到晚上 11:59 的所有点击。
