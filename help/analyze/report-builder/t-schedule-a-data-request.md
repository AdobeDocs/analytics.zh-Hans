---
description: 您可以安排报表按照定义的时间和文件格式发送。
seo-description: 您可以安排报表按照定义的时间和文件格式发送。
seo-title: 计划数据请求
solution: Analytics
title: 计划数据请求
topic: Report Builder
uuid: f6d8c90f-e185-4d60-8035-f20 f74 bfcd89
translation-type: tm+mt
source-git-commit: ed8cfa41a2495c884f1096ea54624820bf3a9e07

---


# 计划工作簿

您可以计划工作簿、指定高级交付选项、指定收件人以及查看计划历史记录。高级交付选项可让您配置要在特定时间或间隔发送的工作簿。您还可以指定发送工作簿的文件格式。

For example, you can schedule workbooks to be delivered immediately or on a recurring schedule, and specify the file format in [!DNL Advanced Delivery Options]. 上传工作簿时，文件大小限制为MB。

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**. （请参阅 Reports &amp; Analytics 帮助中的[报表计划和分发](/help/analyze/reports-analytics/scheduling.md)。）

>[!NOTE]
>
>必须安装Excel2007或兼容性包才能预定工作簿。每个Report Builder许可证最多可有10个计划的工作簿。但是，您可以通过减少其他许可证中的数量来增加此数量。To do so, go to **[!UICONTROL Admin]** &gt; **[!UICONTROL Company Settings]** &gt; **[!UICONTROL Report Builder Reports]**. 已计划(或上传到工作簿库)且尚未在28个月内被触控(已更新、替换)的工作簿将被删除。

>[!NOTE]
>
>用户输入的“交付时间”/“每日时间”指定工作簿应开始处理的时间，而不是实际交付的时间。将提供工作簿的实际时间主要基于处理多长时间(复杂和大型工作簿需要比简单工作簿更长的处理时间)。例如，如果一个工作簿需要15分钟处理，则实际交付时间至少将超过最初指定的“交付时间”/“每日时间”。
>此外，还有许多其他因素可进一步提高工作簿实际交付之前的延迟：
>
> * **同时运行同一类型的很多不同时间表会** 使系统过载。计划系统只允许任何一种类型的(5-10)工作簿同时运行，因此，当超过5-10的工作簿同时预定时，有些工作簿需要在开始处理之前等待其他工作簿排队完成。可通过在一天或一小时内(而不是同时)随机安排公司的工作簿来减轻此问题。
> * 除了特定的工作簿类型之外，如果公司拥有 **一次计划的任何类型的工作簿(跨所有不同的工作簿类型**)，那么工作簿还可以排队等候。这可以通过实例化计划时间来减轻，而不是让很多人同时运行。
> * **调度程序所依赖的下游服务** 中的问题也可能影响工作簿的交付。例如，如果您使用API独立运行工作簿并填写API请求队列，那么您的预定工作簿可能会在您竞争该资源时缓慢交付。
> * **报表包滞后时间** (数据收集的延迟)还可以延迟某些预定的工作簿。


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
| 选择报表 | 工作簿的名称。对于新的计划报表，此字段使用活动工作簿的名称填充。 |
| 选择 | 显示“选择报表”页。您可以从服务器（先前计划的所有工作簿都存储在其中）选择报表，也可以从本地计算机选择报表。如果从本地驱动器选择 .xls 格式的工作簿，系统会将文件转换为 .xlsx。在转换过程中，系统会在 Excel 中打开并激活该文件。如果为计划报表选择的工作簿与当前在 Excel 中打开的工作簿具有相同的文件名，系统会选择本地文件，而不是先前上载的文件。如果从日程安排存储库中选择一个报表，则在服务器上创建一个工作簿副本，其文件名将更新为1。新创建的计划报告使用复制的工作簿。 |
| 通过更改日期范围、 | 允许您自定义日期格式。 |
| 收件人 | 显示 Outlook 通讯簿（如果适用）。 |
| 收件人: 电子邮件 | 工作簿的电子邮件收件人。 |
| 收件人: 发布列表 | 显示此公司的可用通讯组列表的列表。 |
| Power BI | 请参阅[将工作簿发布到 Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md)，以了解更多信息。 |
| 主题 | 用户定义的说明。 |
| 日程安排 | 允许您指定何时发送工作簿。（立即、每小时、每天、每周、每月和每年。） |

## 高级提交选项

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

| 字段 | 描述 |
|--- |--- |
| **计划选项卡** |  |
| 提交时间 | 允许您立即预定工作簿或稍后安排工作簿。时间是相对于在您计算机上指定的时区而言的。 |
| 循环模式 | 根据您的选择发送工作簿。 |
| 循环范围 | 允许您指定何时开始并停止接收工作簿。注意：在任何当前时间段(周、月、季度或年)的第一天计划工作簿只会返回第一天的数据。 |
| **文件选项选项卡** |  |
| 文件格式 | 允许您选择提交格式：Excel 2007 (.xlsx) 或 2003 (.xls)、.pdf、.csv、.mht、.txt 和 .xml。 |
| 文件目标 | 指定电子邮件或 FTP。页面上的选项会因您的选择而有所差异。对于 FTP，必须确保可从外部使用主机。 |
| 发布列表 | 如果将计划工作簿发送到多个发布列表，则工作簿为每个列表运行一次。可变报表包由分配给发布列表的报表包替换。 |
| 文件内容语言 | 指定您希望附信使用的语言。您可以选择中文（简体或繁体）、德语、法语、日语、韩语、巴西葡萄牙语或西班牙语。 |
| **发布选项选项卡** |  |
| 发布到 Power BI | <ul><li>将工作簿发布到 Power BI</li><li>作为 Power BI 数据集表发布所有 Report Builder 请求</li><li>作为 Power BI 数据集表发布所有带格式的表</li></ul> |
| 将此 Power BI 报表标记为 | 标记详细信息 |

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   Report Builder displays the scheduled workbook in the [Scheduled Task Manager](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31).

