---
description: 了解如何将Microsoft Excel与Report Builder函数结合使用，而无需访问Report Builder用户界面。
title: 了解如何将Microsoft Excel与Report Builder函数结合使用
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
TQID: https://experienceleague.adobe.com/cgDjTqGH0KzSrpg66sRfF8Kf81Q-WDwSWJ-OBvJK8DM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 6%

---

# 将Report Builder函数与Microsoft Excel结合使用

{{legacy-arb}}

您可以使用Report Builder函数来访问功能，而无需访问Report Builder用户界面。

例如，要使用基于从其他来源提取到Excel中的数据的输入过滤器自动刷新Report Builder请求，请使用字符串RefreshRequestsInCellsRange(..) 函数。 所有调用均为异步调用，它们会立即返回，而不会等待完全执行。

**要求**

* 需要Report Builder 5.0（或更高版本）。

下表列出了公开的功能。

| 函数名称 | 类型 | 描述 |
|:---| --- | ---|
| AsyncRefreshAll() | 字符串 | 刷新工作簿中存在的所有Report Builder请求。 |
| AsyncRefreshRange(string rangeAddressInA1Format) | 字符串 | 刷新指定单元格范围地址中存在的所有Report Builder请求（字符串表达式，表示A1格式的单元格范围，例如“Sheet1！A2:A10”）。 |
| AsyncRefreshRangeAltTextParam() | 字符串 | 刷新通过Ms表单控件的替换文本传递的指定单元格范围内的所有Report Builder请求。 |
| AsyncRefreshActiveWorksheet() | 字符串 | 刷新活动工作表中存在的所有Report Builder请求。 |
| AsyncRefreshWorksheet(string worksheetName) | 字符串 | 刷新指定工作表中存在的所有Report Builder请求（显示在选项卡上的工作表名称）。 |
| AsyncRefreshWorksheetAltTextParam()； | 字符串 | 刷新通过Ms表单控件的替换文本传递的特定工作表名称中存在的所有Report Builder请求 |
| tring GetLastRunStatus() | 字符串 | 返回描述上次运行状态的字符串。 |

若要访问Report Builder函数，请转到&#x200B;**[!UICONTROL 公式]** > **[!UICONTROL 插入函数]**。 使用搜索字段搜索函数，或者选择一个类别以列出该类别中的函数。

![显示“插入函数”窗口（类别列表已展开）的屏幕截图。](assets/arb_functions.png)

## 示例 {#section_034311081C8D4D7AA9275C1435A087CD}

以下示例显示&#x200B;*如果单元格P5中的值为文本或为空，请刷新单元格P9*&#x200B;中的范围。

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

## 将Report Builder函数与格式控件结合使用 {#section_26123090B5BD49748C8D8ED7A1C5ED84}

您可以将宏分配给您创建的控件，该控件可以是刷新工作簿请求的函数。 例如，函数AsyncRefreshActiveWorksheet将刷新工作表中的所有请求。 但是，有时您可能只想刷新某些请求。

1. 设置宏参数。
1. 右键单击控件并选择&#x200B;**[!UICONTROL 指定宏]**。
1. 输入Report Builder函数名称（不包含参数或圆括号。）

![显示“指定宏”窗口的屏幕截图。](assets/assign_macro.png)

## 使用格式控件将参数传递给Report Builder函数 {#section_ECCA1F4990D244619DFD79138064CEF0}

带有参数的两个函数可用于“格式控制”。 您必须使用&#x200B;**替换文本：**&#x200B;字段：

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string worksheetName)

使用格式控件将参数传递给Report Builder函数

1. 右键单击控件并选择&#x200B;**[!UICONTROL 设置控件格式]**。

   ![显示选定格式控件的屏幕截图。](assets/format_control.png)

1. 单击&#x200B;**[!UICONTROL 替换文本]**&#x200B;选项卡。

   ![显示“替换文本”选项卡和“替换文本”字段的屏幕截图。](assets/alt_text.png)

1. 在&#x200B;**[!UICONTROL 替换文本]**&#x200B;下，输入要刷新的单元格范围。
1. 在&#x200B;**[!UICONTROL 公式]** > **[!UICONTROL 插入函数]**> **[!UICONTROL Report Builder.Adobe.Bridge.ReportBuilder]**&#x200B;下打开参数列表。

1. 选取以 AltTextParam 结尾的两个函数之一，然后单击&#x200B;**[!UICONTROL 确定]**。
