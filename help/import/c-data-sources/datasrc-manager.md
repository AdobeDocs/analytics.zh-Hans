---
description: 创建、管理和查看报表包中数据源的使用情况。
subtopic: Data sources
title: 数据源管理器
topic-fix: Developer and implementation
feature: Data Sources
exl-id: a63137b8-deeb-4865-9be9-322416b00186
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: ht
source-wordcount: '473'
ht-degree: 100%

---

# 数据源管理器

创建、管理和查看报表包中数据源的使用情况。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 数据源]**。

## “创建”选项卡 {#section_74603FDA3D8842E49F1A51624A06DE20}

[!UICONTROL 创建]选项卡允许您为当前选中的报表包配置新的数据源。在激活数据源后，[!UICONTROL 数据源向导]会引导您完成创建数据源模板的过程，然后为上传数据创建一个 FTP 位置。

您在“创建”选项卡中所做的选择决定了所创建模板中的初始字段。请参阅[生成导入文件模板](/help/import/c-data-sources/datasrc-template/t-datasrc-creating-data-sources-file.md)。

## “管理”选项卡 {#section_DD559A6701CA45F1A85E56F840F48DBE}

<table id="table_F74696EC855441328CFE0BF49C20D9B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>选项 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>重新启动处理 </p> </td> 
   <td colname="col2"> <p>重新启动之前由于出错或警告而停止的数据源处理。处理将继续进行，直到发生下一个错误为止。只有在选择<span class="uicontrol">出错时停止处理</span>的情况下，数据源才会中断数据源文件的处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>完成处理 </p> </td> 
   <td colname="col2"> <p>指示数据源关闭文件中一切打开的访问，并结束数据源文件的处理（就好像处理已完成）。这在您的访问跨越了多个数据源文件时很有用。该选项仅适用于<a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   >完全处理</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>停用 </p> </td> 
   <td colname="col2"> <p> 如果停用数据源，则会将其删除。如果已开始处理服务器上的任何文件，则此处理过程将继续进行，直到完成为止。尚未开始处理的文件将不会被处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>出错或警告时停止处理 </p> </td> 
   <td colname="col2"> <p> 指示数据源处理引擎在遇到错误时停止处理。您选择重新启动处理之前，数据源不会恢复处理。“警告时停止处理”选项仅适用于<a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   >完全处理</a>。 </p> <p>当数据源遇到文件错误时，它会通知您该错误。系统会将出错的数据源文件移到 FTP 服务器上名为 <span class="filepath">files_with_errors</span> 的文件夹中。在问题解决之后，请重新提交数据源文件进行处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>配置 </p> </td> 
   <td colname="col2"> <p>允许您修改数据源模板，或此数据源的其他特定设置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FTP 信息 </p> </td> 
   <td colname="col2"> <p>显示此数据源的 FTP 信息。使用此信息访问数据源模板，并发送数据源数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>文件名 </p> </td> 
   <td colname="col2"> <p>已上传文件的名称 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>状态 </p> </td> 
   <td colname="col2"> <p> 文件的当前状态。可能的状态值包含以下几个： </p> 
    <ul id="ul_56A0BF8C1BE249F6BB39B0D11DA3997F"> 
     <li id="li_BAB359E08EDE4E0298C0362258789603">队列中（步骤 1，共 3 步）：文件存在，但是未开始处理。如果文件没有在 30 分钟内显示，请检查关联的 <span class="filepath">.fin</span> 文件是否存在 </li> 
     <li id="li_A09A14F42CB74F01B694799740B3DA17">准备中（步骤 2，共 3 步）：正在检查文件是否出现错误或警告。 </li> 
     <li id="li_793FDCDB64CF434D82CAF5B6E9BDE557">处理中（步骤 3，共 3 步）：正在处理文件。 </li> 
     <li id="li_1D8C4B241FF0453EAF7DDFD8354C5573">失败：文件由于出错而无法处理。 </li> 
     <li id="li_A52507602FB4492B83A70AF6449A539A">成功：文件已成功处理。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## “文件日志”选项卡 {#section_B7AC7EE8CAD740A59DD53CF1919373F0}

“文件日志”选项卡包括一个搜索功能，可按数据源名称、数据源类型、文件名、接收日期或状态搜索信息。
