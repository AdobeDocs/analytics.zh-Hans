---
title: 工作日/周末
description: 确定点击发生在工作日还是周末。
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
TQID: https://experienceleague.adobe.com/9TJv-49ub1zHsgEGtBeoJVoHhsBktlOr7QhmgLdLRSo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 49%
---
# 工作日/周末

“工作日/周末”[维度](overview.md)可提供insight时间，以决定点击是发生在工作日（星期一至星期五）还是周末（星期六至星期日）。 点击时间基于[报表包所在时区](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)。

## 使用数据填充此维度

此维度从每次点击的时间戳派生；没有要设置的变量。 它的唯一依赖项是报表包的时区，该时区确定每次点击在一周中的哪一天。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（派生自点击时间戳） |
| **Web SDK / XDM字段** | 无（派生自点击时间戳） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 点击 |

## 维度项目

此维度始终只包含两个维度项目：`"Weekday"` 和 `"Weekend"`。 维度项目 `"Weekday"` 适用于星期一到星期五的所有点击，而维度项目 `"Weekend"` 适用于星期六和星期日的所有点击。
