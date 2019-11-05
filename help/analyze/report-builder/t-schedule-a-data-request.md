---
description: 您可以安排报表按照定义的时间和文件格式发送。
seo-description: 您可以安排报表按照定义的时间和文件格式发送。
seo-title: 计划数据请求
solution: Analytics
title: 计划数据请求
topic: Report Builder
uuid: f6d8c90f-e185-4d60-8035-f20f74bfcd89
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# 计划工作簿

您可以计划工作簿、指定高级提交选项、指定收件人和查看计划历史记录。 高级交付选项允许您配置要在特定时间或间隔发送的工作簿。 您还可以指定发送工作簿的文件格式。

For example, you can schedule workbooks to be delivered immediately or on a recurring schedule, and specify the file format in [!DNL Advanced Delivery Options]. 上传工作簿的文件大小限制为5 MB。

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**. （请参阅 Reports &amp; Analytics 帮助中的[报表计划和分发](/help/analyze/reports-analytics/scheduling.md)。）

> [!NOTE] 要计划工作簿，必须安装Excel 2007或兼容性包。 每个Report builder许可证最多可有10个计划工作簿。 但是，您可以通过减少其他许可证中的数量来增加此数量。To do so, go to **[!UICONTROL Admin]** &gt; **[!UICONTROL Company Settings]** &gt; **[!UICONTROL Report Builder Reports]**. 将删除在超过28个月内已计划（或已上载到工作簿库）但未触及（更新、替换）的工作簿。

> [!NOTE] 用户输入的“交付时间”/“一天的时间”指定了工作簿开始处理的时间，而不是实际交付的时间。 实际传送工作簿的时间主要取决于处理时间（处理复杂和大型工作簿比处理较简单的工作簿耗时更长）。 例如，如果工作簿需要15分钟才能处理，则实际交付时间将至少比最初指定的“交付时间”/“每日时间”晚15分钟。
>此外，还有许多其他因素可能会进一步增加实际传送工作簿之前的延迟：
>
> * **同时运行多种不同的同类计划** ，可能会使系统过载。 计划系统仅允许少数(5-10)个任何类型的工作簿同时运行，因此，当同时计划的工作簿数量超过5-10时，有些工作簿需要排队等待完成，才能开始处理。 通过在一天或一小时中以交错的时间安排公司的工作簿，而不是同时安排，可以缓解此问题。
> * 除特定工作簿类型外，如果公司同时计划了超过15-20个任何类型的工作簿（跨所有不同的工作簿类型），则工作簿也将排队 ****。 这可以通过令人震惊的计划时间而不是同时进行多次运行来缓解。
> * **调度程序所依赖的下游服务** ，其中的问题也可能影响工作簿的交付。 例如，如果您单独使用API运行工作簿并填充API请求队列，则在您争夺该资源时，计划工作簿传送速度可能会很慢。
> * **报表包延迟** （数据收集的延迟）也可延迟某些计划工作簿。


## 计划工作簿

1. 生成并保存工作簿。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   “[!UICONTROL 计划报表]”选项卡总结您已创建的所有任务，以及剩余任务的数目。
1. On the **[!UICONTROL Scheduled Reports]** tab, click **[!UICONTROL New]**.
1. “基本计划向导”显示如下：

   ![](assets/simple-schedule-wizard.png)

1. 在“[!UICONTROL 基本计划向导]”中，配置以下选项：

| 字段 | 描述 |
|--- |--- |
| 选择报表 | 工作簿的名称。 对于新的计划报表，此字段使用活动工作簿的名称填充。 |
| 选择 | 显示“选择报表”页。您可以从服务器（先前计划的所有工作簿都存储在其中）选择报表，也可以从本地计算机选择报表。如果从本地驱动器选择 .xls 格式的工作簿，系统会将文件转换为 .xlsx。在转换过程中，系统会在 Excel 中打开并激活该文件。如果为计划报表选择的工作簿与当前在 Excel 中打开的工作簿具有相同的文件名，系统会选择本地文件，而不是先前上载的文件。如果从计划存储库中选择报告，则会在服务器上创建工作簿的副本，其文件名将更新为1。新创建的计划报告使用复制的工作簿。 |
| 通过更改日期范围、 | 允许您自定义日期格式。 |
| 收件人 | 显示 Outlook 通讯簿（如果适用）。 |
| 收件人: 电子邮件 | 工作簿的电子邮件收件人。 |
| 收件人: 发布列表 | 显示此公司的可用通讯组列表的列表。 |
| Power BI | 请参阅[将工作簿发布到 Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md)，以了解更多信息。 |
| 主题 | 用户定义的说明。 |
| 日程安排 | 允许您指定何时发送工作簿。 （立即、每小时、每天、每周、每月和每年。） |

## 高级提交选项

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

| 字段 | 描述 |
|--- |--- |
| **计划选项卡** |  |
| 提交时间 | 允许您立即计划工作簿或稍后计划工作簿。 时间是相对于在您计算机上指定的时区而言的。 |
| 循环模式 | 根据您的选择发送工作簿。 |
| 循环范围 | 允许您指定何时开始和停止接收工作簿。   注意： 在任何当前期间（周、月、季度或年）的第一天计划工作簿只返回第一天的数据。 |
| **文件选项选项卡** |  |
| 文件格式 | 允许您选择提交格式：Excel 2007 (.xlsx) 或 2003 (.xls)、.pdf、.csv、.mht、.txt 和 .xml。 |
| 文件目标 | 指定电子邮件或 FTP。页面上的选项会因您的选择而有所差异。对于 FTP，必须确保可从外部使用主机。 |
| 发布列表 | 如果将计划的工作簿发送到多个发布列表，则该工作簿为每个列表运行一次。 可变报表包由分配给发布列表的报表包替换。 |
| 文件内容语言 | 指定您希望附信使用的语言。您可以选择中文（简体或繁体）、德语、法语、日语、韩语、巴西葡萄牙语或西班牙语。 |
| **发布选项选项卡** |  |
| 发布到 Power BI | <ul><li>将工作簿发布到 Power BI</li><li>作为 Power BI 数据集表发布所有 Report Builder 请求</li><li>作为 Power BI 数据集表发布所有带格式的表</li></ul> |
| 将此 Power BI 报表标记为 | 标记详细信息 |

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   Report Builder displays the scheduled workbook in the [Scheduled Task Manager](/help/analyze/report-builder/r-arb-scheduled-reports.md).

