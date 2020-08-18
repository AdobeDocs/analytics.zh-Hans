---
title: Report Builder中的Visual Basic宏
description: 使用VBA扩展Excel工作簿和Report Builder的功能。
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# Report Builder中的Visual Basic宏

VBA宏也称为Visual Basic宏，它允许您以单靠Microsoft Excel无法操作的方式操作工作簿。 Visual Basic有权访问工作簿、Excel甚至Windows。

Adobe支持三种Report BuilderAPI方法。 确保已安装最新版本的report builder，并在运行任何宏之前登录。

>[!IMPORTANT]
>
>出于安全原因，您无法计划包含宏的工作簿。

## `RefreshAllReportBuilderRequests()`

The `RefreshAllReportBuilderRequests()` macro refreshes all Report Builder requests in the active workbook. 它通过通过其产品ID调用Report BuilderCOM Add-in来开始，然后调用API `RefreshAllRequests()` 命令：

```vba
Sub RefreshAllReportBuilderRequests()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshAllRequests(ActiveWorkbook)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInActiveWorksheet()`

The `RefreshAllReportBuilderRequestsInActiveWorksheet()` macro refreshes all Report Builder requests in the active worksheet. API `RefreshWorksheetRequests()` 调用将工作表对象作为参数。 您可以对包含Report Builder请求的任何工作表使用此调用：

```vba
Sub RefreshAllReportBuilderRequestsInActiveWorksheet()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshWorksheetRequests(ActiveWorkbook.ActiveSheet)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInCellsRange()`

The `RefreshAllReportBuilderRequestsInCellsRange()` macro refreshes all Report Builder requests whose cell outputs intersect the specified range of cells. 此示例中使用的单元格范围指向活 `B1:B54` 动工作簿中“数据”工作表的范围。 范围表达式支持所有支持的Excel范围表达式:

```vba
Sub RefreshAllReportBuilderRequestsInCellsRange()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshRequestsInCellsRange("'Data'!B1:B54")
  
End Sub
```
