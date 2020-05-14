---
description: 解释Adobe Analytics的全新连续功能发布战略
title: Adobe Analytics —— 功能发布战略
translation-type: tm+mt
source-git-commit: 0b00405e9e27a427a85b0f4a0d970671ada4aa67
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---


# Adobe Analytics —— 功能发布战略

过去，Adobe Analytics功能的发布遵循固定的月度计划。 从2020年4月开始，Adobe Analytics将转向一种连续的投放模型，该模型允许采用更具可扩展性、分阶段的功能部署方法。

## 发布策略

[!UICONTROL 分析工作] 区使用功能标志（也称为“切换”）控制新功能的可见性，允许在完全发布之前进行受控缩放测试。 此发布策略包括以下阶段：

* **发布到生产(RTP)**: 代码发布到生产环境，并在分析工作区中关闭功能可见性。 **注意**: 此时，该功能可能在2.0 Analytics API中可用。

* **有限测试**: 分阶段发布从Adobe内部用户的测试开始。 然后，该版本在两个月内从0%扩展到100%的可用性。 分阶段转出在Experience Cloud组织级别进行，因此组织中的所有授权用户都可获得相同的体验。

* **一般可用性(GA)**: 该功能可供100%的授权Experience Cloud组织使用，且功能发布已完成。

在每个功能发布时，从RTP到GA的时间线可能会有所不同。 目标是缩短发行时间，这样在发行开始(RTP)的2个月内，功能将是GA。

## 优点

分阶段发布使Adobe能够更好地扩展软件部署流程，并确保功能在全面可用之前得到全面强化。 它还允许功能一经发布即可发布，而不是附在固定的月度发布窗口中。

## 常见问题解答

| 问题 | 回答 |
|---|---|
| 我是否可以请求提前访问某个功能？ | 不可以。不会授予提前访问权限。<br>如果您想要测试早期的Analytics概念，我们建议您尝试 [使用Adobe Analytics](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/tech-previews/overview.html) Labs来提供有关我们行业领先创新的反馈。 |
| 此发布策略是否会影响我访问功能？ | 不可以。一旦某项功能达到GA，您便有权访问该功能（如果该功能包含在您的Analytics包中）。<br>您可以在“管理员”>“视图设置”>“功 [!UICONTROL 能访问级] 别”下 [，以](https://docs.adobe.com/content/help/en/analytics/admin/company-settings/feature-access-levels.html)便公司Analytics包的详细信息。 |