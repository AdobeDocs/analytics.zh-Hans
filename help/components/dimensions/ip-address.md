---
title: IP 地址
description: 每次点击发送的IP地址，可在Data Warehouse中使用。
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 108
ht-degree: 17%

---

# IP 地址

“IP地址”[维度](overview.md)列出了每次点击发送的IP地址。

>[!IMPORTANT]
>
>此维度只能在 Data warehouse 中使用。

## 使用数据填充此维度

AppMeasurement自动从每个图像请求的HTTP标头中收集IP地址。 它对应于数据馈送中的`ip`列。 有关详细信息，请参阅[数据列引用](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)。

如果在报表包的[常规帐户设置](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)中启用了[!UICONTROL IP模糊处理]，则Analytics中的所有位置（包括Data Warehouse）都会对IP地址进行模糊处理或将其删除。

## 维度项目

Dimension项目包括从中发送点击的IP地址。
