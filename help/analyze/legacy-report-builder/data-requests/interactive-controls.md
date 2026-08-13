---
description: 交互式控件允许您直接从工作表中编辑一个或多个请求的区段和日期范围。 这让您在更新Report Builder请求时可以更加灵活。
title: 交互式控件
feature: Report Builder
role: User, Admin
exl-id: 2340ff31-1478-4a54-a4c3-c51e73c39109
TQID: https://experienceleague.adobe.com/I1Lw6gp33QByF6J9SZRgTdn30CpdhJH3yWZ5XwOkBqc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 603
ht-degree: 27%

---

# 交互式控件

{{legacy-arb}}

交互式控件允许您直接从工作表中编辑一个或多个请求的区段和日期范围。 这让您在更新Report Builder请求时可以更加灵活。

创建交互式控件是为了响应一个通用工作流，其中分析人员创建工作簿并与营销组织共享这些工作簿。 通过交互式控件，营销人员无需深入了解Report Builder的工作方式，即可修改和刷新请求。 （请注意，要刷新请求，工作簿收件人必须是Report Builder用户。） 这些控件在计划工作簿内工作。 目前有两种交互式控件可用：

* 滚动日期范围
* 区段

>[!IMPORTANT]
>
>必须安装 Report Builder v5.0 才能使用交互控件。 >
>* 如果您在Windows上运行Microsoft Excel，但运行较低版本的Report Builder，或者如果您未安装Report Builder：您可以更改交互控件中的值，但不会刷新关联的请求，也不会更新请求的相关参数。
>* 如果您在 Mac 上运行 Excel，则更改控件中的值将会导致显示以下消息：“找不到宏‘Adobe.ReportBuilder.Bridge.FormControlClick.Event’。”
>

>[!WARNING]
>
>切勿篡改控件的名称。 （要查看名称，请将焦点置于控件上，此时控件名称便会出现在左上角 Excel 网格的正上方。）

## 实现交互式日期范围控件 {#section_39B228F2D2C44985863D31424C953280}

1. 在“请求向导”的第 1 步中，例如，选择&#x200B;**[!UICONTROL 页面]**&#x200B;报表。
1. 在&#x200B;**[!UICONTROL 常用日期]**&#x200B;下拉列表的旁边，单击&#x200B;**[!UICONTROL 控件设置]**&#x200B;图标：

   ![“请求向导：第1步”屏幕截图，突出显示“控件设置”图标。](assets/date_range_control.png)

1. 在“控件设置”对话框中，选择要显示在交互式控件中的所有日期范围项。 此外，指定控件的左上角单元格位置。

   ![显示选定日期范围项和左上角单元格位置的屏幕截图。](assets/control_settings.png)

1. 请注意“根据项目选择自动刷新链接的请求”选项。

   * 如果选中，则使用此控件的所有请求都将刷新。
   * 如果未选中，则会更新关联的请求参数，但不会刷新请求。

1. 单击&#x200B;**[!UICONTROL 确定]**。 该控件会出现在您指定的单元格位置：

1. 您现在可以更改日期范围，请求将使用该日期范围进行刷新。

   ![显示选定日期范围的屏幕快照。](assets/date_range_control_interactive.png)

1. 您还可以复制请求，然后右键单击以使用两个“粘贴请求”选项之一：

   * **[!UICONTROL 粘贴请求]** > **[!UICONTROL 使用绝对输入单元格]**。 这意味着复制的请求将指向与原始请求相同的交互式日期范围控件。

   * **[!UICONTROL 粘贴请求]** > **[!UICONTROL 使用相对输入单元格]**。 这意味着复制的请求将指向其自身的控件。

     >[!NOTE]
     >
     >您可以使用本机 Microsoft Excel“剪切”/“复制”/“粘贴”控件功能。 Report Builder 会自动识别新添加的控件。

## 实现交互式区段控件 {#section_5003D3F724644280BF1BCD6E1B0CB784}

实施交互区段控件与实施日期范围控件类似。

1. 在请求向导的第1步中，在&#x200B;**[!UICONTROL 区段]**&#x200B;下拉列表的旁边，选择“区段控制设置”图标：

   ![区段控件设置图标屏幕截图。](assets/segment_interactive_1.png)

1. 在区段控制设置对话框中，选择要包含在下拉列表中的区段。 此外，指定控件的左上角单元格位置。

   ![显示选定区段和单元格位置的“区段控制设置”的屏幕截图。](assets/segment_drop_down_properties.png)

1. 新的交互式控件现在将显示在工作簿中：

   ![显示选定新交互控件的屏幕截图。](assets/segment_interactive_3.png)
