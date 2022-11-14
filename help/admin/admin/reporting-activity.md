---
description: 了解如何使用报告活动管理器诊断和修复在报告高峰期出现的容量问题。
title: 报告活动管理器
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 21270e1a4f05208525261969c2e6858df8647aa1
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 92%

---

# 报告活动管理器

>[!NOTE]
>
>此功能当前处于测试阶段。

通过[!UICONTROL 报告活动管理器]，可查看组织中每个报告包的报告容量。 它让管理员详细了解报告消耗，并帮助您轻松地诊断和修复在报告高峰期出现的容量问题。

当您的组织达到报告请求容量并遇到报告性能下降的情况时，现在有办法可自行诊断报告问题，无需 Adobe 客户关怀或工程部门干预。在单个界面中即可轻松地管理报告队列，并可立即采取行动以改善您用户的体验。此工具：

* 实时通知您当前在各个报告包上的报告容量。
* 提供关于当前已排队或正在进行的报告请求的详细报告查询信息。
* 让您通过优先处理某些报告请求并取消其他报告请求以释放容量，从而优化报告队列。换句话说，您可以实时询问：此时是否需要这个报告，或者能否取消它以用于更紧急的报告？

## 访问报告活动管理器

在 Adobe Analytics 中，管理员转到&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报告活动管理器]**。

## 权限

您需要拥有Analytics产品管理员权限(位于Adobe Admin Console中)才能管理报表活动。

![许可](assets/rep-mgr-permission.png)

## 查看报告队列

在打开[!UICONTROL 报告活动]管理器概览页面时，您将看到已启用的基础报告包的列表。

![报告队列](assets/reporting-activity1.png)

| UI 元素 | 描述 |
| --- | --- |
| **[!UICONTROL 报告包]** | 基础报告包，您正在监控其报告活动。 |
| **[!UICONTROL 虚拟报告包]** | 显示馈送入此基础报告包的所有虚拟报告包。由于额外施加多层筛选和分段，因此虚拟报告包提高了报告请求的复杂性。所有来自虚拟报告包的请求合并归入基础报告包。<p>例如，如果您从 5 个 VRS 收到 10 个请求，则基础级别报告包中有 50 个请求。这样即可很快达到容量。 |
| **[!UICONTROL 使用容量]** | 百分比，实时使用了多少报告包的报告容量。 |
| **[!UICONTROL 状态]** | 四种可能的状态指示符： <ul><li>**红色 - [!UICONTROL 满负荷]**：报告包的报告容量已达到极限。(100%) </li><li>**黄色 - [!UICONTROL 接近容量]**：此报告包有达到其最大容量的危险。(90% - 99%)</li><li>**绿色 - [!UICONTROL 一切正常]**：有大量的报告容量。(0% - 89%)</li><li>**灰色 – [!UICONTROL 状态待定/未启用]**：报告容量不可用。</li></ul> |

{style=&quot;table-layout:auto&quot;}

### 其他报告活动操作

* 单击右上部的&#x200B;**[!UICONTROL 刷新]**&#x200B;可刷新结果。
* 单击报告包名称左侧的星号可收藏此报告包。
* 选中左上部的&#x200B;**[!UICONTROL 收藏夹]**&#x200B;可显示您的收藏夹。
* 在搜索栏中按名称或 ID 搜索报告包。
* 按状态筛选报告包。

## 查看各个报告包的报告活动

单击要查看其详细信息的报告包的标题链接。

![报告包](assets/indiv-report-ste.png)

### 折线图

折线图显示选定的报告包在过去 2 小时内的报告活动。

* X 轴显示过去 2 小时内的报告容量数据。
* Y 轴显示查询的平均等待时间（以秒为单位）。
* 您可以将鼠标悬停在折线图的上方来查看该时刻的时间点和平均等待时间。

   ![详细信息](assets/detail.png)

### 筛选

您可以按应用程序（见下表中的列表）、用户和项目筛选表。

![筛选](assets/filter.png)

### 摘要数字

![筛选](assets/summary_numbers.png)

摘要数字显示以下信息：

| 摘要数字 | 描述 |
| --- | --- |
| [!UICONTROL 用户] | 当前向此报表包发送报表请求的用户数。 |
| [!UICONTROL 项目] | Workspace 项目、Report Builder 工作簿等。 |
| [!UICONTROL 查询] | 当前正在运行的查询数。 |
| [!UICONTROL 平均等待时间] | 所有正在运行的查询的平均等待时间。 |
| [!UICONTROL 使用容量] | 此报告包的当前使用容量。 |

{style=&quot;table-layout:auto&quot;}

### 表格

下面的详情表显示有关报告包详情。

| 栏目 | 描述 |
| --- | --- |
| [!UICONTROL 查询 ID] | 可用于故障排除目的。 |
| [!UICONTROL 运行时间] | 查询运行了多长时间。 |
| [!UICONTROL 等待时间] | 查询在处理之前等待了多长时间。当有足够的容量时，一般为“0”。 |
| [!UICONTROL 开始时间] | 查询开始处理的时间（管理员的本地时间）。 |
| [!UICONTROL 应用程序] | [!UICONTROL 报告活动管理器]支持的应用程序包括： <ul><li>Analysis Workspace UI</li><li>工作区计划项目</li><li>Report Builder</li><li>生成器 UI：区段、计算量度、注释、受众等。</li><li>1.4 或 2.0 API 的 API 调用</li><li>智能警报</li></ul> |
| [!UICONTROL 用户] | 发起查询的用户。 |
| [!UICONTROL 项目] | 已保存的 Workspace 项目名称、API 报告 ID 等。（元数据可能因各种应用程序而异。） |
| [!UICONTROL 月边界] | 请求跨越的每月边界数。 这增加了请求的复杂性。 |
| [!UICONTROL 列] | Workspace 中用于衡量请求复杂性的量度和细分的数量。 |
| [!UICONTROL 区段] | 有多少段应用于此请求。这增加了请求的复杂性。 |
| [!UICONTROL 状态] | 状态指示器： <ul><li>**运行中**：请求当前正在处理中。</li><li>**等待中**：请求正在等待处理。</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 取消报告请求

要取消请求

1. 选中表格中一个或多个&#x200B;**[!UICONTROL 查询编号]**&#x200B;左侧的框，然后在底部单击&#x200B;**[!UICONTROL 取消请求]**。 

   您还可以通过查看 [!UICONTROL 用户], [!UICONTROL 项目]或 [!UICONTROL 应用程序]. 在活动刷新时，对于未处于队列或取消时正在运行的项目、用户或应用程序的后续请求仍可能显示。

1. 在出现的&#x200B;**[!UICONTROL 取消 x 查询]**&#x200B;窗口中，您可以根据需要修改取消消息。
1. 单击&#x200B;**[!UICONTROL 继续]**。

   ![cancel-query](assets/cancel-query.png)

例如，Workspace 中的应用程序用户会在他们的项目中看到以下通知：

![cancel-user-notice](assets/cancel-user-facing.png)

## 常见问题解答

| 问题 | 回答 |
| --- | --- |
| 我可以购买额外的报告容量吗？ | 此功能将在不久的将来提供。 |

{style=&quot;table-layout:auto&quot;}
