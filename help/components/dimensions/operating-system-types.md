---
title: 操作系统类型
description: 操作系统，不考虑版本。
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
TQID: https://experienceleague.adobe.com/onZ7Wt7A44gd42hqmjqYHL7OF6VtBke1NDgu1tsnMIg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 137
ht-degree: 55%

---

# 操作系统类型

“操作系统类型”[维度](overview.md)显示访客使用的总体操作系统，而不考虑特定版本。 此维度不仅有助于了解最常用的特定操作系统和版本，而且还有助于了解访客使用的典型操作系统平台。

## 使用数据填充此维度

此维度引用 Adobe 内部的一个查找表。 查找值基于图像请求中的 `User-Agent` HTTP 标头。 Adobe与[DeviceAtlas](https://deviceatlas.com/)合作，共同在用户代理和操作系统类型之间维护查找。

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)时启用[!UICONTROL 设备查找]。

## 维度项目

Dimension项目包括使用的操作系统类型。 示例包括 `"Microsoft Windows"`、`"Apple Macintosh"`、`"Google Android"` 和 `"Apple iOS"`。
