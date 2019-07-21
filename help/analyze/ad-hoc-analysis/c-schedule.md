---
description: 您可以自定义报表的提交计划。可以在特定时间停止提交操作，或指定发送报表的次数。新计划使用在报表中定义的日期范围。例如，如果针对过去 90 天创建一个报表，并计划每天运行该报表，则会每天收到针对过去 90 天的报表。如果您从日历创建了一个固定日期范围的报表，则在每次发送此报表时您将看见相同的报表。
seo-description: 您可以自定义报表的提交计划。可以在特定时间停止提交操作，或指定发送报表的次数。新计划使用在报表中定义的日期范围。例如，如果针对过去 90 天创建一个报表，并计划每天运行该报表，则会每天收到针对过去 90 天的报表。如果您从日历创建具有静态日期范围的报表，则在每次发送此报表时您将看见相同的报表。
seo-title: 计划管理器
solution: Analytics
title: 计划管理器
topic: Ad Hoc Analysis
uuid: 82a054ef-109d-414d-6e1-e09 ee57 c163 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 计划管理器

您可以自定义报表的提交计划。可以在特定时间停止提交操作，或指定发送报表的次数。新计划使用在报表中定义的日期范围。例如，如果针对过去 90 天创建一个报表，并计划每天运行该报表，则会每天收到针对过去 90 天的报表。如果您从日历创建了一个固定日期范围的报表，则在每次发送此报表时您将看见相同的报表。

## 日程安排管理器 {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

您可以自定义报表的提交计划。可以在特定时间停止提交操作，或指定发送报表的次数。新计划使用在报表中定义的日期范围。例如，如果针对过去 90 天创建一个报表，并计划每天运行该报表，则会每天收到针对过去 90 天的报表。如果您从日历创建了一个固定日期范围的报表，则在每次发送此报表时您将看见相同的报表。

>[!NOTE]
>
>禁用某个用户帐户后，该用户创建的任何计划报告交付将被挂起。

To ensure that line items in a breakdown are persistent in saved and scheduled reports, use the **[!UICONTROL Edit Items]** feature in the [Table Builder](../../analyze/ad-hoc-analysis/c-tablebuilder.md#concept_664FC77306E148DBA4EA081814943C5E) to create fixed dimension lists in breakdowns.

>[!IMPORTANT]
>
>临时分析可让您快速定义和计划报告，以满足特定、及时、专门的报告需求。它本身并不适合通过数据提取来完整地导出含有大量行、列、量度评估或庞大划分的数据。
>
>在对 Ad Hoc Analysis 中的计划报表进行实际限制时，应当基于以下原则：如果不能在十分钟内（Ad Hoc Analysis 的超时期限）构建报表，则说明报表很可能过于复杂。
>
>您的报表很可能包含过多的量度、过多的维度元素划分、过多的行或列，或者其他极端情况，这会导致 Ad Hoc Analysis 报表的生成过程过于漫长。这种类型的报表需要在 Data Warehouse 中运行，它是一项 Adobe Analytics 功能，适用于可能需要长达数小时或数天来生成提取了完整数据的报表（脱机运行）。
>
>例如，Ad Hoc Analysis 可处理 50,000 行数据，但是如果将数据划分为十种浏览器类型，那就意味着面临 50,0000 乘以 10 的处理量，这种指数级的增长对于一个临时报告工具而言可能过于复杂。更多其他划分还会再次以指数形式增加数据的行数。应当定义行、列和划分的实际数量，以对其加以限制，因为 Ad Hoc Analysis 报告无法以明确的术语进行定义，但是却综合了所有这些因素。

## 计划报表提交 {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

描述如何计划报表提交的步骤。

<!-- 

t_schedule_delivery.xml

 -->

1. Click **[!UICONTROL Tools]**, then click **[!UICONTROL Schedule Manager]**.
1. 在[!UICONTROL 计划管理器]**中，单击“新建”。**

## 提交选项 - 定义 {#reference_CA49AC560258471AAE959BCA243F170C}

“提交选项”中各项设置的定义。

<!-- 

r_delivery_options.xml

 -->

您可以将当前选定报表内显示的信息发送到所选的格式。您可一次发送或设置提交计划，并指定您倾向的文件格式。您可创建和发送数字签名以确保文件的接收者认为其可信。您可将文件发送到电子邮件地址或上传到 FTP 服务器。

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
   <td colname="col2"> <p> 此报表的可配置名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>告诉您报表 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 文件格式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel：以电子表格输出您的报表，包括所有图像。可在 Microsoft Excel 中编辑。 </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV：以逗号分隔值文件输出您的报表。可在简单的文本编辑器（例如“记事本”）或电子表格编辑器（例如 Excel）中编辑。不包含任何图像。 </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF：以便携文档格式输出您的报表。无法在 Adobe Acrobat 或 Adobe Reader 中编辑和查看。 </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML：以超文本标记语言附件输出您的报表。此格式是构成大多数网页的格式。除非您熟悉 HTML 代码，否则不可编辑。 </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word：以富文本格式输出您的报表，包括所有图像。可在 Microsoft Word 或“写字板”中编辑。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 高级 </p> </td> 
   <td colname="col2"> <p> See <a href="../../analyze/ad-hoc-analysis/c-schedule.md#reference_F99B65BF7C9746638D8147EED147015B" type="reference" format="dita" scope="local"> Advanced Format Settings</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>文件目标 </p> </td> 
   <td colname="col2"> <p>电子邮件：通过电子邮件发送的设置。 </p> <p>FTP：上传到 FTP 服务器的设置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>报表范围和提交计划 </p> </td> 
   <td colname="col2"> <p>指定提交报表的时间。新计划使用在报表中定义的日期范围。例如，如果针对过去 90 天创建一个报表，并计划每天运行该报表，则会每天收到针对过去 90 天的报表。如果您从日历创建了一个固定日期范围的报表，则在每次发送此报表时您将看见相同的报表。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 高级格式设置 - 定义 {#reference_F99B65BF7C9746638D8147EED147015B}

“高级格式设置”上各项设置的定义。

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
   <td colname="col1"> <p>将 ID 附加到文件名 </p> </td> 
   <td colname="col2"> <p>自动将报表 ID 附加到文件名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 将 ID 附加到文件名 </p> </td> 
   <td colname="col2"> <p> 自动将报表日期附加到文件名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>语言 </p> </td> 
   <td colname="col2"> <p> 用于为报表选择一种语言。不论您使用何种语言，都可以发送以下任意一种语言的报表 </p> 
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
   <td colname="col1"> <p> 以压缩文件发送报表 </p> </td> 
   <td colname="col2"> <p> 压缩文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>发送数字签名文件 </p> </td> 
   <td colname="col2"> <p>创建随电子邮件一起发送的数字签名。 </p> </td> 
  </tr> 
 </tbody> 
</table>

