---
description: 此功能将 Report Builder 的使用进一步整合到常规 Excel 工作流程中，而无需您访问 Report Builder 用户界面。
title: 通过 Microsoft Excel 函数调用 Report Builder 功能
topic: Report builder
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 通过 Microsoft Excel 函数调用 Report Builder 功能

此功能将 Report Builder 的使用进一步整合到常规 Excel 工作流程中，而无需您访问 Report Builder 用户界面。

例如，您可能希望自动刷新Report Builder请求，其输入过滤器基于从其他来源从Excel中提取的数据。 现在，您可以使用字符串RefreshRequestsInCellsRange(..)执行此操作。函数。 所有调用都是异步的。 他们会立即返回，并且不会等待呼叫完全执行。

>[!NOTE] 您必须安装 Report Builder 5.0（或更高版本），才能使用此功能。

下面是一个表，其中列表了暴露的函数：

| 函数名 | 描述 |
|---|---|
| string AsyncRefreshAll() | 刷新工作簿中存在的所有Report Builder请求。 |
| string AsyncRefreshRange(string rangeAddressInA1Format) | 刷新指定单元格范围地址(表示A1格式的单元格范围的字符串表达式，例如“Sheet1!A2:A10”)中存在的所有Report Builder请求。 |
| string AsyncRefreshRangeAltTextParam() | 刷新在指定单元格范围内存在的所有Report Builder请求，该单元格范围通过Ms表单控件的替代文本传递。 |
| string AsyncRefreshActiveWorksheet() | 刷新活动工作表中存在的所有Report Builder请求。 |
| string AsyncRefreshWorksheet(string worksheetName) | 刷新指定工作表中存在的所有Report Builder请求（该工作表名称与选项卡上显示的工作表名称相同）。 |
| string AsyncRefreshWorksheetAltTextParam(); | 刷新特定工作表名称中的所有Report Builder请求，该工作表名称通过Ms表单控件的替代文本传递 |
| 字符串GetLastRunStatus() | 返回描述上次运行状态的字符串。 |

要在报表生成器中访问这些功能，请转 [!UICONTROL Formulas] 到> [!UICONTROL Insert Function]。 在类别的列表底部，您会找到Adobe.ReportBuilder.Bridge:

![](assets/arb_functions.png)

## 在公式中运用这些函数 {#section_034311081C8D4D7AA9275C1435A087CD}

例如，公式

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

“如果单元格P5中的值为文本或空，请刷新单元格P9中的范围。”

## 将 Report Builder 函数用于设置控件格式 {#section_26123090B5BD49748C8D8ED7A1C5ED84}

您现在可以为您创建的控件分配一个宏，该控件可以是刷新工作簿请求的函数。 例如，函数AsyncRefreshActiveWorksheet将刷新工作表中的所有请求。 但有时，您可能希望只刷新某些请求，而不是全部。

1. 设置宏参数。
1. 右键单击控件并选择 **[!UICONTROL Assign Macro]**。
1. 输入报表生成器函数名称（无参数或括号）。

![](assets/assign_macro.png)

## 将参数通过“设置控件格式”传递给 Report Builder 函数 {#section_ECCA1F4990D244619DFD79138064CEF0}

获取参数的两个函数可与格式控制一起使用，但只能通过替代文本字段使用：

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string worksheetName)

1. 右键单击控件并选择 **[!UICONTROL Format Control]**。

   ![](assets/format_control.png)

1. Click the [!UICONTROL Alt Text] tab.

   ![](assets/alt_text.png)

1. 在下 [!UICONTROL Alternative text]面，输入要刷新的单元格范围。
1. 在 [!UICONTROL Formulas] > [!UICONTROL Insert Function]>下打开报表生成器参数的列表 [!UICONTROL Adobe.ReportBuilder.Bridge]。

1. Pick one of the two functions that end with AltTextParam and click **[!UICONTROL OK]**.

