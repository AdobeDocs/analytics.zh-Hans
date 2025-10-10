---
description: 了解如何将 Mobile Services 处理规则迁移到 Adobe Analytics
title: 将 Mobile Services 处理规则迁移到 Adobe Analytics
feature: Processing Rules
exl-id: ea183c1a-a85e-4f4e-a7f6-f947b939e9d9
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 88%

---

# 将 Mobile Services 处理规则迁移到 Adobe Analytics

此文档向您介绍如何将在 Mobile Services UI 中创建的附加处理规则（在生命周期量度之外）迁移到 Adobe Analytics。

处理规则用于将上下文数据变量的值迁移到 prop 和 eVar。例如，您可以将“search-term”上下文数据变量的指放在商务变量 eVar 的值中，并在每次点击时覆盖该值。如果没有处理规则，上下文数据变量将毫无意义，并且不会在 Analytics 中填充任何报表。

本文档还会向您演示如何在 Analysis Workspace 完成移动设备使用情况报告。

## 迁移处理规则

如果您要将 Mobile Services 用于免费功能，例如处理规则和使用情况报告功能，则可以无缝迁移到 Analytics UI（处理规则 UI 或 Analysis Workspace）来完成这些功能。对于生命周期量度，或者在 AA 处理规则 UI 中设置的规则，无需进行任何迁移。生命周期量度是现成可用的量度，当您在应用程序中首次实施 Mobile SDK 时自动收集。

但是，如果您在 Mobile Services UI 设置了任何其他处理规则（在生命周期量度之外），则应迁移这些处理规则，这样在您无法访问 Mobile Services 之后才能在 Analytics 中编辑/删除这些规则。

1. 登录 `experience.adobe.com` 并转到 Mobile Services。
1. 对您要将其上下文变量映射迁移到 Adobe Analytics 的移动应用程序，单击其齿轮图标。
1. 单击&#x200B;**[!UICONTROL 管理变量和量度]**&#x200B;菜单项，然后单击&#x200B;**[!UICONTROL 自定义变量]**&#x200B;选项卡。在这里，您可以看到向配置中添加了哪些上下文变量映射（上下文数据）。记录这些配置（或拍摄屏幕快照）。 示例：

   ![上下文变量](assets/context-var.png)

1. 在Experience Cloud中，切换到Adobe Analytics并确保您位于在Mobile Services中查看的同一移动设备报表包中。
1. 转到&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 处理规则]**。
1. 单击&#x200B;**[!UICONTROL 添加规则]**。
1. 忽略条件并继续，添加与在 Mobile Services 中相同的上下文变量。

   ![处理规则](assets/proc-rule.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。

## Analysis Workspace 中的移动设备使用情况报告

除了移动量度和维度之外（如果为 Mobile Services 启用了报表包），Analysis Workspace 将包含多个有助于分析的 Mobile 项目模板：

* **[!UICONTROL 消息]**：重点关注应用程序内和推送消息传送性能。
* **[!UICONTROL 位置]**：包括可展示位置数据的“地图”。
* **[!UICONTROL 关键量度]**：掌握应用程序关键量度。
* **[!UICONTROL 应用程序使用情况]**：应用程序拥有多少用户、启动次数和首次启动次数，以及平均会话时长是多少？
* **[!UICONTROL 客户获取]**：移动设备客户获取链接的表现如何？
* **[!UICONTROL 性能]**：应用程序性能如何、用户在哪些情况下遇到问题？
* **[!UICONTROL 维系率]**：谁是我的忠实用户，他们会怎么做？
* **[!UICONTROL 历程]**：我的应用程序最突出的使用模式是什么？

此处是移动应用程序使用情况模板的摘录：

![移动应用程序使用情况](assets/mobile-app-usage.png)

要访问该模板，请执行以下操作：

1. 登录 `experience.adobe.com` 并选择 Analytics。
1. 确保您位于为Mobile Services启用的报表包中。
1. 单击 **[!UICONTROL Workspace]** 选项卡。
1. 单击&#x200B;**[!UICONTROL 新建项目]**。
1. 选择任意 Mobile 模板并单击&#x200B;**[!UICONTROL 创建]**。

## 迁移其他 Mobile Services 功能

以下 Mobile Services 功能也已绑定到 Adobe Analytics，但需要已购买 Adobe Analytics SKU：

* 客户获取链接
* 推送消息传送
* 应用程序内消息传送
* 位置兴趣点管理

如果您将 Mobile Services 用于付费功能，则没有向其他内部/外部工具迁移的可行途径：

* 对于客户获取链接，我们可以将您引导至 Adobe Partners 以满足您的需求。
* 推送消息传送和应用程序内消息传送在 Adobe Campaign Standard 和 Adobe Campaign Classic（仅限推送）中可用。但是，用于定位的底层数据集是不同的。我们建议您与 Adobe 客户团队合作来确定消息传送数据的迁移选项。
* 对于位置功能，建议您采用新的[Adobe Experience Platform位置服务](https://www.adobe.com/experience-platform/location-service.html)，该服务对所有Adobe Experience Platform客户免费。
