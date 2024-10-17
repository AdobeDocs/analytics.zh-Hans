---
title: 如何在Report Builder中使用Visual Basic宏
description: 了解如何使用VBA宏扩展Excel工作簿和Report Builder的功能。
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 64%

---

# Report Builder 中的 Visual Basic 宏

{{legacy-arb}}

Visual Basic (VBA)宏提供的功能可帮助您刷新Excel工作簿。 Visual Basic可以访问工作簿、Excel和Windows。

运行VBA宏之前，必须运行最新版本的Report Builder并登录。

>[!IMPORTANT]
>
>出于安全原因，您不能计划包含宏的工作簿。

Adobe支持三种Report BuilderAPI方法。

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
