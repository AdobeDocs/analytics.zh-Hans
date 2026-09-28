---
title: 操作系统
description: 访客的操作系统。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
TQID: 'https://experienceleague.adobe.com/WM6GQ-AhLmtudRWXF6lOez6DaVxMBU3rSaEb2UdsXdc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 34%
---
# 操作系统

“操作系统”[维度](overview.md)显示访客使用的操作系统和版本。 如果您的 Web 资产上具有特定于操作系统的功能，则此维度可以帮助您了解最常用的操作系统。

## 使用数据填充此维度

Adobe从`User-Agent` HTTP标头派生此维度，并将其与Adobe与[DeviceAtlas](https://deviceatlas.com/)合作维护的内部查找表进行匹配。 没有要设置的变量。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（派生自用户代理） |
| **Web SDK / XDM字段** | 无（派生自用户代理） |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 不适用 |
| **持久性** | 不适用 |

* 对于AppMeasurement实施，此维度可开箱即用。
* 对于Web SDK实施，请在[配置数据流](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)时启用[!UICONTROL 设备查找]。

## 维度项目

维度项目包括访客使用的操作系统。 示例包括 `"Windows 10"`、`"OS X 10.15.7"` 和 `"Android 9"`。

## 跟踪准确的操作系统版本

随着行业转向客户端提示，一些操作系统版本可能会出现混淆。 例如，如果您不收集高熵客户端提示，“Windows 10”和“Windows 11”都可以分组到“Windows 10”下。 有关详细信息，请参阅技术说明指南中的[客户端提示](/help/technotes/client-hints.md)。
