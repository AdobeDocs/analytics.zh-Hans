---
description: 了解如何将标准和有限的格式应用到单元格范围。
title: 如何以Report Builder设置日期格式
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
source-git-commit: 12d048b42c6a61e03dbbe73acb9d34df3e37693c
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 81%

---

# 设置日期格式

除了通过Excel的“格式”>“单元格(Ctrl+1)”功能提供的标准单元格格式选项之外，您还可以对具有Report Builder的单元格范围应用有限的格式。 这些格式选项取决于您选择的量度。

向“行标签”网格[添加维度](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)后，单击&#x200B;**[!UICONTROL 格式]**。

在&#x200B;**[!UICONTROL 格式]**&#x200B;菜单中，单击&#x200B;**[!UICONTROL 自定义格式]**，以像使用前置和后置功能那样对日期应用自定义格式。例如，您可以输入始终显示在日期之后的文本（如 A.D. B.C.E. A.H. 等）。您可以在日期之前添加文本，如[!UICONTROL 开始日期]以及[!UICONTROL 开始和结束日期]。此外，您可以基于日、月和年缩写构建自定义日期表达式，并在日期的各个部分之间使用自定义分隔符。所有日期格式只能包含 3 个缩写，并且要用括号括起来。

下表说明如何在“[!UICONTROL 自定义格式]”字段中使用日期缩写：

| 缩写 | 含义 | 示例   使用2012年3月14日，星期三 |
|--- |--- |--- |
| MM/dd/yyy | 完整的数字日期 | 03/14/2012 |
| 一 | 月份 | 3 |
| MM | 月份（小于 10 时使用 0 填充） | 03 |
| MMM | 月份的短名称 | 三月 |
| MMMM | 月份的长名称 | 3 月 |
| D | 日期的长名称 | 2012 年 3 月 14 日，星期三 |
| d | 日 | 14 |
| dd | 日（小于 10 时使用 0 填充） | 01 - 09 |
| ddd | 周日期的短名称 | 星期三 |
| dddd | 周日期的长名称 | 星期三 |
| yy | 2 位数年份 | 10 |
| yyyy | 完整的 4 位数年份 | 2012 |
