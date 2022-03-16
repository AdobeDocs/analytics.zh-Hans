---
description: 在 Report Builder 中创建请求时的第一步。
title: 数据请求 — 请求向导第 1 步
feature: Report Builder
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: ht
source-wordcount: '418'
ht-degree: 100%

---

# 数据请求 — 请求向导第 1 步

在“请求向导: 第 1 步”窗体上，您可以选择报表包、报表类型、区段并配置日期。

![](assets/rw1_overview.png)

1. **[!UICONTROL 报表包：]**&#x200B;根据您的登录凭据向您提供的报表包列表。请参阅[选择报表包](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。

1. **范围选择器：**&#x200B;允许您从 Excel 的单元格中选择报表包 ID。请参阅[选择报表包](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。

1. **区段**：区段是数据的自定义子集，或者是按您创建的规则所过滤的数据。区段基于点击数、访问次数和访客数。请参阅[《Analytics 分段指南》](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)，以了解有关区段的更多信息。

   例如，您可以运行[!UICONTROL 页面报表]，然后应用“首次访问”区段。

1. **允许发布列表覆盖**：计划报表时，您可以选择要用于分发的发布列表。发布列表在 **[!UICONTROL Analytics]** > **[!UICONTROL 管理工具]**&#x200B;中进行设置。此请求的报表包由分配给发布列表中每个收件人的报表包 ID 替换。请参阅[允许发布列表覆盖](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)。

1. **报表类型**：指定要在数据请求中运行的基本报表。每个请求运行一个报表，并且报表可以包含一对多维度和一对多指标。报表类型的指标和维度显示在“[!UICONTROL 请求向导: 第 2 步]”界面上。请参阅[选择报表类型](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md)。

1. **日期范围**：定义请求涵盖的时间跨度。系统提供了多种类型的请求时段，如预设、固定和滚动。最大时段数是 366。您还可以选择单元格指定的日期范围，并且将日期范围保存为模板，供以后使用。请参阅[配置报表日期](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **应用粒度**：指定报表中包含的基于时间的详细信息级别。请参阅[粒度](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)。

## 故障诊断

有时，请求向导会显示在屏幕外，尤其是对于在不同显示器设置之间切换的用户而言更是如此。例如，您在办公室使用扩展坞，但在家中使用的是笔记本电脑屏幕。如果在请求向导已打开的情况下再次单击“创建”，则将出现以下错误：

“您需要先完成请求向导过程，然后再启动新过程。”

将请求向导移回屏幕上即可解决此问题。

1. 打开 Microsoft Excel 并登录到 Report Builder。
2. 单击[!UICONTROL 创建]，此时会在屏幕外打开请求向导。
3. 按 `[Alt]` + `[Space]`。
4. 按 `[M]`。
5. 按任意箭头键。
6. 移动鼠标，将请求向导附加到光标上。
7. 单击鼠标，在屏幕上松开请求向导。
