---
description: Adobe Analysis Workspace 及其相关组件中的错误消息列表
title: Analysis Workspace 中的常见错误消息
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: e7e03531454bd56ebe6152edc08765f42ebec728
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 100%

---

# 常见错误消息

当您与 Analysis Workspace 交互时，可能会遇到错误，这也会影响性能。下面列出了最常见的错误类型、发生原因以及优化方案。

| 错误消息 | 为什么出现此错误？ | 优化 |
| --- | --- | --- |
| [!UICONTROL 报告包遇到异常繁重的活动。请稍后重试。] | 您的组织针对特定报告包尝试运行的并发请求过多。导致此错误的因素包括：API 请求、计划项目，以及提出报告请求的并发用户数量。 | 将报告包的请求和计划较为均匀地分布在一天当中。 <p>管理员可以使用 [报告活动管理器来识别和取消](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) 正在消耗报告容量的请求。 |
| [!UICONTROL 该报告套件目前已超出其报告容量。请简化请求或稍后重试。] | 您的组织针对特定报告包尝试运行的并发请求过多。导致此错误的因素包括：API 请求、计划项目、计划报告、计划警报，以及提出报告请求的并发用户数量。 | 将报告包的请求和计划较为均匀地分布在一天当中。 |
| [!UICONTROL 发生系统错误。请在“帮助”>“提交支持服务单”下记录一条客户关怀团队请求，并将错误代码包含在内。] | Adobe 遇到了一个需要解决的问题。 | 将错误代码提交给客户关怀团队。 |
| [!UICONTROL 发生意外错误；请尝试再次刷新项目。如果问题仍然存在，请将此错误 ID 提交给 Adobe 客户关怀团队，以便进一步诊断。] | Adobe 遇到了一个需要解决的问题。 | 请尝试刷新项目，如果问题仍然存在，请将错误代码提交给客户关怀团队。 |
| [!UICONTROL 错误 500：无法加载页面] | 本地网络的问题（如公司[防火墙设置](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=zh-Hans)），是引发该错误的一个因素。此外，Adobe 可能遇到了需要解决的问题。 | 请在几分钟后再次尝试登录。如果问题仍然存在，请向客户关怀团队提交 EIM 实例 ID 代码。 |
| [!UICONTROL 此可视化图表中的一个区段或搜索，包含返回了大量结果的文本搜索。] | 您设定的区段标准或报告过滤器过于宽泛。 | 应缩小搜索文本标准，然后重试请求。 |
| [!UICONTROL 此维度当前不支持非默认归因模型。] | 您使用的维度不支持非默认归因。 | 将表中的维度替换为与[归因](/help/analyze/analysis-workspace/attribution/overview.md)兼容的维度。 |
| [!UICONTROL 由于列或预配置行过多，导致请求失败。] | 表格中自由格式单元格（行数乘以列数）过多。 | 移除表格中的列或行，或考虑将表格拆分为单独的请求。 |
