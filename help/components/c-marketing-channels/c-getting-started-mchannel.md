---
title: 营销渠道入门
description: 了解营销渠道工作流、自动设置以及如何将模板报表包设置应用到多个报表包。
translation-type: tm+mt
source-git-commit: 21f4b9df688776f7a1db96f76e258031ae3abb3d

---


# 营销渠道入门

营销渠道通常用于提供有关访客如何到达您网站的分析。您可以基于要跟踪的渠道以及跟踪方式，自定义营销渠道处理规则。

营销渠道主要考虑首次联系和最近联系量度，这两个量度属于标准转化量度。

## 营销渠道工作流

![](assets/step1_icon.png) 根据企业要求定义每个渠道.

定义使用的渠道是营销渠道中最重要的步骤之一。定义渠道可能需要贵组织中多名人员通力合作。以下是需要考虑的几个问题：

* 您使用的是否为付费搜索？
* 您使用的是否为电子邮件促销活动？您是否正在使用多个要单独跟踪的电子邮件促销活动？
* 是否有附属活动将流量导向您的网站？是否有需要单独跟踪的附属活动？
* 是否有更适合单独跟踪的外部促销活动？
* 是要汇总所有社交网站还是要单独跟踪其中某些网站？
* 是否要跟踪可能影响转化的其他渠道？

建议的渠道列表可在[常见问题和示例](/help/components/c-marketing-channels/c-faq.md)中找到。创建要使用的渠道列表，以便在创建渠道时方便启用和定义渠道。

![](assets/step2_icon.png) 在页面上添加营销 [!UICONTROL Marketing Channel Manager] 渠道。

After defining what channels to track, you enable them in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

请参阅[渠道和规则](/help/components/c-marketing-channels/c-channels.md)，以了解先决条件和概念等重要信息。

请参阅[添加营销渠道](/help/components/c-marketing-channels/c-channels.md)，以了解相关过程。

>[!NOTE]
>
>如果之前未配置营销渠道，则会显示[自动设置](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。该设置提供多个可自定义的预配置渠道。Adobe 建议将这些规则用作模板。但如果已有固定的渠道定义，则可跳过自动设置。

![](assets/step3_icon.png) 在页面上配置或调整每个渠道的 [!UICONTROL Marketing Channel Processing Rules] 规则。

After you create channels on the [!UICONTROL Marketing Channel Manager] page, you configure the rules so that channels can retrieve and report data.

See [Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md).

如果渠道是在自动设置中创建的，则这些渠道中的规则已经过定义。您可以修改这些规则以满足您的需求。

## 营销渠道的自动设置 {#run-auto-setup}

营销渠道报表包含一个一次性设置页面，帮助您入门。它提供了多个可用于跟踪的营销渠道。如果您觉得对创建渠道和规则得心应手，可以跳过此设置。然而，Adobe 建议您允许该向导为您创建渠道。自动设置可使您了解规则是如何构建的，还可让您根据自己的需要进行编辑。您可以随时禁用或删除预定义的渠道。

如何运行营销渠道自动设置。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. 在上， [!UICONTROL Report Suite Manager]选择一个报表包。
1. 单击 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![步骤结果](assets/wizard.png)

   >[!NOTE]
   >
   >The [!UICONTROL Marketing Channels: Auto Setup] page displays automatically when you access channel configuration applications in Admin Tools. （请参阅[营销渠道管理器](/help/components/c-marketing-channels/c-channels.md)。）如果您的报表包包含一个或多个营销渠道，则本页面不会显示。除非您选择另一个不含营销渠道的报表包，否则您不能再访问此页面。

1. 确保选定您要创建的渠道。

   选择后， **[!UICONTROL Email]**、 **[!UICONTROL Display]**&#x200B;和 **[!UICONTROL Affiliate]** 是必填字段。

1. 单击 **[!UICONTROL Save]**.

## 将模板报表包设置应用于多个报表包

如何使用主报表包作为模板来测试您的营销渠道配置。为了节省时间，您可以在批量更新中将此模板应用于一个或多个生产报表包。您需要为渠道和规则集分别执行此任务。

> [!NOTE] 在应用规则集之前，需要先应用模板中的渠道。在执行此步骤时,您的渠道在所有报表包上必须相同。

1. 确保为选定的报表包启用了“营销渠道报表”。您的帐户管理员会执行此步骤。
1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the **[!UICONTROL Report Suite Manager]** page, select the template report suite, as well as one or more target report suites.
1. 单击 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. 在页面 **[!UICONTROL Select Master Report Suites]** 上，选择一个模板报表包。
1. 单击 **[!UICONTROL Save All]**.
1. 将模板中的规则应用于多个报表包： 
   1. 返回页 [!UICONTROL Report Suite Manager] 面。
   1. 选择模板报表包，以及一个或多个目标报表包。
   1. 单击 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. 单击 **[!UICONTROL Save]**. 如果“保存”按钮在此步骤中处于禁用状态，请通过展开其中一项规则来启用它。

