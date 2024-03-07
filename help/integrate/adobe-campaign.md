---
description: 了解如何在 Adobe Analytics 中启用 Adobe Campaign Standard 报告
title: 如何将 Adobe Campaign Standard 报告集成到 Adobe Analytics 中？
feature: Campaign Integration
exl-id: 63bae5ee-f94d-43fa-87ce-6380236745d6
role: Admin
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 99%

---


# Adobe Campaign Standard 报告

有关如何配置此集成的更多信息，请参阅 [Adobe Campaign 文档](https://helpx.adobe.com/cn/campaign/standard/integrating/using/about-campaign-analytics-integration.html)。

>[!IMPORTANT]
>本文仅适用于 Adobe Campaign **Standard** 报告。有关添加 Adobe Campaign **Classic** 报告，请参阅[此处](https://experienceleague.adobe.com/docs/analytics/integration/analytics-to-campaign-classic.html)。

Adobe Analytics 与 Adobe Campaign Standard 之间的此集成：

* 允许您将 KPI（关键绩效指标）数据从 Adobe Campaign Standard 共享到 Adobe Analytics。
* 通过 Adobe Analytics 参数丰富了跟踪公式。
* 在 **[!UICONTROL Analytics]** > **[!UICONTROL 报表]** > **[!UICONTROL Adobe Campaign]** 下添加了新报表。
* 添加了 5 个新的 Adobe Campaign 分类。
* 添加了 9 个新的 Adobe Campaign 量度。
* 添加了 6 个新的 Adobe Campaign 维度。
* 通过自动配置的数据源每 15 分钟将数据同步到 Analytics 一次。

## 步骤 1. 启用 Adobe Campaign Standard 报告 {#section_C685EF10505045708A6536BB13F6CD58}

为了在 Analytics 中查看 Campaign Standard 数据，首先必须在报告包管理器中启用 Campaign 报告。

1. 导航至 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **`<select report suite>`** > **[!UICONTROL 编辑设置]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Adobe Campaign 报告]**。
1. 单击&#x200B;**[!UICONTROL 启用 Campaign 报表]**。

   ![](assets/enable-campaign.png)

## 步骤 2. 查看 Adobe Campaign 报表 {#section_9C18A29F3CC54BD4AC5EA96417F17B33}

Adobe Campaign Standard 与 Adobe Analytics 之间的集成在 **[!UICONTROL Analytics]** > **[!UICONTROL 报告]**&#x200B;下添加了以下报告

* **[!UICONTROL Adobe Campaign 执行的投放 ID]**：显示从 Adobe Campaign 导入的有关从 Adobe Campaign 发送的电子邮件的数据。

## 步骤 3. 使用 Adobe Campaign 分类 {#section_74A28AF3F4CA4091943789DE4D8B2B63}

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **`<select report suite>`** > **[!UICONTROL 编辑设置]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Adobe Campaign 分类]**

为报告包启用 Adobe Campaign 后，即有以下分类可用：

| 分类 | 描述 |
| --- | --- |
| [!UICONTROL 投放 ID] | 您在营销活动中看到的内部投放名称 |
| [!UICONTROL 投放标签] | 营销活动中的投放 — 个别投放/定期投放/交易投放 |
| [!UICONTROL 营销活动 ID] | 您在营销活动中看到的内部营销活动名称 |
| [!UICONTROL 营销活动标签] | Adobe Campaign 中的营销活动 |
| [!UICONTROL 执行的投放标签] | 个别执行的投放的列表 |

## Adobe Analytics 中可用的 Adobe Campaign Standard 维度和量度 {#section_F33385C9660644AF84172EC39601469B}

在 Adobe Analytics 报表包的 Campaign 中可以使用以下&#x200B;**指标**：

* Adobe Campaign 已发送
* Adobe Campaign 已打开
* Adobe Campaign 已点击
* Adobe Campaign 已提交
* Adobe Campaign 唯一打开
* Adobe Campaign 唯一点击
* Adobe Campaign 已取消订阅
* Adobe Campaign 总跳出次数
* Adobe Campaign 执行的投放 ID 实例

在 Adobe Analytics 报表包的 Campaign 中可以使用以下&#x200B;**维度**：

| 维度名称 | 定义 |
| --- | --- |
| 营销活动 ID | 在活动持续期间为其发送了 KPI 的所有促销活动的 ID |
| 营销活动标签 | 营销活动 ID 的标签 |
| 投放 ID | 在活动持续期间为其发送了 KPI 的所有提交的 ID。还包含循环提交和交易提交的主提交的 ID。示例：循环提交 DM1 是计划的提交，DM2、DM3、DM4 和 DM5 是该循环提交的子提交。投放 ID 将显示从 DM1 到 DM5 的所有提交的结果。 |
| 投放标签 | 投放 ID 的标签 |
| 执行的投放 ID | 仅执行的提交的 ID。不包含循环/交易主提交的 ID。示例：循环提交 DM1 是计划的提交，DM2、DM3、DM4 和 DM5 是该循环提交的子提交。执行的投放 ID 显示从 DM2 到 DM5 的所有提交（即已实际执行的提交）的结果。 |
| 执行的投放标签 | 执行的投放 ID 的标签 |
