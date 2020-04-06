---
description: 在日历中，您可以指定日期和日期范围，或者选择一个预设。您可以在项目、工作区和报表级别进行日历选择。 项目的日期范围是默认日期。 但是，工作区日期范围会覆盖项目的日期范围。 同样，报表的日期范围也会覆盖工作区和项目的日期设置。 您无法选择数据可用范围以外的日期范围。
title: 日期和日期范围
uuid: 8f099db7-e74b-4384-ac46-61a545f1dd62
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 日期和日期范围

在日历中，您可以指定日期和日期范围，或者选择一个预设。您可以在项目、工作区和报表级别进行日历选择。 项目的日期范围是默认日期。 但是，工作区日期范围会覆盖项目的日期范围。 同样，报表的日期范围也会覆盖工作区和项目的日期设置。 您无法选择数据可用范围以外的日期范围。

## 日期和日期范围 {#concept_AB32765013F449908B5964AB622C75FF}

在日历中，您可以指定日期和日期范围，或者选择一个预设。您可以在项目、工作区和报表级别进行日历选择。 项目的日期范围是默认日期。 但是，工作区日期范围会覆盖项目的日期范围。 同样，报表的日期范围也会覆盖工作区和项目的日期设置。 您无法选择数据可用范围以外的日期范围。

![](assets/Delete_Standard.png) 启用的 **[!UICONTROL Clear Date]** 选项指示在报表级别指定日期范围。

您还可以将日期（和时间维）拖入报表或 [!UICONTROL Table Builder]。 您可以选择特定的日期、周、月、年或滚动日期。 如果您在市场营销报告和分析中使用自定义日历，则报表包会继承这些设置并相应地更新报表。

在创建项目时选择日期范围时，使用左侧的“预配置”将设置滚动日期，而使用右侧的日历则不会设置滚动日期。 An easy way to tell whether your date range is rolling is the statement &quot;This date range will roll&quot; next to the **[!UICONTROL OK]** button.

![](assets/daterange.jpeg)

>[!NOTE]如果您在运行旧式报表时需要获得帮助，请联系您的客户经理。

## 旧式日期片段 {#concept_53AA34DB3CE647608CAF4B41D6EAF45E}

2010年下半年，Adobe开始将报表包迁移到统一的数据平台，以改进处理和存储。 迁移前存在的数据被视为受日历季度或年边界限制的旧版（或历史）数据。

<!-- 

c_legacy_data.xml

 -->

**访问历史日期片段**

1. [创建或打开一个项目。](/help/analyze/ad-hoc-analysis/c-getting-started.md)
1. Open the [calendar](/help/analyze/ad-hoc-analysis/c-dates.md), then select **[!UICONTROL Quarter]** or **[!UICONTROL Year]**.

>[!NOTE]历史日期片段的约束范围是季度和年份。您无法视图跨越传统切片和新处理平台之间边界的数据。 两个日期范围都会导致错误。 此外，日期范围仅适用于公历，而不适用于自定义日历。

