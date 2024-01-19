---
description: 可对虚拟报表包进行管理以在 Analysis Workspace 中包含和排除组件。
title: 虚拟报表包组件管理
feature: VRS
exl-id: 19163829-328a-4064-b1be-8c09d1d94a0d
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 94%

---

# 虚拟报表包组件管理

可对虚拟报表包进行管理以在 Analysis Workspace 中包含和排除组件。

以下是一段关于组件策展的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23544/?quality=12)

>[!NOTE]
>
>对于管理员和非管理员可在策划的 Workspace 项目和策划的虚拟报告包中看到哪些组件作出了更改。以前，单击&#x200B;**[!UICONTROL 显示所有组件]**&#x200B;后，大家只能看到非策划的组件。[策划体验经过更新后](/help/analyze/analysis-workspace/curate-share/curate.md)，在查看组件方面提供了更加精细化的控制。

要启用组件管理，请执行以下操作：

1. 转到 **[!UICONTROL 分析]** > **[!UICONTROL 组件]** > **[!UICONTROL 虚拟报表包]** > **[!UICONTROL 创建新的虚拟报表包]**.
1. 定义&#x200B;**[!UICONTROL 设置]**&#x200B;后，单击&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡。

1. 选中复选框 **[!UICONTROL 启用虚拟报表包组件的自定义]**：

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >如果启用了组件自定，则虚拟报表包&#x200B;**“只能在 Analysis Workspace 中”**&#x200B;访问，而不能在以下位置访问：
   >
   >* [!UICONTROL Data Warehouse]
   >* [!UICONTROL Report Builder]
   >* [!UICONTROL Activity Map]
   >* Analytics 报表 API

   选中后，通过将适用组件从“排除的组件”列拖入“已包含的组件”列，可添加要包含在虚拟报表包中的组件。可包含和排除的组件包括：

   * 维度
   * 量度
   * 区段
   * 日期范围

   >[!NOTE]
   >
   >不需要&#x200B;*共享*&#x200B;已经过策划的组件（区段、计算指标、日期范围）。在管理虚拟报表包的上述组件时，则即使没有共享，它们也会在 Analysis Workspace 中始终保持可见。

1. 此外，您还可以过滤或搜索组件，并单击&#x200B;**[!UICONTROL 添加全部]**&#x200B;以将整个过滤的选定内容添加到“已包括”列中。

   ![](assets/vrs-add-all.png)

## 重命名组件 {#section_0F7CD9F684FE4765BC00A2AFED56550E}

您可以将包含的组件的显示名称更改为特定于虚拟报表包的名称。例如，如果您要在虚拟报表包中包含“页面名称”，但又希望将其重命名为一个更适合移动设备且用户更易理解的名称，则可以将其更改为“应用程序屏幕”。每当使用此虚拟报表包时，都会在 Analysis Workspace 中显示新名称。

![](assets/vrs-rename-component.png)

在 Analysis Workspace 中，单击任何包含的组件的信息图标，均可显示已重命名组件的原始名称：

![](assets/vrs-aw-renamed.png)

## 组件组 {#section_483BEC76F49E46ADAAA03F0A12E48426}

使用组件组可向您的虚拟报表包中批量添加组件。例如，如果您要导入一组专门用于移动设备应用程序分析的默认组件，请选择移动设备应用程序组。对应的一组维度和指标（已重命名）会被自动添加到虚拟报表包的“已包括”列表中。

![](assets/vrs-comp-grp.png)

## 工作区行为 {#section_6C32F8B642804C0097FCB14E21028D4A}

有关 Analysis Workspace 中策化的更多信息，请参阅[策划和共享项目](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=zh-Hans)。
