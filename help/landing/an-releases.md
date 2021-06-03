---
description: 介绍 Adobe Analytics 的全新连续功能发布战略
title: Adobe Analytics 功能发布
exl-id: 1e403bef-4aab-4a9a-a358-62449ce801ff
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 92%

---

# Adobe Analytics 功能发布

以前，Adobe Analytics 功能发布之后会有为期一个月的固定工作安排。从 2020 年 4 月开始，Adobe Analytics 采用连续交付模型，该模型允许采用更具扩展性的分阶段方法来部署功能。

## 发布策略

[!UICONTROL Analysis Workspace] 使用功能标志（又称为“切换”）控制新功能的可见性，从而允许在完全发布之前进行受控规模测试。此发布策略包括以下阶段：

* **发布到生产 (RTP)**：将代码发布到生产，并在 Analysis Workspace 中关闭功能可见性。**注意**：在 RTP 阶段，可能在 2.0 Analytics API 中提供此功能。

* **有限测试**：从 Adobe 内部用户测试开始的分阶段发布。然后，此发布在两个月内从可用性 0% 扩展到 100%。由于分阶段推出在 Experience Cloud 组织级别进行，因此组织中所有授权用户都可以获得相同的体验。

* **正式发布 (GA)**：此功能对 100% 授权的 Experience Cloud 组织可用，且功能发布已完成。

对于每个功能发布，从 RTP 到 GA 的时间表可能会有所不同。目标是缩短发布时间，以便能够在发布开始 (RTP) 后的 2 个月内，功能将达到 GA 阶段。

## 功能标记

功能标记用于在发布过程中控制新功能的可见性。Adobe 建议将 app.launchdarkly.com 添加到防火墙的[允许列表](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=zh-Hans)，以在发布过程中获得最佳体验。到达 GA 后不久，将删除该标记。

您可以随时在&#x200B;**帮助 > 关于 Workspace > 活动功能标记**&#x200B;下查看活动功能标记。

## 优点

分阶段发布使 Adobe 能够更好地扩展软件部署过程，并确保功能在正式发布之前得到全面强化。它还允许功能一经可用即可发布，而不用遵循固定的月度发布时间期限。

## 常见问题解答

| 问题 | 回答 |
|---|---|
| 我是否可以请求提前访问某个功能？ | 不会。不会授予提前访问权限。<br>如果您想要提前测试 Analytics 概念，我们建议您试用 [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/tech-previews/overview.html)，就我们行业领先的创新技术提供反馈。 |
| 此发布策略是否会影响我对功能的访问？ | 不会。一旦某个功能达到 GA 阶段，您将有权访问该功能，前提是它包含在您的 Analytics 程序包中。<br>您可以在管理员 [!UICONTROL  > ] 所有管理员 [!UICONTROL  > ] 公司设置 [!UICONTROL  > ] 功能访问级别 [](https://experienceleague.adobe.com/docs/analytics/admin/company-settings/feature-access-levels.html)下查看您的Analytics包的详细信息。 |
