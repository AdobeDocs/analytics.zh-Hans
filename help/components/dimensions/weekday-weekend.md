---
title: 工作日/周末
description: 确定点击发生在工作日还是周末。
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 80%

---

# 工作日/周末

“工作日/周末” [维度](overview.md) 提供点击发生在工作日（星期一至星期五）还是周末（星期六至星期日）的分析。 点击时间基于[报表包所在时区](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)。

## 使用数据填充此维度

此维度可开箱即用于所有实施。如果报表包包含数据，则此维度有效。

## 维度项目

此维度始终只包含两个维度项目：`"Weekday"` 和 `"Weekend"`。维度项目 `"Weekday"` 适用于星期一到星期五的所有点击，而维度项目 `"Weekend"` 适用于星期六和星期日的所有点击。
