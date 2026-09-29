---
title: 上午/下午
description: 确定点击是否发生在上午或下午时刻。
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: 'https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 33%
---
# 上午/下午

“AM/PM”[维度](overview.md)提供点击发生在上午还是下午时刻的insight。 点击时间基于[报表包所在时区](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)。

## 使用数据填充此维度

此维度从每次点击的时间戳派生；没有要设置的变量。 它的唯一依赖项是报表包的时区，时区决定着哪些小时是上午以及哪些小时是下午。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（派生自点击时间戳） |
| **Web SDK / XDM字段** | 无（派生自点击时间戳） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 点击 |

## 维度项目

此维度始终只包含两个维度项目：`"AM"` 和 `"PM"`。 维度项`"AM"`适用于从午夜12:00到上午11:59的所有点击，而维度项`"PM"`则适用于从正午12:00到晚上11:59的所有点击。
