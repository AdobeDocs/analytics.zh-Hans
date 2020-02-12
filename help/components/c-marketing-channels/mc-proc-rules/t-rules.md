---
title: 创建营销渠道处理规则
description: 创建营销渠道处理规则，这些规则决定访客点击是否符合分配到渠道的标准。
translation-type: tm+mt
source-git-commit: ea4d9e6c9396032fe323de594cb43eecbf97aa15

---


# 创建营销渠道处理规则

创建营销渠道处理规则，这些规则决定访客点击是否符合分配到渠道的标准。

此步骤使用电子邮件规则作为示例。该示例假定您已经将电子邮件渠道添加到“营销渠道管理器”页面上的渠道列表中。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. 选择报表包。

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md).

1. 单击 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![步骤结果](assets/marketing_channel_rules.png)

1. 从菜单 **[!UICONTROL Add New Rule Set]** 中，选择 **[!UICONTROL Email]**。

   这样做不是在选择渠道，而是选择使用几个必要参数填充规则的模板。

   ![步骤结果](assets/example_email.png)

   使用布尔逻辑（若/则语句）配置规则。例如，在电子邮件渠道规则中，提供以下规则语句中强调的设置或信息：

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   在此示例中，*`<value>`* 是您在电子邮件促销活动中使用的查询字符串参数，如 *`eml`*。
1. 要继续创建规则，请单击 **[!UICONTROL Add Rule]**。
1. 要对规则优先排序，请将其拖放到所需位置。
1. 单击 **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [常见问题和示例](/help/components/c-marketing-channels/mc-faq/c-faq.md)

