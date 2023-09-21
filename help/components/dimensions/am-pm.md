---
title: 上午/下午
description: 确定点击是否发生在上午或下午时刻。
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 86%

---

# 上午/下午

“上午/下午” [维度](overview.md) 提供点击发生在上午还是下午时刻的分析。 点击时间基于[报表包所在时区](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)。

## 使用数据填充此维度

此维度可开箱即用。它没有任何要更改的设置。它的唯一依赖项是报表包中的时区，时区决定着哪些时刻是上午以及哪些时刻是下午。

## 维度项目

此维度始终只包含两个维度项目：`"AM"` 和 `"PM"`。维度项目 `"AM"` 适用于从午夜 12:00 到上午 11:59 的所有点击，而维度项目 `"PM"` 则适用于从中午 12:00 到晚上 11:59 的所有点击。
