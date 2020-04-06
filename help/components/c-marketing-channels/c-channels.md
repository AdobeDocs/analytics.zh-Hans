---
description: 在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，通过自动设置，您可以创建多个渠道及其规则。 您可以编辑预定义的渠道以满足您的需求，或创建您自己的订阅（最多25个）。
subtopic: Marketing channels
title: 管理营销渠道
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 管理营销渠道

在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，通过自动设置，您可以创建多个渠道及其规则。 您可以编辑预定义的渠道以满足您的需求，或创建您自己的订阅（最多25个）。

以下是创建渠道的准则：

* 通过对所有渠道进行列表，提前规划，以便将所有访客点击分类到正确的渠道。
* 始终包含内部点击和 [Direct点击的类别](/help/components/c-marketing-channels/c-faq.md)[的渠道](/help/components/c-marketing-channels/c-faq.md) 。

向页面添加渠道 [!UICONTROL Marketing Channels] 与在“营销渠道处理规则”页面上创 [建规则无关](/help/components/c-marketing-channels/c-rules.md) 。 在创建规则时，将规则与渠道关联。

## 添加营销渠道 {#add-mktg-channels}

在营销渠道管理器中添加营销渠道。

>[!NOTE] 您无法删除渠道。如果您不想使用某个渠道，您可以禁用或重命名该渠道并将其保存以供日后使用。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. 在页 [!UICONTROL Report Suite Manager] 面上，选择报表包。

   如果选择多个报表包，请选择一个模板，将设置从模板复制到选定的报表包。

   See [Apply template report suite settings to multiple report suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. 单击 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   如果您的报表包未定义渠道，则会显示“[自动设置](/help/components/c-marketing-channels/c-getting-started-mchannel.md)”页面。

1. 在页面 [!UICONTROL Marketing Channel Manager] 上，单击 **[!UICONTROL Add Channel]**。

   当定义了 25 个渠道时，此选项便不再可用。

1. 单击 **[!UICONTROL Save.]**
1. 要为渠道配置规则，请单击 **[!UICONTROL Marketing Channel Processing Rules]**。

   请参阅[创建营销渠道处理规则](/help/components/c-marketing-channels/c-rules.md)。

## 营销渠道管理器 - 界面定义 {#mktg-channel-mgr}

页面的字段定 [!UICONTROL Marketing Channel Manager] 义。

| 字段 | 定义 |
|--- |--- |
| 启用 | 启用或禁用此营销渠道。 |
| 渠道名称 | 营销渠道的易记名称。 |
| 覆盖最近联系渠道 | 允许您选择是否使用所选渠道覆盖现有的永久上次联系渠道。 如果选中此复选框，则任何渠道(包括直接和内部渠道)都将覆盖现有的上次联系。 结果是转化被归因于可能不值得信贷的渠道。 例如，此选项可以确保直接渠道在用户之前通过自然搜索渠道获得过转换信用时不会收到该信用。 |
| 渠道划分 | 允许您按此值划分渠道。 您可以在创建营销渠道分类时添加可能的渠道细 [分（子渠道）](/help/components/c-marketing-channels/classifictions-mchannel.md)。 |
| 类型 | 指定用户如何进入您的站点。 您可以选择在线或离线。对通过搜索引擎或电子邮件渠道的访客使用在线活动。 线下渠道适用于通过报纸优惠券或杂志广告找到您网站的访客。 脱机渠道通常包括通过报告数据源导入的数据。 请参阅[数据源](https://docs.adobe.com/content/help/zh-Hans/analytics/import/data-sources/datasrc-home.html)。请参阅[添加离线数据](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。 |
| 彩色 | 与此营销渠道关联的颜色。 此颜色代表营销渠道报表中的渠道。 |

## 定义渠道

在报表中显示渠道和渠道数据之前，请创建处理数据的渠道和基础规则。 您还可以为关联的渠道创建成本和预算金额，并指定希望访客参与期的持续时间。 您可以在管理工具中执行报表配置任务。

将渠道视为访问容器。 规则将访问分配给相应的容器。

![](assets/buckets_2.png)

Adobe在自动设置过程中提供了多个预 [定义渠道](/help/components/c-marketing-channels/c-getting-started-mchannel.md) ，您可以根据自己的需要编辑这些预定义区域。

>[!NOTE]
>
>Adobe 建议您在可作为测试用模板的报表包中设置报表。您可以使用模板将渠道和规则集全局应用到一个或多个生产报表包。
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

### 先决条件 {#prereqs}

如有必要，请联系客户支持来帮助您实现这些先决条件：

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   有关详细信息，请参阅 Analytics 帮助中的[一般帐户设置](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/admin-tools/general-acct-settings-admin.html)。

* 设置对营销渠道维的访问权限。

   See [Marketing Channels permissions](/help/components/c-marketing-channels/c-channel-report-access.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

### 重要的处理说明 {#important-proc-rules}

* 系统按您指定的顺序处理规则，当满足规则时，系统将停止处理其余规则。
* 规则可以访问VISTA已设置的变量，但不能访问VISTA已删除的数据。
* 渠道只存储转化量度。 流量指标不可用。
* 两个营销渠道从不会收到同一事件的积分（如购买或点击）。 这样，营销渠道与eVar不同(其中两个eVar可能会收到同一事件的积分)。
* 报告一次最多可处理25个渠道。

