---
description: 您可以通过构建自定义表达式指定复杂的日期范围。
title: 自定义的日期表达式 - 概述
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: User, Admin
exl-id: b3bdc07e-5c2d-4be3-86c9-b4b7380be0f6
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 29%

---

# 自定义的日期表达式 - 概述

您可以通过构建自定义表达式指定复杂的日期范围。

我们建议您在构建表达式时引用日历，以正确指定周数和天数。 Excel 具有一些内置函数，您可以通过这些函数计算两个日期之间的天数、工作日数、月数和年数。您可以在公式中使用这些函数计算其他间隔，如周数和季度数。

**启用自定义表达式**

以下示例使用 **[!UICONTROL 滚动日期]**.

1. 在 [!UICONTROL 请求向导：第1步]，而不是使用 **[!UICONTROL 预设日期]**，选择 **[!UICONTROL 滚动日期]**.

   ![](assets/rolldates1.png)

1. 切换到每周、每月、每季度或每年滚动。 请注意以下选项发生了什么变化。
1. 有关更多自定义选项，请单击 **[!UICONTROL 显示高级选项]**.

   ![](assets/rolldates2.png)

1. 例如，如果您将上述日期更改为每月滚动日期，从三个月前的第一天更改为本月的第一天，则提前选项部分中的日期将自行更新以反映这一点：

   ![](assets/rolldatesfor3.png)

1. 启用 **[!UICONTROL 自定义表达式]**. 选择下面的选项 **[!UICONTROL 滚动日期]**，即可轻松查看自定义日期表达式的语法。

   ![](assets/rolldatesfor5.png)

   您可以使用高级选项来混合和匹配自定义日期表达式。 例如，如果您要查看从一年的第一天到最后一个整月结束的数据，可以输入以下内容： `From: cy` `To: cm-1d`. 在向导中，这些日期显示为1/1/2020-1/31/2020。
