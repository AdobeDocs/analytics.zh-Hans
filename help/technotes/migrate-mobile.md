---
description: 了解如何将Mobile Services处理规则迁移到Adobe Analytics
title: 将Mobile Services处理规则迁移到Adobe Analytics
translation-type: tm+mt
source-git-commit: bdb6f9ba435513cd1dc3febf35eae0e821c756ca
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 18%

---


# 将Mobile Services处理规则迁移到Adobe Analytics

随着AdobeMobile Services功能即将（尚未宣布）失效，本文档向您提供有关如何将您在Mobile Services UI中创建的任何其他处理规则（超出生命周期指标）迁移到Adobe Analytics的说明。

处理规则用于将上下文数据变量的值迁移到 prop 和 eVar。例如，您可以将“search-term”上下文eVar变量的值放入商务变量的值中，并在每次点击时覆盖该值。 如果没有处理规则，上下文数据变量将毫无意义，并且不会在 Analytics 中填充任何报表。

## 迁移处理规则

如果您正在利用Mobile Services获得免费功能(如处理规则和使用报告功能)，则可以无缝移至Analytics UI(处理规则UI或Analysis Workspace)来完成这些功能。 对于在AA处理规则UI中设置的生命周期指标或规则，您无需执行任何迁移。 生命周期指标是“现成”指标，在您的应用程序中首次实施Mobile SDK时自动收集。

但是，如果您在Mobile Services UI（超出生命周期指标）中设置任何其他处理规则，则应迁移这些规则，以便您在失去Mobile Services访问权限后在Analytics中编辑／删除它们。

1. 登录experience.adobe.com并转到Mobile Services。
1. 单击要迁移到Adobe Analytics的上下文变量映射的移动应用程序的齿轮图标。
1. 单击“管 **[!UICONTROL 理变量和度量]** ”菜单项，然后单击“自 **[!UICONTROL 定义变量]** ”选项卡。 在此，您可以看到哪些上下文变量映射（上下文数据）已添加到配置中。 记下这些配置（或拍下屏幕截图）。 示例：

   ![上下文变量](assets/context-var.png)

1. 在Experience Cloud中，切换到Adobe Analytics并确保您位于Mobile Services中查看的同一移动报告套件中。
1. 转至“管理员”>“报表包”>“编辑设置”>“常规”>“处理规则”。
1. 单击添加规则。
1. 忽略这些条件并继续添加Mobile Services中存在的相同上下文变量。

   ![处理规则](assets/proc-rule.png)

## Analysis Workspace的移动使用报告

除了移动指标和维度（如果为Mobile Services启用了报表包）之外，Analysis Workspace还包含若干可促进分析的移动项目模板：

* 消息：重点关注应用内消息和消息推送的性能。
* 位置：包括可展示位置数据的“地图”
* 关键量度：掌握应用程序关键量度。
* 应用程序使用情况：应用程序拥有多少用户、启动次数和首次启动次数，以及平均会话时长是多少？
* 收购：移动客户获取链接的性能如何？
* 性能：应用程序性能如何、用户在哪些情况下遇到问题？
* 维系率：谁是我的忠实用户，他们会怎么做？
* 历程：我的应用程序最突出的使用模式是什么？

以下是“移动应用程序使用情况”模板的摘录：

![移动应用程序使用](assets/mobile-app-usage.png)

要访问模板，请执行以下操作：

1. 登录experience.adobe.com并选择“分析”。
1. 确保您位于为Mobile Services启用的报表包中。
1. 单击“工作区”(Workspace)选项卡。
1. 单击新建项目。
1. 选择任何移动模板，然后单击创建。

## 迁移其他Mobile Services功能

以下Mobile Services功能也与Adobe Analytics相关，但需要购买的Adobe AnalyticsSKU:

* “客户获取链接”
* 推送消息
* 应用程序内消息传送
* 位置目标点管理

如果您正在利用Mobile Services实现付费功能，则没有可行的迁移途径可迁移到其他内部／外部工具：

* 对于客户获取链接，我们可以将您定向到Adobe合作伙伴，以满足您的需求。
* 虽然Adobe Campaign Standard和Adobe Campaign Classic（仅限推送）提供推送消息和应用程序内消息传递的各种功能，但用于定位的基础数据集不同，不可能迁移数据或消息活动。
* 对于位置功能，建议您采用全新的 [Adobe Experience Platform位置服务](https://www.adobe.com/experience-platform/location-service.html)，该服务对所有AEP客户都是免费的。
