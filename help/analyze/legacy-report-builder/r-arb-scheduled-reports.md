---
description: 了解“计划任务管理器”的字段说明。
title: 关于计划任务管理器
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 91%

---

# 计划任务管理器

{{legacy-arb}}

[!UICONTROL 计划任务管理器]允许您查看现有计划报告的列表，以及其收件人、计划详细信息和文件格式。它还允许您重新激活运行失败的计划工作簿。

## 暂停旧版计划任务

2022 年 4 月 21 日，作为性能和交付优化工作的一部分，我们在 Report Builder 中推出了对计划任务的更改。这些更改包括取消预定交付“在发生 x 次后结束”的功能。为了响应一些客户要求更多时间来探索和实施替代方案的请求，我们决定在 **2023 年 1 月 31 日**&#x200B;之前有限地恢复此选项。

您将继续能够计划每小时 Report Builder 任务，并在最多发生 99 次后结束这些任务。 请注意，回滚仅适用于小时任务；对于所有其他交付间隔期（每天、每周、每月和每年），“在发生x次后结束”不可用。

请注意，此选项已于2023年1月31日停用。
如果还有更多问题或需要获取相关支持，请联系 Adobe 客户关怀团队。

具体而言，这一暂停适用于 **2020 年 1 月 31 日之前创建的任何任务**。任何任务、工作簿或数据都不会被删除。超过两年的任务将暂停，并且不会发送其他计划任务。

您希望继续发送的任何任务都可以重新激活。登录 Report Builder，启动[!UICONTROL 计划任务管理器]。若您想继续发送任何计划任务，请点击&#x200B;**[!UICONTROL 重新激活]**。任何重新激活的任务都将拥有 18 个月默认到期日期，除非选择更短的到期日期。

此外，任何创建日期少于两年且无当前到期日期（或到期日期超过两年）的任务将有 18 个月的默认到期日期。新的到期日期为 2023 年 10 月 15 日。您可以将此到期日期编辑为小于 18 个月，但不能大于 18 个月。到期时，任务将暂停。但是，您可以在新的 18 个月到期日期内重新激活任务。任何任务、工作簿或数据都不会被删除。

暂停的目的是有效地管理和维护我们的计划任务数据库，确保所需任务和工作簿的最佳性能和交付。这将成为我们今后的新治理政策。2023年1月31日之后，所有任务的最长有效期为18个月。 18 个月后，到期的任务将暂停，并可根据需要重新激活。

## 配置计划任务

| 字段 | 描述 |
| --- | --- |
| **[!UICONTROL 计划报告选项卡]** | |
| [!UICONTROL 报告名称] | 指示计划任务的名称。 |
| [!UICONTROL 电子邮件/FTP] | 收件人的电子邮件或 FTP 地址。**注意：**&#x200B;如果选择了电子邮件，那么大于 1MB 的报表将自动作为 .zip 文件添加到邮件附件中。此功能有助于保持较小的附件文件大小，您无法禁用该功能。 |
| [!UICONTROL 发布选项] | 如果选择了 [Power BI 发布选项](https://experienceleague.adobe.com/docs/analytics/analyze/legacy-report-builder/publish-powerbi/power-bi.html)之一，本栏将列出 Power BI。 |
| [!UICONTROL 计划] | 计划的提交类型。 |
| [!UICONTROL 文件格式] | 报告的提交格式，如 Excel、PDF、HTML 等。 |
| [!UICONTROL 重新激活] | 计划工作簿无法运行时，Report Builder 会尝试再运行该工作簿 2 次，每次间隔 15 分钟。3 次尝试均失败后，Report Builder 会停用该计划并显示“重新激活”按钮。重新激活工作簿时，计划提交从停用的时间重新开始。<p>例如，如果计划工作簿在 14 天之前停用，而您在今天将其重新激活，它将运行以弥补错过的每一天并且将提交 14 次。如果您不希望为错过的时间提交工作簿，可以删除计划工作簿，然后使用相同的计划参数创建新的计划工作簿。<p>**请注意：**&#x200B;除非您知道系统停用工作簿的原因，否则不要重新激活工作簿。要进行故障诊断，请下载已停用的工作簿并在客户端刷新。如果没有显示任何错误，则您应该可以将其重新激活。 |
| [!UICONTROL 上次发送] | 报告上次发送的日期和时间。 |
| **收件人选项卡** | |
| [!UICONTROL 收件人电子邮件] | 报告的电子邮件收件人。 |
| [!UICONTROL 报告] | 发送给每个收件人的报告。 |
| **报告历史记录选项卡** | |
| [!UICONTROL 文件名] | 指示计划任务的名称。 |
| [!UICONTROL 日期] | 报告上次发送的日期和时间。 |
| [!UICONTROL 状态] | 状态指示报告是已发送，还是未发送。 |
| [!UICONTROL 电子邮件/FTP] | 报告收件人的电子邮件或 FTP 地址。 |
| [!UICONTROL 文件格式] | 报告的提交格式，如 Excel、PDF、HTML 等。 |