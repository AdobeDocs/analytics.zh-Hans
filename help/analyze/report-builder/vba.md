---
title: Report Builder 中的 Visual Basic 宏
description: 使用 VBA 扩展 Excel 工作簿和 Report Builder 的功能。
translation-type: ht
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: ht
source-wordcount: '196'
ht-degree: 100%

---


# Report Builder 中的 Visual Basic 宏

VBA 宏（也称为 Visual Basic 宏），它允许您以单靠 Microsoft Excel 无法实现的方式来操作工作簿。Visual Basic 可以访问工作簿、Excel 甚至是 Windows。

Adobe 支持三种 Report Builder API 方法。请确保安装了最新版本的 Report Builder，并在运行任何宏之前登录。

>[!IMPORTANT]
>
>出于安全原因，您不能计划包含宏的工作簿。

## `RefreshAllReportBuilderRequests()`

`RefreshAllReportBuilderRequests()` 宏会刷新活动工作簿中的所有 Report Builder 请求。首先，通过产品 ID 调用 Report Builder COM 加载项，然后调用 `RefreshAllRequests()` API 命令：

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

`RefreshAllReportBuilderRequestsInActiveWorksheet()` 宏会刷新活动工作表中的所有 Report Builder 请求。`RefreshWorksheetRequests()` API 调用会将工作表对象作为参数。您可以对包含 Report Builder 请求的任何工作表使用此调用：

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

`RefreshAllReportBuilderRequestsInCellsRange()` 宏会刷新单元格输出与指定单元格范围相交的所有 Report Builder 请求。此示例中使用的单元格范围指向活动工作簿中“Data”工作表的范围 `B1:B54`。范围表达式支持所有受支持的 Excel 范围表达式：

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
