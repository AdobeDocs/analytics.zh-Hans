---
description: 您可以在 Analysis Workspace 中根据上下文查看和分析数据异常。
title: 异常检测概述
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
feature: AI 工具
role: Business Practitioner, Administrator
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '288'
ht-degree: 100%

---

# 异常检测概述

您可以在 Analysis Workspace 中根据上下文查看和分析数据异常。

[异常检测视频教程](https://docs.adobe.com/content/help/zh-Hans/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html) (4:53)

[贡献分析视频教程](https://docs.adobe.com/content/help/zh-Hans/analytics-learn/tutorials/data-science/contribution-analysis-workspace.html) (3:20)

>[!IMPORTANT]
>
>异常检测已从 Reports &amp; Analytics 功能集中删除，现在只能通过 Analysis Workspace 使用。请注意，Adobe Analytics Select 和 Adobe Analytics Foundation 客户只能访问工作区中的“每日粒度”异常检测。有关更多信息，请参阅[异常检测和贡献分析授权](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md#section_9278D58F21A840AA9B1ED1BD07A1EF0A)。

“异常检测”提供了一种统计方法来确定给定的量度相对于以前的数据发生了什么变化。

通过异常检测，您可以将“真实形势”与“假象”区分开来，然后确定对这些形势或异常造成影响的潜在因素。换言之，该功能可让您确认哪些统计波动会造成影响，而哪些不会。然后您便可以确认真正异常的根本原因。此外，您可以获得可靠的量度 (KPI) 预测。

您可能会调查的异常情况包括：

* 平均订单值的显著降低
* 低收入订单的剧增
* 试用注册量剧增或骤降
* 登录页面查看次数骤降
* 视频缓冲事件剧增
* 低视频比特率剧增

异常检测和[贡献分析](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html)是 Analysis Workspace 中的核心工作流程。您可以针对任何每日异常运行“贡献分析”，并将结果嵌入到您的 Analysis Workspace 项目中。

Analysis Workspace 的异常检测算法包括

* 对每小时、每周和每月粒度以及现有的每天粒度的支持。
* 季节性（如“黑色星期五”）和假日的概念。
