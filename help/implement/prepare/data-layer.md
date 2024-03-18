---
title: 创建数据层
description: 了解 Analytics 实施中的数据层，以及如何在 Adobe Analytics 中使用它来映射变量。
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
source-git-commit: 5ef8ba686a13f8b4ab592c0b48a9c074b0477fcf
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 97%

---

# 创建数据层

数据层是网站上 JavaScript 对象的框架，其中包含 Analytics 实施中使用的变量值。在为 Analytics 变量分配值时，它可以帮助更好地控制和更轻松地维护变量值。

## 先决条件

[创建解决方案设计文档](solution-design.md) - 贵组织务必要根据跟踪要求进行调整，这一点很重要。在联系组织中的开发团队之前，确保您已准备了解决方案设计文档。

## 工作流

使用数据层实施 Adobe Analytics 时通常遵循以下步骤：

1. **与网站开发团队合作实施数据层**：网站开发团队主要负责确保使用正确的值填充数据层对象。与您的网站开发团队一起检查此页面，以确保各团队的期望是一致的。

   >[!NOTE]
   >
   > 是否遵循 Adobe 推荐的数据层规范是可选的。如果您已经有一个数据层，或者选择不遵循 Adobe 提供的规范，请确保贵组织与要遵循的规范保持一致。

1. **使用浏览器控制台验证数据层**：创建数据层后，您可以使用任意浏览器的开发人员控制台来验证数据层是否可正常使用。在大多数浏览器中，您都可以使用 `F12` 键打开开发人员控制台。`adobeDataLayer.page.title` 是一个示例变量值。
1. **使用 Adobe Experience Platform 数据收集将数据层对象映射到数据元素**：此步骤因您组织的实施方法而异：
   * **如果使用 Web SDK**：将所需的数据层对象映射到 Adobe Experience Platform Edge 中所需的 XDM 字段。 请参阅 [Analytics XDM变量映射](../aep-edge/xdm-var-mapping.md) 以确定所需的数据层映射。
   * **如果使用 Analytics 扩展程序**：在 Adobe Experience Platform 数据集的标签下创建数据元素，并将其分配给所需的数据层对象。 然后在 Analytics 扩展程序中，将每个数据元素分配给适当的 Analytics 变量。

## 规范

Adobe 建议将 [Adobe 客户端数据层](https://github.com/adobe/adobe-client-data-layer/wiki)用于新的或重构的实现。

您的组织可以自由使用其他数据层规范，例如[客户体验数字数据层](https://www.w3.org/2013/12/ceddl-201312.pdf)，或完全另外自定义一个规范。与满足组织需求的一致数据层保持一致是最重要的。

数据层是可扩展的；如果贵组织有特定需求，则可以在数据层中包含相应对象以满足这些需求。

## 设置数据层值

数据层通常会在服务器端生成，并引用构建网站内容时所使用的相同对象。根据在组织的[解决方案设计文档](solution-design.md)中设定的跟踪需求建立网站数据层。

## 后续步骤

[将数据层对象映射到数据元素](../launch/layer-to-elements.md)：在 Adobe Experience Platform 中使用网站的数据层。
