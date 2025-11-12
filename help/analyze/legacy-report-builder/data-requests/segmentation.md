---
description: 如何在 Report Builder 中添加、编辑、应用和过滤 Adobe Analytics 区段。
title: 管理区段(Report Builder)
feature: Report Builder
role: User, Admin
exl-id: c4ad89e0-91c9-47e1-a226-69d82fdb8918
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 20%

---

# 管理区段

{{legacy-arb}}

如何在 Report Builder 中添加、编辑、应用和过滤 Adobe Analytics 区段。

Report Builder在“请求向导”的第1步中提供了一个分段面板，允许您创建和管理区段。

![显示“添加”、“编辑”或“清除”区段选项并突出显示“控制”、“筛选”和“刷新”图标的屏幕截图。](assets/seg_dialog.png)

## 添加或编辑区段 {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE]
>
>添加或编辑区段时，Report Builder 区段界面会在 Microsoft Internet Explorer 窗口中启动 Analytics 区段生成器。您的Report Builder会话将保持活动状态。 此操作不支持Internet Explorer以外的浏览器。

1. 在“请求向导”第1步的区段面板中，单击&#x200B;**[!UICONTROL 添加]**。
1. 此时将启动一个Internet Explorer窗口，以打开Analytics区段生成器界面。 有关如何构建区段的信息，请参阅 [Analytics 分段](/help/components/segmentation/seg-home.md)。
1. 定义并保存区段后，返回请求向导。
1. 单击“刷新”图标可刷新区段列表。

>[!IMPORTANT]
>
>该列表已缓存，新建区段只有在刷新后才会出现。

## 创建上下文区段 {#section_6DD2C663B2854469AA1075438F907678}

您可能希望将特定的报表维度组合转换为区段。您可以从Report Builder界面创建这些区段。 例如，从页面请求输出中选择几个页面，并根据这些值创建区段。

1. 选择要转换为区段的报表输出项。
1. 单击鼠标右键以选择&#x200B;**[!UICONTROL 在此容器中创建关联区段]**，并指定适当的容器（点击次数容器、访问次数容器、访客数容器）。

   ![屏幕截图显示在选定和可用的容器选项中创建上下文区段。](assets/seg_in_context.png)

   有关容器的详细信息，请参阅[分段指南](/help/components/segmentation/seg-home.md)。

1. 现在，区段生成器UI将在Internet Explorer中启动。 区段生成器UI将使用您指定的容器和过滤器进行初始化。
1. 向区段添加名称和描述后，请保存该区段。
1. 返回Report Builder并单击刷新图标以刷新区段列表。
1. 您现在已准备好应用此区段。

## 搜索并应用区段

此区段列表中会显示在Reports &amp; Analytics（现已终止使用）、Report Builder或Data Warehouse中创建的任何区段。 要刷新列表，请单击“刷新”图标![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg)。

您可以将一个或多个区段应用于任何给定请求。 这包括顺序区段。

1. 转至&#x200B;**[!UICONTROL 区段]**&#x200B;下拉列表，然后单击&#x200B;**[!UICONTROL 选择区段]**&#x200B;框中的向下小箭头以显示所有区段。

1. 选中要应用的区段。

   ![显示选定区段的屏幕快照。](assets/seg_list.png)

>[!NOTE]
>
>无论您是否为管理员，在Report Builder中，您都只能查看那些您拥有的区段以及与您共享的区段。

## 过滤区段 {#filter}

单击“筛选器”图标&#x200B;**筛选器图标**&#x200B;以筛选![区段](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)

可用的过滤器包括：

| 筛选器名称 | 描述 |
|---|---|
| 标记 | 允许您对具有特定标记的区段进行过滤。 请注意，标记过滤器使用AND运算符。 如果选中两个标记，右侧窗格会显示已使用&#x200B;**both**&#x200B;标记进行标记的区段。 |
| 所有者 | 允许您按所有者筛选区段。 请注意，所有者筛选器使用OR运算符。 如果选中两个所有者，右侧窗格将显示&#x200B;**任一**&#x200B;所有者拥有的区段。 |
| 其他筛选器>仅&#x200B;*报表包名称* | 如果在Adobe Analytics的区段生成器中应用“仅&#x200B;*报表包名称*”过滤器，然后在[!DNL Report Builder]中显示“高级过滤器”，则“高级过滤器”将仅显示选定报表包的区段。 |
| 其他过滤器 > 我的 | 显示您拥有的所有区段。 |
| 其他过滤器 > 与我共享 | 显示其他人与您共享的所有区段。 |
| 其他过滤器>收藏夹 | 显示标记为收藏的所有区段。 |
| 其他过滤器>已批准 | 显示所有正式批准的区段。 |

## 将区段控件添加到工作簿 {#segment-control}

通过添加区段控件，您可以从工作簿中切换区段，而不必转至“请求向导”。

1. 单击区段下拉列表旁边的“控件”图标![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)。

1. 选中所有要显示在区段控件中的区段，或选中&#x200B;**[!UICONTROL 全选]**。

   ![选定了所有区段的“控件设置”对话框屏幕截图。](assets/seg_control.png)

1. 注意选项&#x200B;**[!UICONTROL 根据项目选择]**&#x200B;自动刷新链接的请求。

   * 如果选中，则使用此控件的所有请求都将刷新。
   * 如果未选中，则会更新关联的请求参数，但不会刷新请求。

1. 指定区段控件的左上角单元格位置。

1. 单击&#x200B;**[!UICONTROL 确定]**，区段控件将显示在指定位置。

   ![显示“选择区段”字段下拉字段的屏幕截图。](assets/seg_control2.png)

## 刷新区段列表 {#refresh}

每次添加新区段或编辑现有区段时，都应单击“刷新”图标![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg)以刷新缓存的区段列表。

## 在请求间管理区段 {#manage}

在v5.4之前，Report Builder允许用户更改多个请求中的区段。 但是，此过程始终会替换现有区段。 想要向每个请求添加新区段的用户无法执行此操作，因为添加该区段会删除已分配给每个请求的前一组区段。

Report Builder 5.4允许您在多个请求中添加、删除、替换和替换所有区段：

1. 在工作簿中选择多个请求。
1. 右键单击并选择&#x200B;**[!UICONTROL 编辑请求]** > **[!UICONTROL 按区段]**。

   ![显示编辑请求并按所选区段划分的屏幕截图。](assets/edit_by_segment.png)

1. 在“编辑组”对话框中，选择以下四个选项之一：

   | 选项 | 描述 |
   |---|---|
   | 添加区段 | 可选择要添加到当前区段列表的一个或多个区段。 |
   | 替换区段 | 可选择要用一个或多个区段替换的区段。 |
   | 所有区段替换方式 | 可让您选择一个或多个区段来替换当前区段。 |
   | 删除区段 | 允许您从请求中删除区段。 |
