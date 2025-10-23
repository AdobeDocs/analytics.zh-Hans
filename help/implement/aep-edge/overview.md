---
title: 使用 Adobe Experience Platform Edge 实施 Adobe Analytics
description: 在 Adobe Analytics 中使用源自 Experience Platform 的 XDM 数据概述
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9845f1bc73b6cf5fd932c6896a50379ddd008c20
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 15%

---

# 使用 Adobe Experience Platform Edge Network 实施 Adobe Analytics

Adobe Experience Platform Edge Network 允许您将发送到多个产品的数据发送到一个集中的位置。 Edge Network 将适当的信息转发给所需的产品。 此概念允许您整合实施工作，尤其是跨多个数据解决方案进行整合。 Adobe Analytics是可以使用Edge Network将数据发送到的产品之一。

## Adobe Analytics 处理 Edge Network 数据的方式

由于发送到Edge Network的数据与AppMeasurement数据的操作方式不同，因此Edge Network有效负载决定了Adobe Analytics如何处理点击。 有关详细信息，请参阅Adobe Analytics中的[Edge Network事件类型](hit-types.md)。

发送到Adobe Experience Platform Edge Network的数据可遵循三种格式：**XDM对象**、**数据对象**&#x200B;和&#x200B;**上下文数据**。 当数据流将数据转发到Adobe Analytics时，它们会转换为Adobe Analytics可以处理的格式。

## `xdm`对象

符合您基于[XDM](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/home) (Experience Data Model)创建的架构。 XDM 可让您灵活地将字段定义为事件的一部分。如果要使用特定于Adobe Analytics的预定义架构，可将[Adobe Analytics ExperienceEvent架构字段组](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/field-groups/event/analytics-full-extension)添加到您的架构中。 添加后，您可以使用Web SDK中的`xdm`对象填充此架构，以将数据发送到报表包。 数据到达Edge Network时，会将XDM对象转换为Adobe Analytics可以理解的格式。

有关XDM字段及其映射到Adobe Analytics变量的方式的完整引用，请参阅映射到Analytics的[XDM对象变量](xdm-var-mapping.md)。

>[!TIP]
>
>如果您计划在未来迁移到[Customer Journey Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-landing)，Adobe建议不要使用Adobe Analytics架构字段组。 相反，Adobe建议[创建自己的架构](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/schema/cja-upgrade-schema-architect)，并使用数据流映射填充所需的Analytics变量。 当您准备好迁移到Customer Journey Analytics时，此策略不会将您锁定在prop和eVar架构中。

## `data`对象

作为使用`xdm`对象的替代方法，您可以改用`data`对象。 数据对象适用于当前使用AppMeasurement的实施，使得升级到Web SDK更加容易。 Edge Network检测特定于Adobe Analytics的字段是否存在，而无需符合架构。

请参阅映射到Adobe Analytics的[数据对象变量](data-var-mapping.md)，以获取数据对象字段的完整引用以及它们如何映射到Analytics变量。

## 上下文数据变量

以您需要的任何格式将数据发送到Edge Network。 任何未自动映射到`xdm`或`data`对象字段的字段在转发到Adobe Analytics时均包括为[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)。 然后，必须使用[处理规则](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)将所需字段映射到各自的Analytics变量。

例如，如果您有一个类似于以下内容的自定义XDM架构：

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

然后，这些字段将成为您在处理规则界面中可用的上下文数据键：

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

给定上下文数据变量负载（包括键和值）的最大大小为32 KB。 您可以通过调整相关字段以便Adobe Analytics在[`xdm`](xdm-var-mapping.md)或[`data`](data-var-mapping.md)对象中识别这些字段，从而减小此有效负载的大小。
