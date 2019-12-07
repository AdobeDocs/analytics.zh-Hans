---
description: 创建营销渠道处理规则，这些规则决定访客点击是否符合分配到渠道的标准。
subtopic: Marketing channels
title: 创建营销渠道处理规则
topic: Reports and analytics
uuid: 0e47634f-3c69-46db-8af4-8d0b3d15f7a8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 创建营销渠道处理规则

创建营销渠道处理规则，这些规则决定访客点击是否符合分配到渠道的标准。

此步骤使用电子邮件规则作为示例。该示例假定您已经将电子邮件渠道添加到“营销渠道管理器”页面上的渠道列表中。

1. 单击 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理员]** &gt; **[!UICONTROL 报表包]**。
1. 选择报表包。

   如果您的报表包未定义渠道，则会显示[!UICONTROL “营销渠道：自动设置”]页面。

   请参阅[运行自动设置](/help/components/c-marketing-channels/c-channel-autosetup.md)。

1. 单击&#x200B;**[!UICONTROL 编辑设置]** &gt; **[!UICONTROL 营销渠道]** &gt; **[!UICONTROL 营销渠道处理规则]**。

   ![步骤结果](assets/marketing_channel_rules.png)

1. 从&#x200B;**[!UICONTROL 添加新的规则集]**&#x200B;菜单中，选择&#x200B;**[!UICONTROL 电子邮件]**。

   这样做不是在选择渠道，而是选择使用几个必要参数填充规则的模板。

   ![步骤结果](assets/example_email.png)

   使用布尔逻辑（若/则语句）配置规则。例如，在电子邮件渠道规则中，提供以下规则语句中强调的设置或信息：

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   在此示例中，*`<value>`* 是您在电子邮件促销活动中使用的查询字符串参数，如 *`eml`*。
1. 要继续创建规则，请单击&#x200B;**[!UICONTROL 添加规则]**。
1. 要对规则优先排序，请将其拖放到所需位置。
1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!MORELIKETHIS]
>
>* [常见问题和示例](/help/components/c-marketing-channels/c-faq.md)

