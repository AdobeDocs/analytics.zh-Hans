---
title: 营销渠道入门
description: 了解营销渠道工作流、自动设置以及如何将模板报表包设置应用到多个报表包。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 营销渠道入门

营销渠道通常用于分析访客如何到达您的网站。 您可以根据要跟踪的渠道以及要跟踪的方式自定义您的营销渠道处理规则。

营销渠道主要考虑首次联系和最近联系量度，这两个量度属于标准转化量度。

## 营销渠道工作流

![](assets/step1_icon.png) 根据企业要求定义每个渠道。

定义您使用的渠道是营销渠道中最重要的组件之一。 定义渠道可能需要组织中的多个人之间进行协作。 以下是几个需要考虑的问题：

* 您使用付费搜索吗？
* 您是否在使用电子邮件活动? 您是否在使用要单独跟踪的多个电子邮件活动?
* 您是否有将流量导向您网站的附属机构？ 您是否希望单独跟踪的附属机构？
* 是否存在有利于单独跟踪的外部活动?
* 您是要聚合所有社交网站，还是要单独跟踪任何社交网站？
* 是否有其他渠道可能影响要跟踪的转化？

推荐的列表渠道可在常见问题解答和示 [例中找到](/help/components/c-marketing-channels/c-faq.md)。 创建要使用的渠道列表，以便在创建渠道时方便启用和定义渠道。

![](assets/step2_icon.png) 在页面上添加营销渠道 [!UICONTROL Marketing Channel Manager] 信息。

After defining what channels to track, you enable them in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

请参阅[渠道和规则](/help/components/c-marketing-channels/c-channels.md)，以了解先决条件和概念等重要信息。

请参阅[添加营销渠道](/help/components/c-marketing-channels/c-channels.md)，以了解相关过程。

>[!NOTE]
>
>如果之前未配置营销渠道，则会显示[自动设置](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。此设置提供了若干可自定义的预配置渠道。 Adobe建议您将这些规则用作模板。 但是，如果您已有可靠的渠道定义，则可以跳过自动设置。

![](assets/step3_icon.png) 在页面上配置或调整每个渠道的 [!UICONTROL Marketing Channel Processing Rules] 规则。

在页面上创建渠道 [!UICONTROL Marketing Channel Manager] 后，您可以配置规则，以便渠道能够检索和报告数据。

See [Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md).

如果在自动设置中创建了渠道，则会定义这些渠道中的规则。 您可以根据自己的需求修改它们。

## 营销渠道的自动设置 {#run-auto-setup}

营销渠道报表包含一个一次性设置页面，帮助您入门。它提供了多个可用于跟踪的营销渠道。 如果您觉得可以创建渠道和规则，可以跳过此设置。 但是，Adobe建议您允许向导为您创建渠道。 通过自动设置，您可以查看规则的构建方式，或根据自己的用途编辑它们。 您可以随时禁用或删除预定义的渠道。

如何运行营销渠道自动设置。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. 在上， [!UICONTROL Report Suite Manager]选择一个报表包。
1. 单击 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![步骤结果](assets/wizard.png)

   >[!NOTE]
   >
   >The [!UICONTROL Marketing Channels: Auto Setup] page displays automatically when you access channel configuration applications in Admin Tools. （请参阅[营销渠道管理器](/help/components/c-marketing-channels/c-channels.md)。）如果您的报表包包含一个或多个营销渠道，则不显示此页面。 除非您选择其他不包含营销渠道的报表包，否则您无法再次访问此页面。

1. 确保选定您要创建的渠道。

   选择后， **[!UICONTROL Email]**、 **[!UICONTROL Display]**&#x200B;和 **[!UICONTROL Affiliate]** 是必填字段。

1. 单击 **[!UICONTROL Save]**.

## 将模板报表包设置应用于多个报表包

如何使用主报表包作为模板来测试您的营销渠道配置。 要节省时间，您可以在批量更新中将此模板应用到一个或多个生产报表包。 您可以分别对渠道和规则集执行此任务。

>[!NOTE] 在应用规则集之前，需要先应用模板中的渠道。在执行此步骤时,您的渠道在所有报表包上必须相同。

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

