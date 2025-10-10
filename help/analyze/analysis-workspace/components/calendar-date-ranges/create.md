---
title: 创建日期范围
description: 了解如何创建可在Analysis Workspace中使用的日期范围。
feature: Date Ranges
role: User
exl-id: 62ce2ca5-4df1-43bf-88ce-3c9f106f4a59
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 96%

---

# 创建日期范围

任何人都可以创建自定义日期范围。您可以通过以下方式创建日期范围：

![创建注释](assets/create-date-range.png)

* **A** - 在主界面中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 日期范围]**。从[[!UICONTROL 日期范围]管理器](manage.md)中选择 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]**。
* **B** - 在工作区项目中，从可视化界面的上下文菜单中选择&#x200B;**[!UICONTROL 将日期范围自定义为此日期范围]**。
* **C** - 在工作区项目中，从菜单中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 创建日期范围]**
* **D** - 在工作区项目中，使用快捷键&#x200B;**[!UICONTROL ctrl+shift+d]** (Windows) 或 **[!UICONTROL shift+command+d]** (macOS)。
* **E** - 在工作区项目中，从组件左侧面板中选择在![日程表](/help/assets/icons/Calendar.svg)**日期范围**&#x200B;内![添加](/help/assets/icons/Add.svg)。
* **F** - 在受支持的可视化图表（如可视化折线图）中，从数据点的上下文菜单中选择&#x200B;**[!UICONTROL 注释选项]**。

若要定义注释，您可以使用[[!UICONTROL 日期范围生成器]](#annotation-builder)：

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## 日期范围生成器 {#date-range-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="结束时间"
>abstract="结束时间始终包括 59 秒。"

<!-- markdownlint-enable MD034 -->




**[!UICONTROL 新建日期范围]**&#x200B;或&#x200B;**[!UICONTROL 编辑日期范围]**&#x200B;对话框用于创建新的日期范围或编辑现有的日期范围。

![注释详情窗口，其中显示下一节将会介绍的字段和选项。](assets/edit-date-range.png)


1. 为日期范围指定一个&#x200B;**[!UICONTROL 标题]**。例如，**[!UICONTROL 每季度]**。
1. （可选）指定&#x200B;**[!UICONTROL 描述]**。
1. 通过创建或应用一个或多个&#x200B;**[!UICONTROL 标记]**&#x200B;来组织区段。开始键入，以查找您可以选择的现有标记。或者按&#x200B;**[!UICONTROL 输入]**&#x200B;键添加新的标记。选择 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 以移除标记。|
1. 通过先选择开始日期，然后选择结束日期来选择&#x200B;**[!UICONTROL 日期范围]**。
或者，您也可以从[!UICONTROL *选择预设*]&#x200B;下拉菜单中选择一个&#x200B;**[!UICONTROL 预设]**。

1. 或者，选择&#x200B;**[!UICONTROL 显示高级设置]**&#x200B;以：

   * 指定&#x200B;**[!UICONTROL 开始时间]**&#x200B;和&#x200B;**[!UICONTROL 结束时间]**，而不是默认的 `12:00 AM` (`0:00`) 和 `11:59 PM` (`23:59`)。结束时间始终包括 59 秒。如果日期范围跨越许多天，则开始时间适用于该日期范围的第一天，结束时间适用于日期范围内的最后一天。使用&#x200B;**[!UICONTROL （重置时间值）]**&#x200B;将开始和结束时间重置为默认值。
   * **[!UICONTROL 使用滚动日期]**。如果启用，预设日期范围（如&#x200B;**[!UICONTROL 过去 7 个整天]**）会随着当前日期和时间的进展而动态更新。如果禁用，则此类预设在应用后便不会更新。

     您可以选择括号内的文本（例如&#x200B;**[!UICONTROL 固定开始——每季度滚动]**）来扩展面板并指定&#x200B;**[!UICONTROL 开始]**&#x200B;和&#x200B;**[!UICONTROL 结束]**&#x200B;的详细信息。

     ![Rolling dates](assets/rolliing-dates.png)

      1. 选择&#x200B;**[!UICONTROL 开始]**、**[!UICONTROL 结束]**&#x200B;或&#x200B;**[!UICONTROL 固定日期]**。
      1. 当选择了&#x200B;**[!UICONTROL 开始]**&#x200B;或&#x200B;**[!UICONTROL 结束]**&#x200B;时，您可以生成一个完整的表达式。例如：******[!UICONTROL 当前季度结束]****[!UICONTROL 减去]**`20`**[!UICONTROL 天]**。为表达式的每个部分选择适当的值。
         * 选择当前时间的值。例如&#x200B;**[!UICONTROL 当前季度]**。
         * 选择一个值进行额外的计算。例如，**[!UICONTROL 减]**。
         * 当您指定了额外的计算时，请指定一个值。例如，`20`。
         * 当您指定了额外的计算时，请选择用于该计算的时段。例如&#x200B;**[!UICONTROL 天]**。

     选择&#x200B;**[!UICONTROL 隐藏详细信息]**，以隐藏计算滚动日期的详细信息。

1. 选择：
   * **[!UICONTROL 保存]**&#x200B;以保存日期范围。
   * **[!UICONTROL 另存为]**&#x200B;以保存日期范围的副本。
   * **[!UICONTROL 取消]**&#x200B;以取消对日期范围所做的任何更改，或取消创建新的日期范围。


<!--


You can create a date range using either of the following two methods:

* Directly in a workspace project by clicking the '`+`' button next to the list of date range components on the left
* Within the date range manager

To create a date range in the date range manager:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Navigate to [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Click the [!UICONTROL Add] button to open the modal window that creates a date range.

## Create a date range modal window

The modal window has four fields you can edit:

* **Date range**: The date range you want for this component.
* **Title**: The name you want for this component. The title is used in workspace projects.
* **Description**: The description you want for this component. The description is seen when clicking the ![i](../assets/i.png) icon.
* **Tags**: Use tags to organize your date ranges. A date range can belong to multiple tags.

## Selecting a date range

When clicking the date range in the modal window, you have several options:

* **Calendar**: Select the start and end date.
* **Use rolling dates**: Check this box if you want the date range to change as time goes on. Do not check this box if you want your date range to remain static.
* **Select preset**: Use this drop-down selection if you want a custom date range based on a range that Adobe offers by default. When you select a preset, you can further customize the date range to suit your needs. It does not affect the preset that Adobe offers.

## Rolling date ranges

If you want a rolling date range, you can customize when it rolls. You can control when the start and end dates roll independently of each other.

* **When the date starts**: Choose if the date starts at the beginning of a time period, at the end of a time period, or use a fixed day.
* **The time period to use**: Choose how often the date range rolls. You can have it roll every day, every week, every month, every quarter, or every year.
* **Offset**: Choose the offset of the date range. You can add or subtract days, weeks, months, quarters, or years.

## Rolling date examples

Some date ranges can be useful in certain reports.

Year-to-date:

```text
Start: Start of current year
End: End of current day
```

Last Thursday to this Thursday:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Fiscal year (for example, if a fiscal year starts in December)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```


-->
