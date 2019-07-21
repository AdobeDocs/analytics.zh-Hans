---
description: 除了 Excel 的“格式”>“单元格”(Ctrl+1) 功能提供的标准单元格格式选项之外，您还可以通过 Report Builder 对单元格范围应用少量格式。这些格式选项取决于您选择的量度。
seo-description: 除了 Excel 的“格式”>“单元格”(Ctrl+1) 功能提供的标准单元格格式选项之外，您还可以通过 Report Builder 对单元格范围应用少量格式。这些格式选项取决于您选择的量度。
seo-title: 设置日期格式
solution: Analytics
title: 设置日期格式
topic: Report Builder
uuid: 5211db30-07b3-4413-97c3-e40 e6 ff223 cd
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 设置日期格式

除了 Excel 的“格式”&gt;“单元格”(Ctrl+1) 功能提供的标准单元格格式选项之外，您还可以通过 Report Builder 对单元格范围应用少量格式。这些格式选项取决于您选择的量度。

After you [add dimensions](../../../analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4) to the Row Labels grid, click **[!UICONTROL Format]**.

在&#x200B;**[!UICONTROL 格式]**&#x200B;菜单中，单击&#x200B;**自定义格式]，以像使用前置和后置功能那样对日期应用自定义格式。[!UICONTROL **&#x200B;例如，您可以输入始终显示在日期之后的文本（如 A.D. B.C.E. A.H. 等）。您可以在日期之前添加文本，如[!UICONTROL 开始日期]以及[!UICONTROL 开始和结束日期]。此外，您可以基于日、月和年缩写构建自定义日期表达式，并在日期的各个部分之间使用自定义分隔符。所有日期格式只能包含 3 个缩写，并且要用括号括起来。

下表说明如何在“[!UICONTROL 自定义格式]”字段中使用日期缩写：

| 缩写 | 含义 | 示例   使用 2012 年 3 月 14 日，星期三 |
|--- |--- |--- |
| MM/dd/yyy | 完整的数字日期 | 03/14/2012 |
| 一 | 月份 | 3 |
| MM | 月份（小于 10 时使用 0 填充） | 03 |
| MMM | 月份的短名称 | 三月 |
| MMMM | 月份的长名称 | 三月 |
| D | 日期的长名称 | 2012 年 3 月 14 日，星期三 |
| d | 日 | 14 |
| dd | 日（小于 10 时使用 0 填充） | 01 - 09 |
| ddd | 周日期的短名称 | 星期三 |
| dddd | 周日期的长名称 | 星期三 |
| yy | 2 位数年份 | 10 |
| yyyy | 完整的 4 位数年份 | 2012 |