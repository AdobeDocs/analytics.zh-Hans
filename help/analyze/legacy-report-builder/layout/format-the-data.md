---
description: 了解如何将标准和有限的格式应用到单元格范围。
title: 如何在Report Builder中设置日期格式
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
TQID: https://experienceleague.adobe.com/8FuosvmSvi-bRNaG5QbwUExuDffOIXbrkuiQLh0NZXM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 18%

---

# 设置日期格式

{{legacy-arb}}

除了Excel的“格式”>“单元格(Ctrl+1)”功能提供的标准单元格格式选项之外，您还可以使用Report Builder将有限的格式应用到单元格范围。 这些格式选择取决于您选择的量度。

向“行标签”网格[添加维度](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)后，单击&#x200B;**[!UICONTROL 格式]**。

在&#x200B;**[!UICONTROL 格式]**&#x200B;菜单中，单击&#x200B;**[!UICONTROL 自定义格式]**，以像使用前置和后置功能那样对日期应用自定义格式。 例如，您可以输入始终在日期之后出现的文本（例如A.D. B.C.E. A.H.等）。 您可以在日期之前添加文本，如[!UICONTROL 开始日期]和[!UICONTROL 开始日期和结束日期]。 此外，您可以构建由天、月、年缩写组成的自定义日期表达式，并在日期的各部分之间使用自定义分隔符。 所有日期格式都必须由三个仅括在方括号中的缩写组成。

下表描述了如何在[!UICONTROL 自定义格式]字段中使用日期缩写：

| 缩写 | 含义 | 使用2012年3月14日星期三的示例 |
|--- |--- |--- |
| MM/dd/yyyy | 完整数字日期 | 03/14/2012 |
| M | 月数 | 3 |
| 毫米 | 月数，0填充表示月数&lt; 10 | 03 |
| MMM | 月份的简短名称 | 3 月 |
| MMMM | 月份的长名称 | 3 月 |
| D | 日期的长名称 | 2012年3月14日，星期三 |
| d | 天数 | 14 |
| dd | 带0边距的天数&lt; 10 | 01 - 09 |
| ddd | 简短的日期名称 | 星期三 |
| dddd | 一天的长名称 | 星期三 |
| yy | 2位数年份 | 10 |
| yyyy | 完整4位数年份 | 2012 |
