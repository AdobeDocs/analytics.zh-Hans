---
description: 了解如何将Mobile Services处理规则迁移到Adobe Analytics
title: 将Mobile Services处理规则迁移到Adobe Analytics
translation-type: tm+mt
source-git-commit: d6601640d06f65dd1ddd09cb9bde0267df20eec3
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 6%

---


# 将Mobile Services处理规则迁移到Adobe Analytics

本文档向您提供有关如何将您在Mobile Services UI中创建的任何其他处理规则（超出生命周期指标）迁移到Adobe Analytics的说明。

处理规则用于将上下文数据变量的值迁移到 prop 和 eVar。例如，您可以将“search-term”上下文eVar变量的值放入商务变量的值中，并在每次点击时覆盖该值。 如果没有处理规则，上下文数据变量将毫无意义，并且不会在 Analytics 中填充任何报表。

此文档还向您展示如何在Analysis Workspace进行移动使用报告。

## 迁移处理规则

如果您正在利用Mobile Services获得免费功能(如处理规则和使用报告功能)，则可以无缝移至Analytics UI(处理规则UI或Analysis Workspace)来完成这些功能。 对于在AA处理规则UI中设置的生命周期指标或规则，您无需执行任何迁移。 生命周期指标是“现成”指标，在您的应用程序中首次实施Mobile SDK时自动收集。

但是，如果您在Mobile Services UI（超出生命周期指标）中设置任何其他处理规则，则应迁移这些规则，以便您在失去Mobile Services访问权限后在Analytics中编辑／删除它们。

1. Log in to `experience.adobe.com` and go to Mobile Services.
1. 单击要迁移到Adobe Analytics的上下文变量映射的移动应用程序的齿轮图标。
1. 单击“管 **[!UICONTROL 理变量和度量]** ”菜单项，然后单击“自 **[!UICONTROL 定义变量]** ”选项卡。 在此，您可以看到哪些上下文变量映射（上下文数据）已添加到配置中。 记下这些配置（或拍下屏幕截图）。 示例：

   ![上下文变量](assets/context-var.png)

1. 在Experience Cloud中，切换到Adobe Analytics并确保您位于Mobile Services中查看的同一移动报告套件中。
1. 转至“管 **[!UICONTROL 理员]** ”>“ **[!UICONTROL 报表包]** ”>“ **[!UICONTROL 编辑设置]** ”>“ **[!UICONTROL 常规”]******>“处理规则”。
1. 单击 **[!UICONTROL Add Rule]**.
1. 忽略这些条件并继续添加Mobile Services中存在的相同上下文变量。

   ![处理规则](assets/proc-rule.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。

## Analysis Workspace的移动使用报告

除了移动指标和维度（如果为Mobile Services启用了报表包）之外，Analysis Workspace还包含若干可促进分析的移动项目模板：

* **[!UICONTROL 消息]**:专注于应用内和推送消息性能。
* **[!UICONTROL 位置]**:包括展示位置数据的地图。
* **[!UICONTROL 关键指标]**:掌握应用程序的关键指标。
* **[!UICONTROL 应用程序使用]**:应用程序有多少个应用程序用户、启动项和首次启动项，平均会话长度是多少？
* **[!UICONTROL 客户赢取]**:移动客户获取链接的性能如何？
* **[!UICONTROL 性能]**:应用程序的性能如何，用户在哪里遇到问题？
* **[!UICONTROL 保留]**:我的忠实用户是谁，他们做什么？
* **[!UICONTROL 旅程]**:我的应用程序的主要使用模式是什么？

以下是“移动应用程序使用情况”模板的摘录：

![移动应用程序使用](assets/mobile-app-usage.png)

要访问模板，请执行以下操作：

1. Log in to `experience.adobe.com` and select Analytics.
1. 确保您位于为Mobile Services启用的报表包中。
1. Click the **[!UICONTROL Workspace]** tab.
1. 单击&#x200B;**[!UICONTROL 新建项目]**。
1. 选择任何移动模板，然后单击“ **[!UICONTROL 创建]**”。

## 迁移其他Mobile Services功能

以下Mobile Services功能也与Adobe Analytics相关，但需要购买的Adobe AnalyticsSKU:

* “客户获取链接”
* 推送消息
* 应用程序内消息传送
* 位置目标点管理

如果您正在利用Mobile Services实现付费功能，则没有可行的迁移途径可迁移到其他内部／外部工具：

* 对于客户获取链接，我们可以将您定向到Adobe合作伙伴，以满足您的需求。
* 推送消息和应用程序内消息在Adobe Campaign Standard和Adobe Campaign Classic（仅限推送）提供。 但是，用于定位的基础数据集不同。 我们建议与您的Adobe客户团队合作，确定消息数据的迁移选项。
* 对于位置功能，建议您采用全新的 [Adobe Experience Platform位置服务](https://www.adobe.com/experience-platform/location-service.html)，该服务对所有AEP客户都是免费的。
