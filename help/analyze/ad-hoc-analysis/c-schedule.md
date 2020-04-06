---
description: 可以自定义报表的投放计划。 您可以在特定时间停止投放，或指定要发送报告的次数。 新计划使用报告中定义的日期范围。 例如，如果您创建了过去90天的报表并将其计划为每天运行，则您每天将收到过去90天的报表。 如果从日历创建具有静态日期范围的报表，则每次发送报表时都会看到相同的报表。
title: 计划管理器
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 计划管理器

可以自定义报表的投放计划。 您可以在特定时间停止投放，或指定要发送报告的次数。 新计划使用报告中定义的日期范围。 例如，如果您创建了过去90天的报表并将其计划为每天运行，则您每天将收到过去90天的报表。 如果从日历创建具有静态日期范围的报表，则每次发送报表时都会看到相同的报表。

## 计划管理器 {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

可以自定义报表的投放计划。 您可以在特定时间停止投放，或指定要发送报告的次数。 新计划使用报告中定义的日期范围。 例如，如果您创建了过去90天的报表并将其计划为每天运行，则您每天将收到过去90天的报表。 如果从日历创建具有静态日期范围的报表，则每次发送报表时都会看到相同的报表。

>[!NOTE]禁用某个用户帐户时，该用户创建的计划报表交付将会挂起。

To ensure that line items in a breakdown are persistent in saved and scheduled reports, use the **[!UICONTROL Edit Items]** feature in the [Table Builder](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) to create fixed dimension lists in breakdowns.

>[!IMPORTANT]
>
>Ad Hoc Analysis 允许您快速定义和计划报表，以便及时满足 Ad Hoc 报表的特定需求。它不设计为使用数据提取完全导出具有大量行数、列数、度量评估或大量细分的数据。
>
>Ad Hoc分析中调度报告的实际约束基于以下原则：如果您的报表未在10分钟内构建(临时分析超时)，则您的报表很可能过于复杂。
>
>您的报表极有可能包含过多的指标、过多的维度元素细分、过多的行或列，或其他极端情况，使临时分析的报表生成过程过长。 此类报表需要在数据仓库中运行，Adobe Analytics的这一功能使得整个数据提取能够脱机运行并生成报表，这可能需要花费数小时或数天的时间。
>
>例如，临时分析可以处理50,000行数据，但将十种浏览器类型的数据细分意味着50,000次10，这是指数级增长，对于临时报告工具而言可能过于复杂。 其他细分会再次以指数级增加数据行。 为临时分析报告定义实际数或行、列和细分，不能用明确的术语进行定义，而是所有这些因素的组合。

## 计划报表提交 {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

描述如何计划报表提交的步骤。

<!-- 

t_schedule_delivery.xml

 -->

1. 单 **[!UICONTROL Tools]**&#x200B;击，然后单击 **[!UICONTROL Schedule Manager]**。
1. 在上 [!UICONTROL Schedule Manager]，单击 **[!UICONTROL New.]**

## 提交选项 - 定义 {#reference_CA49AC560258471AAE959BCA243F170C}

“投放选项”设置的定义。

<!-- 

r_delivery_options.xml

 -->

您可以将当前选定报告中显示的信息发送到您选择的格式。 您可以一次发送它或设置投放计划，然后指定您喜欢的文件格式。 您可以创建并发送数字签名以确保文件的接收者签名是正版的。 您可以将文件发送到电子邮件地址或将其上传到FTP服务器。

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>字段 </p> </th> 
   <th colname="col2" class="entry"> <p>定义 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>名称 </p> </td> 
   <td colname="col2"> <p> 此报告的可配置名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>告诉您报表ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 文件格式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel:在电子表格中输出报表，包括所有图像。 可在Microsoft Excel中编辑。 </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV:以逗号分隔值输出报表。 在简单的文本编辑器（如记事本）或电子表格编辑器（如Excel）中可编辑。 不包含任何图像。 </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF:以可移植文档格式输出报表。 在Adobe Acrobat或Adobe Reader中不可编辑和查看。 </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML:以超文本标记语言附件输出报表。 此格式是大多数网站的组成部分。 除非您熟悉HTML代码，否则不可编辑。 </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word:以富文本格式输出报表，包括所有图像。 可在Microsoft Word或WordPad中编辑。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 高级 </p> </td> 
   <td colname="col2"> <p> 请参阅<a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   >高级格式设置</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>文件目标 </p> </td> 
   <td colname="col2"> <p>电子邮件：通过电子邮件发送的设置。 </p> <p>FTP:上传到FTP服务器的设置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>报告范围和投放计划 </p> </td> 
   <td colname="col2"> <p>指定何时传送报表。 新计划使用报告中定义的日期范围。 例如，如果您创建了过去90天的报表并将其计划为每天运行，则您每天将收到过去90天的报表。 如果从日历创建具有静态日期范围的报表，则每次发送报表时都会看到相同的报表。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 高级格式设置 - 定义 {#reference_F99B65BF7C9746638D8147EED147015B}

“高级格式设置”设置的定义。

<!-- 

r_advanced_format_settings_dsc.xml

 -->

<table id="table_CD0888E8390745F4B83DF6AC69CB0854"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>字段 </p> </th> 
   <th colname="col2" class="entry"> <p>定义 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>文件名 </p> </td> 
   <td colname="col2"> <p>用户定义的文件名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将ID追加到文件名 </p> </td> 
   <td colname="col2"> <p>自动将报告ID附加到文件名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 将日期追加到文件名 </p> </td> 
   <td colname="col2"> <p> 自动将报告的日期附加到文件名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>语言 </p> </td> 
   <td colname="col2"> <p> 允许您为报表选择语言。 无论您使用何种语言，都可以使用以下任何语言发送报告 </p> 
    <ul id="ul_BD3D331B0D6146F79A6D254136E43920"> 
     <li id="li_0EE6A371B1BB4627BD3F64BD0EF07E44">英语 </li> 
     <li id="li_5EF76261928543FDB36D99E4C89DE994">西班牙语 </li> 
     <li id="li_FABF47E8CD64486BA1567E02460422C5">简体中文 </li> 
     <li id="li_8A6BC2DE92DB47DA9397B8931D8DCC6E">繁体中文 </li> 
     <li id="li_EDA24D700BE040E8B839B82E31DABC28">法语 </li> 
     <li id="li_A8D41DCCC91542BB8D0A522EC99575E8">德语 </li> 
     <li id="li_E9F73C93C94A46B78BCE85A7261CEDD4">日语 </li> 
     <li id="li_699B97050AA54D818659C191F4594E4E">葡萄牙语 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>编码 </p> </td> 
   <td colname="col2"> <p>指定编码类型。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 以压缩文件的形式发送报告 </p> </td> 
   <td colname="col2"> <p> 压缩文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>发送数字签名文件 </p> </td> 
   <td colname="col2"> <p>创建要随电子邮件一起发送的数字签名。 </p> </td> 
  </tr> 
 </tbody> 
</table>

