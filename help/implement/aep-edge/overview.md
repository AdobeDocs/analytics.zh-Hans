---
title: 使用 Adobe Experience Platform Edge 实施 Adobe Analytics
description: 在 Adobe Analytics 中使用源自 Experience Platform 的 XDM 数据概述
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/-WWT7-dW4vo8g0DXtuQK9E30DktJ2yjzbc6w69oxJnc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 596
ht-degree: 100%

---

# 使用 Adobe Experience Platform Edge Network 实施 Adobe Analytics

Adobe Experience Platform Edge Network 允许您将发送到多个产品的数据发送到一个集中的位置。 Edge Network 将适当的信息转发给所需的产品。 此概念允许您合并实施工作，尤其是在跨多个数据解决方案的情况下。 Adobe Analytics 是可以用 Edge Network 向其发送数据的一项产品。

## Adobe Analytics 如何处理 Edge Network 数据

由于发送到 Edge Network 的数据与 AppMeasurement 数据的运行方式不同，因此 Edge Network 负载决定了 Adobe Analytics 如何处理点击。 更多信息请参阅 [Adobe Analytics 中的 Edge Network 事件类型](hit-types.md)。

发送到 Adobe Experience Platform Edge Network 的数据可遵循三种格式：**XDM 对象**、**数据对象**&#x200B;和&#x200B;**上下文数据**。 当数据流将数据送到 Adobe Analytics 时，数据会转换成 Adobe Analytics 可以处理的格式。

## `xdm` 对象

符合您基于 [XDM](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/home)（体验数据模型）创建的架构。 XDM 可让您灵活地将字段定义为事件的一部分。 如果要使用 Adobe Analytics 特有的预定义架构，可将 [Adobe Analytics ExperienceEvent 架构字段组](https://experienceleague.adobe.com/cn/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)添加到您的架构中。 添加后，您就可以使用 Web SDK 中的 `xdm` 对象填充这个架构，以将数据发送到报告包。 数据到达 Edge Network 后，会将 XDM 对象转换为 Adobe Analytics 可以理解的格式。

有关 XDM 字段的完整参考以及它们如何映射到 Adobe Analytics 变量，请参阅[映射到 Adobe Analytics 的 XDM 对象变量](xdm-var-mapping.md)。

>[!TIP]
>
>如果您计划未来迁移到 [Customer Journey Analytics](https://experienceleague.adobe.com/cn/docs/analytics-platform/using/cja-landing)，Adobe 建议不要使用 Adobe Analytics 架构字段组。 Adobe 建议[创建您自己的架构](https://experienceleague.adobe.com/cn/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect)，然后使用数据流映射填充所需的 Analytics 变量。 当您准备好迁移到 Customer Journey Analytics 时，此策略不会将您锁定在 prop 和 eVar 架构中。

## `data` 对象

如果不使用 `xdm` 对象，您可以改用 `data` 对象。 此数据对象针对当前使用 AppMeasurement 的实施，这使升级到 Web SDK 更加容易。 Edge Network 会检测 Adobe Analytics 特有的字段的存在，而无需符合某个架构。

有关数据对象字段的完整参考以及它们如何映射到 Analytics 变量，请参阅[映射到 Adobe Analytics 的数据对象变量](data-var-mapping.md)。

## 上下文数据变量

以您希望的任何格式将数据发送到 Edge Network。 任何未自动映射到 `xdm` 或 `data` 对象字段的字段都作为[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)被包含发送到 Adobe Analytics。 然后，您必须使用[处理规则](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)将所需字段映射到其相应的 Analytics 变量。

例如，如果您有一个类似这样的自定义 XDM 架构：

```json
{
  "xdm": {
    "key": "value",
    "animal": {
      "species": "Raven",
      "size": "13 inches"
    },
    "array": [
      "v0",
      "v1",
      "v2"
    ],
    "objectArray":[{
      "ad1": "300x200",
      "ad2": "60x240",
      "ad3": "600x50"
    }]
  }
}
```

那么这些字段将成为您在处理规则界面中可用的上下文数据键：

```javascript
a.x.key // value
a.x.animal.species // Raven
a.x.animal.size // 13 inches
a.x.array.0 // v0
a.x.array.1 // v1
a.x.array.2 // v2
a.x.objectarray.0.ad1 // 300x200
a.x.objectarray.1.ad2 // 60x240
a.x.objectarray.2.ad3 // 600x50
```

一个给定的上下文数据变量负载（包括键和值）最大为 32 KB。 您可以通过调整相关字段来减小此负载的大小，以便 Adobe Analytics 在 [`xdm`](xdm-var-mapping.md) 或 [`data`](data-var-mapping.md) 对象中能够识别这些字段。
