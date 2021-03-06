---
title: 在分析中排除特定日期
description: 如果您不想在报表中包含日期或日期范围，请提供排除该日期或日期范围的提示。
exl-id: 744666c0-17f3-443b-9760-9c8568bec600
source-git-commit: d03206b127e16cbb98d1318b0acc6c304f91ca48
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 2%

---

# 在分析中排除特定日期

如果您有数据 [受事件影响](overview.md)，则可以使用区段排除任何您不希望包含在报表中的日期范围。 划分出受事件影响的日期有助于阻止您的组织对局部数据做出决策。

## 隔离受影响的日期 {#isolate}

创建一个区段以隔离受影响的日期或日期范围。 如果您只想关注问题日期以了解有关其影响的更多信息，则此区段非常有用。

1. 通过转到 **[!UICONTROL 组件]** > **[!UICONTROL 区段]**，然后单击 **[!UICONTROL 添加]**.
2. 将“日”维度拖动到定义画布，并将其设置为等于要隔离的日期。
3. 对要在报表中隔离的每一天重复上述步骤。

![受影响的天数区段](assets/affected_days.jpg)

>[!TIP]
>
>要将OR语句更改为AND语句，请单击OR旁边的向下箭头，然后选择AND。

Adobe建议使用橙色维度维度组件，而不是紫色日期范围组件。 如果使用紫色日期范围组件，则它们会覆盖项目的日历范围：

![排除区段日期类型](assets/exclude_segment_day_type.jpg)

## 排除受影响的日期 {#exclude}

创建一个区段，以排除受影响的日期或日期范围。 如果您要排除出现问题的日期，以最大限度地减少对整体报表的影响，此区段非常有用。

1. 通过转到 **[!UICONTROL 组件]** > **[!UICONTROL 区段]**，然后单击 **[!UICONTROL 添加]**.
2. 在区段定义画布的右上角，单击 **[!UICONTROL 选项]** > **[!UICONTROL 排除]**.
3. 将“日”维度拖动到定义画布，并将其设置为等于要删除的日期。
4. 对要在报表中删除的每一天重复上述步骤。

![排除受影响的日期](assets/exclude_affected_days.jpg)

## 在报表中使用这些区段

创建排除区段后，您可以像使用其他区段一样使用该区段。

### 在趋势报表中比较区段 {#compare}

您可以在报表中同时应用“受影响的日期”区段和“排除受影响的日期”区段，以并排比较这些区段。 将两个区段拖动到量度的上方或下方，以比较它们：

![两个区段](assets/affected_and_exclude.png)

如果不想在表或可视化图表中显示零（导致低谷），请启用 **[!UICONTROL 将零解释为没有值]** 列设置下。

![解释零](assets/interpret_zero.png)

如果不想在表或可视化图表中显示零（导致低谷），请启用 **[!UICONTROL 将零解释为没有值]** 列设置下。

![解释零](assets/interpret_zero.png)

### 将排除区段应用到项目 {#apply}

您可以将“排除受影响的日”区段应用到工作区项目。 将排除区段拖到Workspace画布区域，该区域标记为 *在此处放置区段*.

>[!TIP]
>
>在面板描述中包含有关排除数据的注释，以帮助查看报表的用户。 右键单击面板的标题，然后单击 **[!UICONTROL 编辑描述]**.

![应用于面板的区段](assets/exclude_segment_panel.jpg)

### 在虚拟报表包中使用排除区段 {#use-vrs}

您可以在 [虚拟报表包](/help/components/vrs/vrs-about.md) 以便更方便地排除数据。 此选项的理想做法是，您无需记住为每个包含受影响日期范围的报表应用区段。 如果您已使用虚拟报表包作为主要数据源，则可以将区段添加到现有VRS。

1. 导航到 **[!UICONTROL 组件]** > **[!UICONTROL 虚拟报表包]**.
2. 单击&#x200B;**[!UICONTROL 添加]**。
3. 输入虚拟报表包的所需名称和描述。
4. 将排除区段拖到标有的区域 **[!UICONTROL 添加区段]**.
5. 单击 **[!UICONTROL 继续]** ，然后单击 **[!UICONTROL 保存]**.

![应用于VRS的区段](assets/exclude_segment_vrs.png)
