---
description: 可以在分析工作区中创建虚拟报告套件以包含和排除组件。
title: 虚拟报表包组件管理
uuid: 6c6a4071-22ad-4e8c-b1ed-140b2aa04f76
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 虚拟报表包组件管理

可以在分析工作区中创建虚拟报告套件以包含和排除组件。

>[!NOTE] 无论是管理员还是非管理员，都可以在策划的 Workspace 项目和策划的虚拟报表包 (VRS) 中，查看发生更改的组件。以前，任何人都可以通过单击查看非特选组件 **[!UICONTROL Show all Components]**。 The [updated curation experience](https://marketing.adobe.com/resources/help/zh_CN/analytics/analysis-workspace/curate-projects-vrs.html) allows for more fine-grained control over which components are visible.

要启用组件管理，请执行以下操作：

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]** > **[!UICONTROL Create new virtual report suite]**.
1. 定义后， **[!UICONTROL Settings]**&#x200B;单击该选 **[!UICONTROL Components]** 项卡。

1. 选中此复选框 **[!UICONTROL Enable Customization of Virtual Report Suite Components]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >如果启用了组件自定，则虚拟报表包&#x200B;**只能在 Analysis Workspace 中**&#x200B;访问，而不能在以下位置访问：

   * [!UICONTROL Reports & Analytics]
   * [!UICONTROL Ad Hoc Analysis]
   * [!UICONTROL Data Warehouse]
   * [!UICONTROL Report Builder]
   * Analytics Reporting API
   选中后，您可以通过将适用组件从“已排除的组件”列拖动到“已包含的组件”列，来添加要包含在虚拟报表包中的组件。 可以包括和排除的组件包括：

   * 维度
   * 量度
   * 区段
   * 日期范围
   >[!NOTE]
   >
   >不需要&#x200B;*共享*&#x200B;已经过策划的组件（区段、计算量度、日期范围）。在管理虚拟报表包的上述组件时，则即使没有共享，它们也会在 Analysis Workspace 中始终保持可见。

1. Additionally, you can filter or search the components and add the entire filtered selection to the included column by clicking **[!UICONTROL Add All]**.

   ![](assets/vrs-add-all.png)

## 重命名组件 {#section_0F7CD9F684FE4765BC00A2AFED56550E}

您可以更改特定于虚拟报告套件的包含组件的显示名称。 例如，如果要在虚拟报告套件中包含页面名称，但要将其重命名为更适合移动设备的上下文，则可以将其更改为应用程序屏幕。 只要使用此虚拟报告套件，新名称就会显示在分析工作区中。

![](assets/vrs-rename-component.png)

在分析工作区中，单击包含的任何组件的信息图标以显示重命名的组件的原始名称：

![](assets/vrs-aw-renamed.png)

## 组件组 {#section_483BEC76F49E46ADAAA03F0A12E48426}

使用组件组向虚拟报表包添加批量组件。 例如，如果要导入特定于移动应用程序分析的一组默认组件，请选择移动应用程序组。 相应的一组维度和度量（已重命名）会自动添加到虚拟报告包“包含”列表。

![](assets/vrs-comp-grp.png)

## 工作区行为 {#section_6C32F8B642804C0097FCB14E21028D4A}

有关 Analysis Workspace 中策化的更多信息，请参阅[策划和共享项目](https://marketing.adobe.com/resources/help/zh_CN/analytics/analysis-workspace/curate.html)。
