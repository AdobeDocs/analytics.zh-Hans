---
description: 您可以安排报表按照定义的时间和文件格式发送。
title: 计划数据请求
topic: Report builder
uuid: f6d8c90f-e185-4d60-8035-f20f74bfcd89
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 计划工作簿

您可以计划工作簿、指定高级提交选项、指定收件人和查看计划历史记录。高级提交选项允许您配置要在特定时间发送或定期发送的工作簿。您还可以指定发送工作簿时要使用的文件格式。

例如，您可以安排工作簿立即提交或者按定期计划提交，还可以指定 [!DNL Advanced Delivery Options] 中的文件格式。上载工作簿时，文件大小不能超过 5 MB。

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**. （请参阅 Reports &amp; Analytics 帮助中的[报表计划和分发](/help/analyze/reports-analytics/scheduling.md)。）

>[!NOTE]您必须安装 Excel 2007 或兼容包才能计划工作簿。对于每个 Report Builder 许可证，您最多可以有 10 个计划工作簿。但是，您可以通过减少其他许可证中的数量来增加此数量。要执行此操作，请转至 **[!UICONTROL Admin]** > **[!UICONTROL Company Settings]** > **[!UICONTROL Report Builder Reports]**。 已计划（或已上载到工作簿库）的工作簿以及超过 28 个月未使用（更新、替换）的工作簿将被删除。

>[!NOTE]用户输入的“提交时间”/“时间”指定了应开始处理工作簿的时间，而不是实际提交工作簿的时间。提交工作簿的实际时间主要取决于处理时间（处理复杂和大型工作簿比处理简单的工作簿耗时更长）。例如，如果需要 15 分钟才能处理工作簿，则实际提交时间将至少比最初指定的“提交时间”/“时间”晚 15 分钟。
>此外，在实际提交工作簿之前，还有许多其他因素可能会进一步增加延迟时间：
>
> * **同时运行同一类型的多个计划**&#x200B;可能会造成系统过载。计划系统仅允许同时运行少数几 (5-10) 个任一类型的工作簿，因此，当同时计划运行的工作簿数量超过 5-10 个时，有些工作簿需要排队等待其他工作簿完成后才能开始处理。通过错开安排一天或一小时中处理公司的工作簿的时间，而不是同时安排，可以缓解此问题。
> * 除特定工作簿类型外，如果公司&#x200B;**同时计划了超过 15-20 个任意类型的工作簿（跨所有不同的工作簿类型）**，则工作簿也将需要排队等候处理。可以通过错开计划时间运行而不是在同一时间运行来缓解这种情况。
> * 计划程序所依赖的&#x200B;**下游服务中的问题**&#x200B;也会影响工作簿的提交。例如，如果您单独使用 API 运行工作簿并填充 API 请求队列，则在您争夺该资源时，计划工作簿提交速度可能会较慢。
> * **报表包延迟**（数据收集的延迟）也会导致某些计划工作簿提交延迟。


## 计划工作簿

1. 生成并保存工作簿。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   The [!UICONTROL Scheduled Reports] tab summarizes all the tasks you have created, as well as the number of remaining tasks.
1. 在选项卡 **[!UICONTROL Scheduled Reports]** 上，单击 **[!UICONTROL New]**。
1. “基本计划向导”显示如下：

   ![](assets/simple-schedule-wizard.png)

1. 在中， [!UICONTROL Basic Scheduling Wizard]配置以下选项：

| 字段 | 描述 |
|--- |--- |
| 选择报表 | 工作簿的名称。对于新的计划报表，此字段使用活动工作簿的名称填充。 |
| 选择 | 显示“选择报表”页。您可以从服务器（先前计划的所有工作簿都存储在其中）选择报表，也可以从本地计算机选择报表。如果从本地驱动器选择 .xls 格式的工作簿，系统会将文件转换为 .xlsx。在转换过程中，系统会在 Excel 中打开并激活该文件。如果为计划报表选择的工作簿与当前在 Excel 中打开的工作簿具有相同的文件名，系统会选择本地文件，而不是先前上载的文件。如果从计划存储库中选择报表，则会在服务器上创建工作簿的副本并在副本文件名中附加 1。新创建的计划报表使用复制的工作簿。 |
| 自定义 | 允许您自定义日期格式。 |
| 至 | 显示 Outlook 通讯簿（如果适用）。 |
| 收件人: 电子邮件 | 工作簿的电子邮件收件人。 |
| 收件人: 发布列表 | 显示此公司的可用通讯组列表的列表。 |
| Power BI | 请参阅[将工作簿发布到 Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md)，以了解更多信息。 |
| 主题 | 用户定义的说明。 |
| 日程安排 | 允许您指定发送工作簿的时间。（立即、每小时、每天、每周、每月和每年。） |

## 高级提交选项

1. 单击 **[!UICONTROL Advanced Delivery Options]** 以配置文件和发布选项：

| 字段 | 描述 |
|--- |--- |
| **计划选项卡** |  |
| 提交时间 | 允许您安排工作簿立即发送或稍后发送。时间是相对于在您计算机上指定的时区而言的。 |
| 循环模式 | 基于您的选择发送工作簿。 |
| 循环范围 | 允许您指定何时开始和停止接收工作簿。注意：如果安排工作簿在任何当前时段（周、月、季度或年）的第一天发送，则仅返回第一天的数据。 |
| **文件选项选项卡** |  |
| 文件格式 | 允许您选择提交格式：Excel 2007 (.xlsx) 或 2003 (.xls)、.pdf、.csv、.mht、.txt 和 .xml。 |
| 文件目标 | 指定电子邮件或 FTP。页面上的选项会因您的选择而有所差异。对于 FTP，必须确保可从外部使用主机。 |
| 发布列表 | 如果将计划工作簿发送给多个发布列表，则工作簿针对每个列表运行一次。可变报表包由分配给发布列表的报表包替换。 |
| 文件内容语言 | 指定您希望附信使用的语言。您可以选择中文（简体或繁体）、德语、法语、日语、韩语、巴西葡萄牙语或西班牙语。 |
| **发布选项选项卡** |  |
| 发布到 Power BI | <ul><li>将工作簿发布到 Power BI</li><li>作为 Power BI 数据集表发布所有 Report Builder 请求</li><li>作为 Power BI 数据集表发布所有带格式的表</li></ul> |
| 将此 Power BI 报表标记为 | 标记详细信息 |

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   Report Builder 在[计划任务管理器](/help/analyze/report-builder/r-arb-scheduled-reports.md)中显示计划工作簿。

