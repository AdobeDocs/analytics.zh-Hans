---
description: 了解 Analysis Workspace 中的错误及其排查方法。
title: 错误和故障排除
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: e09234ca27fbf923e026aa1f2ed0ebfed636bf7c
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 100%

---

# 错误和故障排除

当您与 Analysis Workspace 交互时，可能会遇到影响其功能或性能的错误。下面列出了最常见的错误类型、发生原因以及优化方案。

## 错误消息

使用 Analysis Workspace 时可能会看到的一些常见错误消息：

| 错误消息 | 为什么会出现这个错误？ | 优化 |
| --- | --- | --- |
| [!UICONTROL 数据视图正在经历异常繁重的报告。请稍后重试。] | 您的组织针对特定数据查看尝试运行的并发请求过多。导致此错误的因素包括：API 请求、计划项目、计划报告、计划警报，以及提出报告请求的并发用户数量。 | 将数据查看的请求和计划较为均匀地分布在一天当中。<p>管理员可以使用 [报告活动管理器来识别和取消](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md) 正在消耗报告容量的请求。</p> |
| [!UICONTROL 这份报告太复杂了。请查看构建 Analysis Workspace 报告的最佳实践。] | 您的报告请求过大，无法执行。造成此错误的原因是由于请求的复杂性而导致的超时。 | 简化您的请求。例如，缩短日期范围，或简化分段条件，或移除表格中的某些列或行。您也可以考虑将表拆分为单独的请求。 |
| [!UICONTROL 数据视图目前已超出其报告容量。请简化请求或稍后重试。] | 您的组织针对特定数据查看尝试运行的并发请求过多。导致此错误的因素包括：API 请求、计划项目，以及提出报告请求的并发用户数量。 | 将数据查看的请求和计划较为均匀地分布在一天当中。 |
| [!UICONTROL 发生系统错误。请在&#x200B;**[!UICONTROL 帮助 > 提交支持票证]**&#x200B;下记录一条客户关怀团队请求，并将您的错误代码包含在内。] | Adobe 遇到了一个需要解决的问题。 | 将错误代码提交给客户关怀团队。 |
| [!UICONTROL 错误 500：无法加载页面] | 本地网络的问题（如公司[防火墙设置](/help/technotes/ip-addresses.md)），是引发该错误的一个因素。此外，Adobe 可能遇到了需要解决的问题。 | 请在几分钟后再次尝试登录。如果问题仍然存在，请向客户关怀团队提交 EIM 实例 ID 代码。 |
| [!UICONTROL 由于列或预配置行过多，导致请求失败。] | 表格中自由格式单元格（行数乘以列数）过多。 | 移除表格中的列或行，或考虑将表格拆分为单独的请求。 |


## 故障排除

使用 Analysis Workspace 时，您可以使用以下信息来解决一些常见问题。

| 问题 | 如何排除故障 |
|---|---|
| 当我拖动一个量度时，它会显示&#x200B;*无效数据*。 | 无效数据意味着 Adobe 无法通过报告中使用的维度和量度组合返回数据。例如，两个彼此堆叠的量度不能作为数据返回，因为无法以这种堆叠方式显示这两个量度。相反，应将两个量度并排放置。 |
| 当我将量度拖动到上面时，看不到任何实际数据 - 只有零。 | 如果您成功创建了 Workspace 报告，但报告中没有数据，则可以检查以下几项内容：<ul><li>如果在报告中应用了区段，区段标准可能与所有数据不匹配。请尝试移除区段或调整区段定义。</li><li>检查右上角的日期范围，并确保它已设置为预期的值。</li><li>导航到您的网站，然后使用 [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hans) 验证正在收集的数据。</li></ul> |



<!--
# Common error messages

You may encounter errors when interacting with Analysis Workspace that will also influence performance. Listed below are the most common error types, why they occur, and optimizations that can be made.

| Error message | Why does this occur? | Optimization |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. <p>Administrators can use the [Reporting Activity Manager to identify and cancel requests](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md) that are consuming reporting capacity. |
| [!UICONTROL The report suite is currently exceeding its reporting capacity. Please simplify the request or try again later.] |  Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, scheduled reports, scheduled alerts, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe is experiencing an issue that needs to be resolved. | Submit the error code to Customer Care. |
| [!UICONTROL An unexpected error has occurred; try refreshing your project again. If the problem persists, please submit this error ID to Adobe Customer Care for further diagnosis.] | Adobe is experiencing an issue that needs to be resolved. | Try refreshing your project and if the problem persists, submit the error code to Customer Care. |
| [!UICONTROL Error 500: Failed to load page] | Issues with your local network, such as company [firewall settings](/help/technotes/ip-addresses.md), are a contributing factor to this error. Additionally, Adobe may be experiencing an issue that needs to be resolved. | Try logging in again after several minutes. If the issue persists, submit the EIM instance ID code to Customer Care. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Your segment criteria or report filter is too broad. | Narrow your search text criteria and try the request again. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | Non-default attribution is not supported for the dimension that you are using. | Replace the dimension in your table with one that is compatible with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Your table has too many freeform cells (row * columns). | Remove columns or rows in your table, or consider splitting the table into separate requests. |
-->