---
description: 在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以编辑预定义渠道以满足您的需求，或创建您自己的渠道（最多 25 个）。
subtopic: Marketing channels
title: 管理营销渠道
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: dd58453a0459bc200a00badf34d06c259ce9fb59

---


# 管理营销渠道

在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以编辑预定义渠道以满足您的需求，或创建您自己的渠道（最多 25 个）。

以下是创建渠道的一些指示：

* 通过列出所有渠道进行预先计划，以便将所有访客点击划分到正确的渠道。
* 始终包括[内部](/help/components/c-marketing-channels/mc-faq/c-faq.md)点击和[直接](/help/components/c-marketing-channels/mc-faq/c-faq.md)点击类别的渠道。

Adding channels to the [!UICONTROL Marketing Channels] page is done independently of creating rules on the [Marketing Channel Processing Rules](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md) page. 创建规则时，您应将规则和渠道相关联。

## 添加营销渠道 {#add-mktg-channels}

在营销渠道管理器中添加营销渠道。

> [!NOTE] 您无法删除渠道。如果您不想使用某个渠道，您可以禁用或重命名该渠道并将其保存以供日后使用。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. 在页 [!UICONTROL Report Suite Manager] 面上，选择报表包。

   如果您选择多个报表包，则需要选择一个可将设置从模板复制到选定报表包的模板。

   请参阅 [将模板报表包设置应用于多个报表包](/help/components/c-marketing-channels/getting-started/t-template.md).

1. 单击 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   如果您的报表包未定义渠道，则会显示“[自动设置](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md)”页面。

1. 在页面 [!UICONTROL Marketing Channel Manager] 上，单击 **[!UICONTROL Add Channel]**。

   当定义了 25 个渠道时，此选项便不再可用。

1. 单击 **[!UICONTROL Save.]**
1. 要配置渠道规则，请单击 **[!UICONTROL Marketing Channel Processing Rules]**。

   请参阅[创建营销渠道处理规则](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md)。

## 营销渠道管理器 - 界面定义 {#mktg-channel-mgr}

页面的字段定 [!UICONTROL Marketing Channel Manager] 义。

| 字段 | 定义 |
|--- |--- |
| 启用 | 启用或禁用此营销渠道。 |
| 渠道名称 | 营销渠道的易记名称。 |
| 覆盖最近联系渠道 | 您可以选择是否用所选渠道覆盖现有持续的最近联系渠道。如果选中此复选框，任何渠道（包括直接和内部）都将会覆盖现有的最近联系渠道。结果会导致对不该取得信用的渠道进行转换。例如，如果用户此前已经通过免费搜索渠道取得信用，则此选项可以确保直接渠道不会接收用于转换的信用。 |
| 渠道划分 | 允许您使用该值划分渠道。You can add possible channel breakdowns (subchannels) when creating [marketing channel classifications](/help/components/c-marketing-channels/mc-classifications/classifictions-mchannel.md). |
| 类型 | 指定用户访问您网站的途径。您可以选择在线或离线。对于通过搜索引擎或电子邮件促销活动来访的访客，使用“在线”渠道。“离线”渠道适用于通过报纸优惠券或杂志广告发现您网站的访客。离线渠道通常包括通过报表数据源导入的数据。请参阅[数据源](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html)。请参阅[添加离线数据](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md)。 |
| 颜色 | 与此营销渠道关联的颜色。此颜色代表营销渠道报表中的渠道。 |