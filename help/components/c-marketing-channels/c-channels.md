---
description: 在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以编辑预定义渠道以满足您的需求，或创建您自己的渠道（最多 25 个）。
subtopic: Marketing channels
title: 管理营销渠道
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 管理营销渠道

在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以编辑预定义渠道以满足您的需求，或创建您自己的渠道（最多 25 个）。

以下是创建渠道的一些指示：

* 通过列出所有渠道进行预先计划，以便将所有访客点击划分到正确的渠道。
* 始终包括[内部](/help/components/c-marketing-channels/c-faq.md)点击和[直接](/help/components/c-marketing-channels/c-faq.md)点击类别的渠道。

将渠道添加到[!UICONTROL “营销渠道”]页面与在[“营销渠道处理规则”](/help/components/c-marketing-channels/c-rules.md)页面上创建规则是两项不同的操作。创建规则时，您应将规则和渠道相关联。

## 添加营销渠道 {#add-mktg-channels}

在营销渠道管理器中添加营销渠道。

>[!NOTE] 您无法删除渠道。如果您不想使用某个渠道，您可以禁用或重命名该渠道并将其保存以供日后使用。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
1. 在“[!UICONTROL 报表包管理器]”页面上，选择一个报表包。

   如果您选择多个报表包，则需要选择一个可将设置从模板复制到选定报表包的模板。

   请参阅 [将模板报表包设置应用于多个报表包](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 营销渠道]** > **[!UICONTROL 营销渠道管理器]**。

   如果您的报表包未定义渠道，则会显示“[自动设置](/help/components/c-marketing-channels/c-getting-started-mchannel.md)”页面。

1. 在“[!UICONTROL 营销渠道管理器]”页面上，单击&#x200B;**[!UICONTROL 添加渠道]**。

   当定义了 25 个渠道时，此选项便不再可用。

1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 要配置渠道规则，请单击&#x200B;**[!UICONTROL 营销渠道处理规则]**。

   请参阅[创建营销渠道处理规则](/help/components/c-marketing-channels/c-rules.md)。

## 营销渠道管理器 - 界面定义 {#mktg-channel-mgr}

[!UICONTROL “营销渠道管理器”]页面的字段定义。

| 字段 | 定义 |
|--- |--- |
| 启用 | 启用或禁用此营销渠道。 |
| 渠道名称 | 营销渠道的易记名称。 |
| 覆盖最近联系渠道 | 您可以选择是否用所选渠道覆盖现有持续的最近联系渠道。如果选中此复选框，任何渠道（包括直接和内部）都将会覆盖现有的最近联系渠道。结果会导致对不该取得信用的渠道进行转换。例如，如果用户此前已经通过免费搜索渠道取得信用，则此选项可以确保直接渠道不会接收用于转换的信用。 |
| 渠道划分 | 允许您使用该值划分渠道。You can add possible channel breakdowns (subchannels) when creating [marketing channel classifications](/help/components/c-marketing-channels/classifictions-mchannel.md). |
| 类型 | 指定用户访问您网站的途径。您可以选择在线或离线。对于通过搜索引擎或电子邮件促销活动来访的访客，使用“在线”渠道。“离线”渠道适用于通过报纸优惠券或杂志广告发现您网站的访客。离线渠道通常包括通过报表数据源导入的数据。请参阅[数据源](https://docs.adobe.com/content/help/zh-Hans/analytics/import/data-sources/datasrc-home.html)。请参阅[添加离线数据](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。 |
| 颜色 | 与此营销渠道关联的颜色。此颜色代表营销渠道报表中的渠道。 |

## 定义渠道

先创建渠道和用于处理数据的基础规则，然后渠道和渠道数据才能显示在报表中。您还可以创建相关渠道的成本和预算金额，并指定您希望访客参与时间持续多久。在“管理工具”中执行报表配置任务。

渠道可以看作是一个收集访问的容器。规则把访问分配到正确的容器中。

![](assets/buckets_2.png)

Adobe 在[自动设置](/help/components/c-marketing-channels/c-getting-started-mchannel.md)过程中提供了多个预定义渠道，您可以根据自己的需要对这些渠道进行编辑。

>[!NOTE]
>
>Adobe 建议您在可作为测试用模板的报表包中设置报表。您可以使用该模板将这些渠道和规则集全局应用到一个或多个生产报表包中。
>
>请参阅[将模板报表包设置应用于多个报表包](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。

### 先决条件 {#prereqs}

如有必要，请联系客户支持来帮助您实现这些先决条件：

* 在“管理控制台”（“一般帐户设置”）中，启用报表包的&#x200B;**[!UICONTROL 转化级别]**（电子商务）选项。

   有关详细信息，请参阅 Analytics 帮助中的[一般帐户设置](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/admin-tools/general-acct-settings-admin.html)。

* 设置对营销渠道维的访问权限。

   See [Marketing Channels permissions](/help/components/c-marketing-channels/c-channel-report-access.md).

* 确保您的帐户管理员已经为您的报表包启用 了&#x200B;**[!UICONTROL 渠道报表]**。

### 重要的处理说明 {#important-proc-rules}

* 系统会按您指定的顺序处理规则，当一个规则得到满足时，系统会停止处理剩余规则。
* 规则可以访问已由 VISTA 设置的变量，但不能访问已被 VISTA 删除的数据。
* 渠道只存储转化量度。流量量度不可用。
* 两个营销渠道从不会接收相同事件的信用，如购买或点击次数。在这方面，营销渠道不同于 eVar（两个 eVar 可能会接收相同事件的信用）。
* 该报表一次最多可处理 25 个渠道。

