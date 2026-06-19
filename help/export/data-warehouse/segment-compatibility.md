---
title: 数据仓库区段兼容性
description: 了解哪些区段定义在Data Warehouse中有效。
feature: Data Warehouse
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 456
ht-degree: 9%

---

# 数据仓库区段兼容性

区段生成器中构建的所有区段并非都可以在Data Warehouse中使用。 使用此页面可了解哪些区段定义与Data Warehouse兼容，以便在[创建Data Warehouse请求](/help/export/data-warehouse/create-request/t-dw-create-request.md)时可供选择。

仅当以下&#x200B;**两个**&#x200B;均为true时，区段才与Data Warehouse兼容：

* **支持的组件**：区段仅使用Data Warehouse支持的维度和量度。
* **支持的结构**：区段的结构遵循Data Warehouse强制实施的规则。

如果不满足这两个条件中的任何一个条件，则在构建Data Warehouse请求时，区段都不会显示为选项；如果您选择的虚拟报表包包含不兼容的区段，则会显示错误。

## 支持的组件

由于评估区段的数据与将其应用于该区段的请求的数据相同，因此&#x200B;**Data Warehouse请求中不支持的任何组件在区段中也不受支持。** 有关Data Warehouse不支持的维度和量度的完整列表，请参阅Data Warehouse中的[组件支持](component-support.md)。

除了[组件支持](component-support.md)中列出的维度和量度之外，Data Warehouse *请求*&#x200B;中还提供以下维度，但&#x200B;**不能在区段定义**&#x200B;中使用：

* [[!UICONTROL 这月的其中一天]](/help/components/dimensions/day-of-month.md)
* [[!UICONTROL 这周的其中一天]](/help/components/dimensions/day-of-week.md)
* [[!UICONTROL 每年的某一天]](/help/components/dimensions/day-of-year.md)
* [[!UICONTROL 这天的其中一个小时]](/help/components/dimensions/hour-of-day.md)
* [[!UICONTROL 营销渠道]](/help/components/dimensions/marketing-channel.md)（请改用[[!UICONTROL 最近联系渠道]](/help/components/dimensions/last-touch-channel.md)）
* [[!UICONTROL 这年的其中一个月]](/help/components/dimensions/month-of-year.md)
* [[!UICONTROL 页面未找到]](/help/components/dimensions/pages-not-found.md)（请改用[[!UICONTROL 页面类型错误]](/help/components/dimensions/pages-not-found.md)）
* [[!UICONTROL 这年的其中一个季度]](/help/components/dimensions/quarter-of-year.md)
* [[!UICONTROL 工作日/周末]](/help/components/dimensions/weekday-weekend.md)

## 支持的结构

即使区段仅使用受支持的组件，其结构也必须遵循Data Warehouse实施的规则。 区段结构完全受支持、部分受支持或不受支持：

**支持**：

* **区段栈叠**：可以将多个区段应用于单个Data Warehouse请求。
* **嵌套容器**：支持，提供的范围在每个级别（访客→访问→点击）都减少。 不支持范围增加的容器。

**部分支持**：

* **排除容器**：仅在顶级支持。 Data Warehouse仅支持可表示为`A AND NOT B`的区段，即&#x200B;**包含此特征**&#x200B;和&#x200B;**排除此特征**。 不支持排除嵌套在其他容器中的容器。
* **AND/OR logic**：受支持，但有限制。 在将`exclusion`或`without`容器与AND/OR逻辑结合使用时，仅支持可重写为`A AND NOT B`的区段。

**不支持**：

* **顺序区段**：不支持使用THEN运算符定义顺序访客导航序列的区段。
* **“等于任何”和“不等于任何”运算符**：Data Warehouse区段不支持这些运算符。

## 用作维度的区段

在Data Warehouse报表中使用区段作为维度时，报表返回包含`"0"`或`"1"`的列：

* **`"0"`**：维度项不符合区段的标准。
* **`"1"`**：维度项符合区段的标准。
