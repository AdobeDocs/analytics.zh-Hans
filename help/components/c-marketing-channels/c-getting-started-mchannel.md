---
title: 《营销渠道快速入门》
description: 了解营销渠道工作流程、自动设置以及如何将模板报表包设置应用到多个报表包。
feature: Marketing Channels
exl-id: 35938bf9-89ab-434f-9dc2-7a65251412ef
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 97%

---

# 营销渠道快速入门

>[!NOTE]
>
>为了最大化归因和 Customer Journey Analytics 的营销渠道效率，我们发布了一些[修订后的最佳实践](/help/components/c-marketing-channels/mchannel-best-practices.md)。
>
>Analytics 管理员可以管理其组织的营销渠道，如[管理营销渠道](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md)中所述。

营销渠道通常用于提供有关访客如何到达您网站的分析。您可以基于要跟踪的渠道以及跟踪方式，自定义营销渠道处理规则。

营销渠道主要考虑首次联系和最近联系指标，这两个指标属于标准转化指标。

## 营销渠道工作流程

![](assets/step1_icon.png) 根据企业要求定义每个渠道。

定义使用的渠道是营销渠道中最重要的步骤之一。定义渠道可能需要贵组织中多名人员通力合作。以下是需要考虑的几个问题：

* 您使用的是否为付费搜索？
* 您使用的是否为电子邮件促销活动？您是否正在使用多个要单独跟踪的电子邮件促销活动？
* 是否有附属活动将流量导向您的网站？是否有需要单独跟踪的附属活动？
* 是否有更适合单独跟踪的外部促销活动？
* 是要汇总所有社交网站还是要单独跟踪其中某些网站？
* 是否要跟踪可能影响转化的其他渠道？

建议的渠道列表可在[常见问题和示例](/help/components/c-marketing-channels/c-faq.md)中找到。创建要使用的渠道列表，以便在创建渠道时方便启用和定义渠道。

![](assets/step2_icon.png) 在“[!UICONTROL 营销渠道管理器]”页面上添加营销渠道。

定义要跟踪的渠道后，可在&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**&#x200B;中启用它们。

请参阅[渠道和规则](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md)，以了解先决条件和概念等重要信息。

请参阅[添加营销渠道](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md)，以了解相关过程。

>[!NOTE]
>
>如果之前未配置营销渠道，则会显示[自动设置](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。该设置提供多个可自定义的预配置渠道。Adobe 建议将这些规则用作模板。但如果已有固定的渠道定义，则可跳过自动设置。

![](assets/step3_icon.png)在[!UICONTROL 营销渠道处理规则]页面上配置或优化每个渠道的规则。

在[!UICONTROL 营销渠道管理器]页面上创建渠道后，可配置规则，以便渠道可检索和报告数据。

请参阅[营销渠道处理规则](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md)。

如果渠道是在自动设置中创建的，则这些渠道中的规则已经过定义。您可以修改这些规则以满足您的需求。

## 自动设置营销渠道 {#run-auto-setup}

营销渠道报表包含一个一次性设置页面，帮助您入门。它提供了多个可用于跟踪的营销渠道。如果您觉得对创建渠道和规则得心应手，可以跳过此设置。然而，Adobe 建议您允许该向导为您创建渠道。自动设置可使您了解规则是如何构建的，还可让您根据自己的需要进行编辑。您可以随时禁用或删除预定义的渠道。

如何运行营销渠道自动设置。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
1. 在[!UICONTROL 报表包管理器]上，选择一个报表包。
1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 营销渠道]** > **[!UICONTROL 营销渠道管理器]**。

   ![步骤结果](assets/wizard.png)

   >[!NOTE]
   >
   >当您访问“管理工具”中的渠道配置应用程序时，会自动显示[!UICONTROL 营销渠道: 自动设置]页面。（请参阅[营销渠道管理器](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md)。）如果您的报表包包含一个或多个营销渠道，则不会显示此页面。 除非您选择另一个不含营销渠道的报表包，否则您不能再访问此页面。

1. 确保选定您要创建的渠道。

   一旦选定，**[!UICONTROL 电子邮件]**、**[!UICONTROL 显示]**&#x200B;和&#x200B;**[!UICONTROL 附属活动]**&#x200B;便为必填字段。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 将模板报表包设置应用于多个报表包

如何使用主报表包作为模板来测试您的营销渠道配置。为了节省时间，您可以在批量更新中将此模板应用于一个或多个生产报表包。您需要为渠道和规则集分别执行此任务。

>[!NOTE]
>
>在应用规则集之前，需要先应用模板中的渠道。在执行此步骤时，您的渠道在所有报表包上必须相同。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
1. 在&#x200B;**[!UICONTROL “报表包管理器”]**&#x200B;页面上，选择模板报表包，以及一个或多个目标报表包。
1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 营销渠道]** > **[!UICONTROL 营销渠道管理器]**。
1. 在&#x200B;**[!UICONTROL “选择主报表包”]**&#x200B;页面上，选择一个模板报表包。
1. 单击&#x200B;**[!UICONTROL 全部保存]**。
1. 将模板中的规则应用于多个报表包： 
   1. 返回到[!UICONTROL “报表包管理器”]页面。
   1. 选择模板报表包，以及一个或多个目标报表包。
   1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 营销渠道]** > **[!UICONTROL 营销渠道处理规则]**。
   1. 单击&#x200B;**[!UICONTROL 保存]**。如果“保存”按钮在此步骤中处于禁用状态，请通过展开其中一项规则来启用它。
