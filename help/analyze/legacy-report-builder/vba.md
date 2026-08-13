---
title: 如何在Report Builder中使用Visual Basic宏
description: 了解如何使用VBA宏扩展Excel工作簿和Report Builder的功能。
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
TQID: https://experienceleague.adobe.com/RxOpojtJn2vi5uMO8CGzCCm7FcPp4qVwbH-XTEBSRsY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 195
ht-degree: 64%

---

# Report Builder 中的 Visual Basic 宏

{{legacy-arb}}

Visual Basic (VBA)宏提供的功能可帮助您刷新Excel工作簿。 Visual Basic可以访问工作簿、Excel和Windows。

运行VBA宏之前，必须运行最新版本的Report Builder并登录。

>[!IMPORTANT]
>
>出于安全原因，您不能计划包含宏的工作簿。

Adobe支持三种Report Builder API方法。

## `RefreshAllReportBuilderRequests()`

`RefreshAllReportBuilderRequests()` 宏会刷新活动工作簿中的所有 Report Builder 请求。 首先，通过产品 ID 调用 Report Builder COM 加载项，然后调用 `RefreshAllRequests()` API 命令：

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

`RefreshAllReportBuilderRequestsInActiveWorksheet()` 宏会刷新活动工作表中的所有 Report Builder 请求。 `RefreshWorksheetRequests()` API 调用会将工作表对象作为参数。 您可以对包含 Report Builder 请求的任何工作表使用此调用：

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

`RefreshAllReportBuilderRequestsInCellsRange()` 宏会刷新单元格输出与指定单元格范围相交的所有 Report Builder 请求。 此示例中使用的单元格范围指向活动工作簿中“Data”工作表的范围 `B1:B54`。 范围表达式支持所有受支持的 Excel 范围表达式：

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
