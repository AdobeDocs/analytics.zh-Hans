---
description: Report Builder 中“管理请求”的字段说明。
seo-description: Report Builder 中“管理请求”的字段说明。
seo-title: 管理请求-定义
solution: Analytics
title: 管理请求-定义
topic: Report Builder
uuid: 01b21d0e-c870-4df8-95b9 aef1 aef1 f4 d16 b
translation-type: tm+mt
source-git-commit: 6a70b32b576cc7b5b6a6f0037d98e35b3f8c1426

---


# 管理请求-定义

Report Builder 中“管理请求”的字段说明。

## 概述 {#section_75C288C945FA4781A4EDF806711A5660}

[!UICONTROL 请求管理器]提供一个详细视图，其中显示为活动工作簿中的所有工作表或一个工作表构建的所有请求的状态。通过右键单击 Excel 电子表格中包含先前请求的可用单元格，您还可以添加、编辑、刷新和删除请求（通常与[!UICONTROL 请求向导]和[!UICONTROL 请求管理器]相关联的功能）。

The [!UICONTROL Request Manager] displays when you click **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) in the Report Builder toolbar.

>[!NOTE]
>
>Adobe Report Builder仅强制在同一工作表内请求依赖关系，而不能在工作表中执行请求依赖项。将从属关系限制在一张工作表中可确保执行的时效性。

## 定义 {#section_FD29D8614DE74F32A0027FA130F40304}

<table id="table_0880204181074BDBBA37E3DF2972A672"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>所有工作表 </p> </td> 
   <td colname="col2"> <p>显示活动工作簿的所有工作表中的请求。要查看特定工作表中的请求，请禁用此选项。如果禁用此选项，必须单击 Excel 报表底部的工作表标签，以在<span class="wintitle">请求管理器</span>中显示与该工作表相关联的请求。复选框旁边的标签指示工作簿中的哪个工作表当前获得了焦点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>工作表 </p> </td> 
   <td colname="col2"> <p>显示工作簿中工作表的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>报表包 </p> </td> 
   <td colname="col2"> <p>显示报表包的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期范围 </p> </td> 
   <td colname="col2"> <p>显示报表的指定日期范围。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>粒度 </p> </td> 
   <td colname="col2"> <p>指定请求的粒度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 上次运行 </p> </td> 
   <td colname="col2"> <p>指定 Report Builder 上次处理请求的日期。诊断消息也会显示在此表的“<span class="wintitle">上次运行</span>”列中（如果适用）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>添加 </p> </td> 
   <td colname="col2"> <p>显示请求向导对话框。请参阅 <a href="../../../analyze/report-builder/data-requests/t-create-a-data-request.md#task_65B453C8F015429A8EA73A1B64025B6C" type="task" format="dita" scope="local"> 创建数据请求</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>编辑 </p> </td> 
   <td colname="col2"> <p> （或者“编辑多个”）编辑所选的请求。系统会显示<span class="wintitle">请求向导</span>对话框。See <a href="../../../analyze/report-builder/manage-requests/t-edit-multiple-requests.md#task_70A13DBE43CD4BBEBE1B62459ADB3AD1" type="task" format="dita" scope="local"> Edit Multiple Requests</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>删除 </p> </td> 
   <td colname="col2"> <p>删除请求。您可以删除多个选定的请求。您还可以通过选择请求并按键盘上的 Delete 键来删除列表中的请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 选择全部 </p> </td> 
   <td colname="col2"> <p>选择全部请求。<span class="wintitle">请求管理器</span>在请求列表的底部显示您选择的请求数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>从单元格 </p> </td> 
   <td colname="col2"> <p>从工作表中获取请求的数据。如果某请求与活动工作表中当前选定的单元格相关联，则列表中关联的请求处于选定状态。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 刷新 </p> </td> 
   <td colname="col2"> <p>刷新单个请求或所选的多个请求。（请参阅 <a href="../../../analyze/report-builder/manage-requests/t-refresh-a-request.md#task_96556DB051A2479A955999D3837EE609" type="task" format="dita" scope="local"> 刷新请求</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>刷新列表 </p> </td> 
   <td colname="col2"> <p>刷新显示的所有请求。刷新所有请求时，将信息从服务器更新到报表所用的时间与报表中请求的复杂程度成正比。对于大型报表，刷新所有请求可能需要数分钟的时间。因此，您可能希望单独更新最紧急的请求，然后在时间不太紧张时选择“<span class="wintitle">全部刷新</span>”。 </p> <p> <p>注意：如果您刷新包含多个请求的工作表，建议您经常在<span class="wintitle">请求管理器</span>中查看结果。如果请求失败，诊断列中的错误消息可帮助您找出错误的根源。尽管在大多数情况下请求失败时都会显示错误消息，但请注意，有时不生成错误消息。您可能会发现，刷新不更新包含引用的单元格中的数据，或者更新从单元格中删除了数据。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

