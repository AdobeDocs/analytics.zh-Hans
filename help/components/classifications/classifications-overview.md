---
title: 分类概述
description: 自定义维度项目的分组。
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
TQID: https://experienceleague.adobe.com/raB90u-JEBgDroQPLC1eCSmxs4V-J7Av8Snr6oeKwvk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 309
ht-degree: 84%

---

# 分类概述

分类是在生成报表时对 Analytics 变量数据进行分类，然后以不同的方式显示数据的方法。 您在变量值和与该值相关的元数据之间建立关系。 分类可用于大多数自定义维度，例如[跟踪代码](/help/components/dimensions/tracking-code.md)、[props](/help/components/dimensions/prop.md) 和 [eVar](/help/components/dimensions/evar.md)。

* **分类集**&#x200B;是用于对数据进行分类的主要组件。 [分类集](/help/components/classifications/sets/overview.md)允许您在一个简化的界面中创建和管理分类。

* **旧版分类**&#x200B;记录了用于对数据进行分类的旧版分类方法。 这些方法将在不久的将来被弃用，并且将无法再访问。

   * [分类规则](/help/components/classifications/crb/classification-rule-builder.md)：创建将给定维度项分配给分类维度项的规则。 当一个维度频繁遇到新的唯一值或者当手动分类相当频繁而繁琐时，这种数据分类方法最适用。 此功能将在2027年2月28日之后弃用。

   * [分类导入程序](/help/components/classifications/importer/c-working-with-saint.md)：导出每行包含维度项的模板电子表格。 列标识维度的每个分类。 当所有维度项已知且不需要频繁更新时，此数据分类方法最适用。 此功能将在2026年8月31日之后弃用。 弃用后，您将无法使用标准FTP导入分类。

单个维度可具有多个分类维度。 例如，您可以使用附加产品属性（如产品名称、颜色、大小、描述和 SKU）对[!UICONTROL 产品 ID] 进行分类。 其中每个属性都是一个单独的分类维度，都属于同一个父维度。 通过这些属性来扩充您的报告，可以提供更深入、更复杂的报告机会。 如果一个维度中包含分类数据，报告中就会有这个仅包含分类维度项的分类维度。 任何不包含分类值的父维度项都会分到[未指定](/help/technotes/unspecified.md)组中
