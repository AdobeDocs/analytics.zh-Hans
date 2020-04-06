---
description: 如何在 Report Builder 中添加、编辑、应用和过滤 Adobe Analytics 区段。
title: 管理区段
topic: Report builder
uuid: 4e4edc39-ed93-498f-913d-7b231b10e7a0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 管理区段

如何在 Report Builder 中添加、编辑、应用和过滤 Adobe Analytics 区段。

Report Builder在请求向导的步骤1中提供了一个分段面板，可让您创建和管理区段。

![](assets/seg_dialog.png)

## 添加或编辑区段 {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE] 添加或编辑区段时，Report Builder 区段界面会在 Microsoft Internet Explorer 窗口中启动 Analytics 区段生成器。您的报表生成器会话将保持活动状态。 此操作不支持Internet Explorer以外的浏览器。

1. 在请求向导第1步的区段面板中，单击 **[!UICONTROL Add]**。
1. 此时将启动Internet Explorer窗口，打开Analytics区段生成器界面。 有关如何构建区段的信息，请参阅 [https://marketing.adobe.com/resources/help/en_US/analytics/segment/](https://marketing.adobe.com/resources/help/zh_CN/analytics/segment/)。
1. 定义并保存区段后，返回请求向导。
1. 单击刷新图标以刷新区段列表。

>[!IMPORTANT]
>
>该列表已缓存，新建区段只有在刷新后才会出现。

## 创建关联区段 {#section_6DD2C663B2854469AA1075438F907678}

您可能希望将特定的报表维度组合转换为区段。您可以从Report Builder界面创建这些区段。 例如，从页面请求输出中选择几个页面，然后根据这些值创建区段。

1. 选择要转换为区段的报表输出项。
1. Right-click to select **[!UICONTROL Create In-Context Segment in]** and specify the right container (Hits Container, Visits Container, Visitor Container).

   ![](assets/seg_in_context.png)

   有关容器的详细信息，请参阅分 [段指南](https://marketing.adobe.com/resources/help/zh_CN/analytics/segment/)。

1. 区段生成器UI现在将在Internet Explorer中启动。 区段生成器UI将使用您指定的容器和过滤器进行初始化。
1. 在您为区段添加名称和说明后，请保存它。
1. 返回报表生成器，单击刷新图标以刷新区段的列表。
1. 您现在可以应用此区段。

## 搜索并应用区段 {#section_CACA269B48E94CFD91C2D5A15E9C77B7}

此区段列表中会显示在 Reports &amp; Analytics、Ad Hoc Analysis、Report Builder 或 Data Warehouse 中创建的所有区段。要刷新该列表，请单击“刷新”图标 (![](assets/refresh_icon.png))。

您可以将一个或多个区段应用到任何给定请求。 这包括顺序区段。

1. Go to the **[!UICONTROL Segment]** drop-down list and click the small down arrow in the **[!UICONTROL Choose Segment]** box to display all the segments.

   ![](assets/seg_list.png)

1. 选中要应用的区段。

>[!NOTE] 不论您是否为管理员，在 Report Builder 中，您都只能查看那些您拥有的区段以及与您共享的区段。（在市场营销 Reports &amp; Analytics 用户界面中，管理员可以查看组织中的所有区段）。

## 过滤区段 {#section_376E986D3E684999A7CDB08E53854159}

通过单击“过滤器”图标 **，可以**&#x200B;过滤![](assets/segment_filter.png)区段。

可用过滤器包括：

| 过滤器名称 | 描述 |
|---|---|
| 标记 | 允许您使用特定标记筛选区段。 请注意，标记过滤器使用AND运算符。 如果选中两个标记，右侧窗格将显示已用这两个标记标记的 **区段** 。 |
| 所有者 | 允许您按所有者筛选区段。 请注意，所有者过滤器使用OR运算符。 如果选中两个所有者，则右侧窗格将显示由任一所有者拥有的 **区段** 。 |
| 其他过滤器>仅 *报告包名称* | 如果您在 [!DNL marketing reports & analytics] 中应用区段生成器的“仅&#x200B;*报表包名称*”过滤器，然后在 [!DNL report builder] 中显示“高级过滤器”，则“高级过滤器”将仅显示选定报表包的区段。 |
| 其他过滤器 > 我的 | 显示您拥有的所有区段。 |
| 其他过滤器 > 与我共享 | 显示其他人与您共享的所有区段。 |
| 其他过滤器>收藏夹 | 显示标记为“收藏夹”的所有区段。 |
| 其他过滤器>已批准 | 显示所有正式批准的区段。 |

## 向工作簿添加区段控件 {#section_E3E5149A8464441FA5445A98DBD520AC}

通过添加区段控件，您可以从工作簿中切换区段，而不必转至“请求向导”。

1. 单击区段下拉列表旁边的“控件”图标 (![](assets/control_icon.png))。

   ![](assets/seg_control.png)

1. 检查要显示在区段控件中的所有区段，或检查 **[!UICONTROL Select All]**。
1. 注意此选 **[!UICONTROL Automatically refresh linked requests upon item selection]**&#x200B;项。

   * 如果选中此选项，则会刷新使用此控件的所有请求。
   * 如果未选中此项，则会更新关联的请求参数，但不会刷新请求。

1. 指定段控件的左上角的单元格位置。
1. 单 **[!UICONTROL OK]** 击，区段控件将显示在指定位置。

   ![](assets/seg_control2.png)

## 刷新区段的列表 {#section_22E4A86789444B4A998532396B476EFB}

无论您何时添加了新区段或编辑了现有区段，都应单击“刷新”图标 (![](assets/refresh_icon.png)) 以刷新缓存的区段列表。

## 跨请求管理区段 {#section_C3D63FCBE1A94369A319243313B03C93}

在v5.4之前，Report Builder允许用户在多个请求中更改区段。 但是，此过程始终会替换现有区段。 希望向每个请求添加一个新区段的用户无法执行此操作，因为添加区段将删除已分配给每个请求的前一组区段。

Report Builder 5.4允许您添加、删除、替换和替换多个请求中的所有区段：

1. 在工作簿中选择多个请求。
1. 右键单击并选择 **[!UICONTROL Edit Requests]** > **[!UICONTROL By Segment]**。

   ![](assets/edit_by_segment.png)

1. 在“编辑组”对话框中，选择以下四个选项之一：

   | 选项 | 描述 |
   |---|---|
   | 添加 区段 | 允许您选择一个或多个区段以添加到当前区段的列表。 |
   | 替换区段 | 允许您选择要替换为一个或多个区段的区段。 |
   | 将所有区段替换为 | 允许您选择一个或多个区段，以将当前区段替换为。 |
   | 删除区段 | 允许您从请求中删除区段。 |

