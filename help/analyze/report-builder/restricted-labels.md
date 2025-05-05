---
title: Report Builder 中受到限制的标签是什么
description: 描述 Report Builder 中受到限制的标签
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: eedabc6295f9b918e1e00b93993680e676c216c3
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 49%

---

# Report Builder 中受到限制的标签

通常，Adobe Analytics中与数据治理相关的设置继承自Adobe Experience Platform。 Adobe Analytics与Adobe Experience Platform数据管理之间的集成允许标记敏感Adobe Analytics数据和实施隐私政策。

在Experience Platform使用的数据集上创建的隐私标签和策略可以在Adobe Analytics报表包工作流中显示。 这些标签会阻止或警告从敏感字段创建量度和/或维度的用户。有关数据集的更多信息，请参阅[数据集概述](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=zh_Hans)。

此外，从Adobe Analytics导出数据时（通过报表、导出、API等），将添加警告或标签，以通知用户报表包含需要以特定方式处理的敏感信息。

此集成允许您更轻松地管理合规性。 组织中的数据管理员可以设置策略以限制使用。 因此，您的Adobe Analytics用户可以更自信地使用数据，因为他们知道此等数据使用符合数据管理员定义的策略。

有关详细信息，请参阅[Adobe Analytics和数据管理](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=zh-Hans)

## 查看 Report Builder 中受到限制的标签

Adobe Analytics中出现了两个Adobe定义的策略，这些策略影响报表、下载和共享：

* 强制分析策略
* 强制下载策略

受这些策略影响的组件将以灰色显示。当您将鼠标悬停在应用了策略的组件上时，将会显示一条注释，以指示以下内容：**相关策略已应用于此字段，因此禁止使用此数据。**&#x200B;有关更多信息，请参阅[标签和政策](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=zh-Hans)。

![指示禁止使用数据的策略注释。](assets/rb-restricted-label.png)

## 更新包含受限数据的报告

如果用户创建的 Report Builder 报告中的数据元素后来受到限制，则在刷新报告时，会显示一条错误消息。

![稍后限制数据元素之后显示的错误消息。](assets/error-restricted-data.png)
