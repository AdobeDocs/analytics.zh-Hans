---
description: 计划任务管理器的字段说明。
seo-description: 计划任务管理器的字段说明。
seo-title: 计划任务管理器
solution: Analytics
title: 计划任务管理器
topic: Report Builder
uuid: dc259f0-2a04-4c94-abbc-5008cf2 f1 cb8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 计划任务管理器

计划任务管理器的字段说明。

计划任务管理器允许您查看现有计划报表的列表，及其收件人、计划详细信息和文件格式。它还允许您重新激活运行失败的计划工作簿。

<table id="table_21B07A0B5F1D4435A4E882E45A7A6B6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>计划报表</b>选项卡 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>报表名称 </p> </td> 
   <td colname="col2"> <p>指示计划任务的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 电子邮件/FTP </p> </td> 
   <td colname="col2"> <p>收件人的电子邮件或 FTP 地址。 </p> <p>注意：如果选择了电子邮件，那么大于 1MB 的报表将自动作为 .zip 文件添加到邮件附件中。此功能有助于保持较小的附件文件大小，您无法禁用该功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>发布选项 </p> </td> 
   <td colname="col2"> <p>如果选中了其中一个<a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#concept_0C4105AA10F9460A872C2489C9CD7945" format="dita" scope="local">Power BI 发布选项</a>，此列将列出 Power BI。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>计划 </p> </td> 
   <td colname="col2"> <p>计划的提交类型。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 文件格式 </p> </td> 
   <td colname="col2"> <p> 报表的提交格式，如 Excel、PDF、HTML 等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>重新激活 </p> </td> 
   <td colname="col2"> <p>计划工作簿无法运行时，Report Builder 会尝试再运行该工作簿 2 次，每次间隔 15 分钟。3 次尝试均失败后，Report Builder 会停用该计划并显示“<span class="wintitle">重新激活</span>”按钮。重新激活工作簿时，计划提交从停用的时间重新开始。 </p> <p>例如，如果计划工作簿在 14 天之前停用，而您在今天将其重新激活，它将运行以弥补错过的每一天并且将提交 14 次。如果您不希望为错过的时间提交工作簿，可以删除计划工作簿，然后使用相同的计划参数创建新的计划工作簿。 </p> <p> <p>注意：除非您知道系统停用工作簿的原因，否则不应该将其重新激活。一种解决问题的方法是下载停用的工作簿，并在客户端刷新该工作簿。如果没有显示任何错误，则您应该可以将其重新激活。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上次发送 </p> </td> 
   <td colname="col2"> <p>报表上次发送的日期和时间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>收件人</b>选项卡 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收件人电子邮件 </p> </td> 
   <td colname="col2"> 报表的电子邮件收件人。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>报表 </p> </td> 
   <td colname="col2"> 发送到每个收件人的报表。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>报表历史记录</b>选项卡 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>文件名 </p> </td> 
   <td colname="col2"> 指示计划任务的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面 </p> </td> 
   <td colname="col2"> 报表上次发送的日期和时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>状态 </p> </td> 
   <td colname="col2"> 状态指示报表是已发送，还是未发送。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>电子邮件/FTP </p> </td> 
   <td colname="col2"> 报表收件人的电子邮件或 FTP 地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>文件格式 </p> </td> 
   <td colname="col2"> 报表的提交格式，如 Excel、PDF、HTML 等。 </td> 
  </tr> 
 </tbody> 
</table>
