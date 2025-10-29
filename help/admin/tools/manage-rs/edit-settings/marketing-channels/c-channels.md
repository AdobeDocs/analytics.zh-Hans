---
description: 在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以根据自己的需要编辑预定义渠道，或创建自己的渠道（最多总共25个）。
subtopic: Marketing channels
title: 管理营销渠道
feature: Marketing Channels
exl-id: a768a4c2-f922-4d96-a9fb-78a1dfac04d8
role: Admin
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 68%

---

# 管理营销渠道

>[!NOTE]
>
> 有关营销渠道的一般信息，请参阅[营销渠道快速入门](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。
>
> 为了最大限度地提高归因和 Customer Journey Analytics 的营销渠道效率，我们发布了一些[修订后的最佳实践](/help/components/c-marketing-channels/mchannel-best-practices.md)。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 营销渠道]** > **[!UICONTROL 营销渠道管理器]**。

在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以根据自己的需要编辑预定义渠道，或创建自己的渠道（最多总共25个）。

向[!UICONTROL 营销渠道]页面添加渠道与在[营销渠道处理规则](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)页面上创建规则是相互独立的。 创建规则时，可以将规则与渠道关联。

以下是创建渠道的指南：

* 通过列出所有渠道提前计划，以便将所有访客点击分类到正确的渠道。
* 包括[内部](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)点击类别的渠道。
* 包括一个全能型“其他营销活动”渠道，放在付费渠道之后且有机渠道之前。


## 先决条件 {#prereqs}

* 设置对营销渠道维度的访问权限。

  请参阅[营销渠道权限](/help/components/c-marketing-channels/c-channel-report-access.md)。

## 添加营销渠道 {#add-mktg-channels}

在营销渠道管理器中添加营销渠道。

>[!NOTE]
>
>您无法删除渠道。如果您不想使用某个渠道，您可以禁用或重命名该渠道并将其保存以供日后使用。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
1. 在“[!UICONTROL 报表包管理器]”页面上，选择一个报表包。

   如果您选择多个报表包，则需要选择一个可将设置从模板复制到选定报表包的模板。

   请参阅[将模板报表包设置应用于多个报表包。](/help/components/c-marketing-channels/c-getting-started-mchannel.md)

1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 营销渠道]** > **[!UICONTROL 营销渠道管理器]**。

   如果您的报表包未定义渠道，则会显示“[自动设置](/help/components/c-marketing-channels/c-getting-started-mchannel.md)”页面。

1. 在“[!UICONTROL 营销渠道管理器]”页面上，单击&#x200B;**[!UICONTROL 添加渠道]**。

   当定义了 25 个渠道时，此选项便不再可用。

1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 要配置渠道规则，请单击&#x200B;**[!UICONTROL 营销渠道处理规则]**。

   请参阅[创建营销渠道处理规则](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)。

## 应用渠道设置 {#mktg-channel-mgr}

可以将各种设置应用于[!UICONTROL 营销渠道管理员]页面上的每个渠道。

| 字段 | 定义 |
|--- |--- |
| 已启用 | 启用或禁用此营销渠道。 |
| 渠道名称 | 营销渠道的友好名称。 |
| 覆盖最近联系渠道 | 允许您选择是否使用选定的渠道覆盖现有的永久最近联系渠道。 如果选中此复选框，则任何渠道（包括直接和内部）都将覆盖现有的最近联系渠道。 结果是将转化归因于可能不值得该评价的渠道。 例如，如果之前已通过“免费搜索”渠道获得用户，则此选项可以确保“直接”渠道不会收到转化积分。 |
| 渠道细分 | 允许您按此值划分渠道。 创建[营销渠道分类时](/help/admin/tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md)，您可以添加可能的渠道划分（子渠道）。 |
| 类型 | 指定用户访问网站的方式。 您可以选择在线或离线。对于通过搜索引擎或电子邮件促销活动访问的访客，请使用在线渠道。 线下渠道适用于通过报纸优惠券或杂志广告找到您网站的访客。 离线渠道通常包括通过报告数据源导入的数据。请参阅[数据源](/help/import/data-sources/overview.md)。请参阅[添加离线数据](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。 |

### 覆盖最佳实践

最好取消选中“直接”和“内部”渠道的覆盖最近联系选项，以便这些渠道不能从其他持久保留的最近联系渠道获得点数（或相互获得点数）。

![](assets/int-channel2.png)

## 定义渠道规则

先创建渠道和用于处理数据的基础规则，然后渠道和渠道数据才能显示在报告中。您还可以指定希望[访客参与期](/help/admin/tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md)的持续时间。

Adobe 在[自动设置](/help/components/c-marketing-channels/c-getting-started-mchannel.md)过程中提供了多个预定义渠道，您可以根据自己的需要进行编辑。此外，您还可以修改此设置，并在[营销渠道处理规则](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)中定义自定义规则。

>[!NOTE]
>
>Adobe 建议您在可作为测试用模板的报表包中设置报告。您可以使用该模板将这些渠道和规则集全局应用到一个或多个生产报表包中。
>
>请参阅[将模板报表包设置应用于多个报表包。](/help/components/c-marketing-channels/c-getting-started-mchannel.md)
