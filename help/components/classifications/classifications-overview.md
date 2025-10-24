---
title: 分类概述
description: 自定义维度项目的分组。
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 3701aa7a2a1528cd735c70fc7b061755a15b34a6
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 28%

---

# 分类概述

分类是在生成报表时对 Analytics 变量数据进行分类，然后以不同的方式显示数据的方法。您在变量值和与该值相关的元数据之间建立关系。分类可用于大多数自定义维度，如[跟踪代码](/help/components/dimensions/tracking-code.md)、[prop](/help/components/dimensions/prop.md)和[eVars](/help/components/dimensions/evar.md)。

**分类集**&#x200B;是分类数据的主要方式。 **分类规则**&#x200B;和&#x200B;**分类导入器**&#x200B;是旧的数据分类方法。 这些方法已弃用，在2026年8月31日之后将无法再访问。

* **分类集**：在单个简化的界面中创建和管理分类。
* **分类规则**（旧版）：创建将给定维度项分配给分类维度项的规则。 当维度经常遇到新的唯一值或手动分类频繁且繁琐时，这种数据分类方法最佳。
* **分类导入器**（旧版）：导出模板电子表格，其中每行包含维度项目。 列标识维度的每个分类。当所有维度项已知且不需要频繁更新时，此数据分类方法最适用。

单个维度可具有多个分类维度。例如，您可以使用其他产品属性（如产品名称、颜色、大小、描述和SKU）对[!UICONTROL 产品ID]进行分类。 其中每个属性都是一个单独的分类维度，属于相同的父维度。 使用这些属性来扩充报表可提供更深入、更复杂的报表机会。 一旦某个维度包含分类数据，分类维度就可在仅包含分类维度项目的报表中使用。 任何不包含分类值的父维度项都会分组到[未指定](/help/technotes/unspecified.md)下
