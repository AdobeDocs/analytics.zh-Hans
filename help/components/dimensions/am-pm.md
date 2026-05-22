---
title: 上午/下午
description: 确定点击是否发生在上午或下午时刻。
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 121
ht-degree: 64%

---

# 上午/下午

“AM/PM”[维度](overview.md)提供点击发生在上午还是下午时刻的insight。 点击时间基于[报表包所在时区](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)。

## 使用数据填充此维度

此维度可开箱即用。 它没有任何要更改的设置。 它的唯一依赖项是报表包中的时区，时区决定着哪些时刻是上午以及哪些时刻是下午。

## 维度项目

此维度始终只包含两个维度项目：`"AM"` 和 `"PM"`。 维度项`"AM"`适用于从午夜12:00到上午11:59的所有点击，而维度项`"PM"`适用于从正午12:00到下午11:59的所有点击。
