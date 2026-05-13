---
description: 了解您可以使用Advertising Analytics执行的所有操作，包括所需的权限以及可用的维度和量度。
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
TQID: https://experienceleague.adobe.com/BY9Zpnhu8FzGDHePD-MuWtyMWOuJKRgC-wTr42-rlyU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1132
ht-degree: 24%

---

# Advertising Analytics

通过Advertising Analytics，您可以在Adobe Analytics中并排查看所有Google广告和Microsoft Advertising付费搜索数据。 以前，必须在Google或每个相应的广告界面中查看任何Adobe Advertising广告或Microsoft Advertising数据。 您现在可以直接从搜索引擎以及AMO ID实例（点击实例）获取展示次数、点击次数和成本数据。

通过将来自这些搜索引擎的数据放入Adobe Analytics中，您可以使用Analysis Workspace的强大功能分析相同数据。 Workspace中新增的[付费搜索性能](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md)模板有助于进行此分析。

![](assets/aa_aw.png)

此集成针对以下受众：

* 需要为付费搜索营销人员收集性能报告的&#x200B;**分析师**。
* **付费搜索营销人员**&#x200B;在寻求以下问题的答案：我向网站发送的流量以及客户转化率是多少？ 我的广告促销活动具有哪些成本效益？


## 先决条件 {#prerequisites}

* Advertising Analytics仅适用于Adobe Analytics [Select](https://www.adobe.com/cn/data-analytics-cloud/analytics/select.html)、[Prime](https://www.adobe.com/cn/data-analytics-cloud/analytics/prime.html)和[Ultimate](https://www.adobe.com/cn/data-analytics-cloud/analytics/ultimate.html) SKU。
* 此功能适用于不使用Adobe Advertising的客户。
* 您必须是Adobe Analytics管理员才能访问Advertising Analytics，或者您属于已被[授予对Advertising Analytics的访问权限](/help/integrate/c-advertising-analytics/overview.md#permissions)的产品配置文件。
* 对于您想要在其中查看Google广告或Microsoft Advertising搜索数据的任何报表包，必须[为Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)启用这些报表包&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL Advertising Analytics配置]**。
* 您需要具有搜索帐户（您要与Adobe Analytics集成）编辑权限的用户登录凭据，例如Google帐户ID和密码。
* 对于Microsoft Advertising，您还需要[[!UICONTROL 帐户ID]和[!UICONTROL 经理帐户ID]](c-adanalytics-workflow/aa-locate-account-id.md)。

## Advertising Analytics 权限 {#permissions}

Analytics具有自动授予Analytics管理员的两个权限。 然后，管理员可以选择将这些权限授予非管理员。

| 权限 | 定义 | 如果您已登录到Adobe Experience Cloud，则授予权限 |
| --- | --- | --- |
| Advertising Analytics 管理 | 允许用户设置/编辑/查看广告搜索帐户。 | 登录到[adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL 产品] > [!UICONTROL Adobe Analytics] > [!UICONTROL 产品配置文件] > [!UICONTROL 权限]选项卡> [!UICONTROL Analytics工具] > [!UICONTROL Advertising Analytics管理] |
| Advertising Analytics 配置 | 允许用户配置要为Advertising Analytics配置的报表包。 | 登录到[adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL 产品] > [!UICONTROL Adobe Analytics] > [!UICONTROL 产品配置文件] > [!UICONTROL 权限]选项卡> [!UICONTROL Analytics工具] > [!UICONTROL Advertising Analytics配置] |

## Advertising Analytics维度和量度 {#dimensions-metrics}

Advertising Analytics可将以下维度和量度添加到Analysis Workspace、Report Builder和Analytics报表API。

### 维度

>[!IMPORTANT]
>
>这项集成可通过 AMO ID 变量的分类创建一组新维度。 这些新维度不会影响或修改您现有的营销渠道或促销活动跟踪变量维度。 当访客从付费搜索广告登陆网站时，AMO ID会连接到访客的配置文件。 因此，AMO 维度不仅可用于划分由此集成提供的 AMO 指标，还可以划分由访客在下游捕获的任何数据（访问次数、访客数、页面查看次数、跳出率、订单数、收入、自定义事件数等等）。 在报告其他本地指标时，它们也可以按照其他维度进行划分。
>
>这些指标的分类每天更新一次。 因此，如果您对搜索引擎中的元数据进行了更改，您可能直到第二天更新分类后才会看到这些更改反映出来。

| 分类（维度）名称 | 定义 |
| --- | --- |
| **[!UICONTROL 关键字MatchType (AMO ID)]** | 关键字匹配类型。 值通常为广泛、精确或无值（如果广告类型没有匹配类型）。 |
| **[!UICONTROL 广告平台(AMO ID)]** | 搜索引擎名称。 值可以包括“Google AdWords”或“Microsoft Bing Ads”。 |
| **[!UICONTROL 帐户(AMO ID)]** | 被跟踪的搜索引擎帐户的名称。 |
| **[!UICONTROL 促销活动(AMO ID)]** | 您的搜索引擎帐户中的促销活动的名称。 |
| **[!UICONTROL 广告组(AMO ID)]** | 您的搜索引擎促销活动中的广告组的名称。 |
| **[!UICONTROL 广告(AMO ID)]** | 广告上使用的广告标题+广告描述。 |
| **[!UICONTROL 关键字(AMO ID)]** | 来自您的搜索引擎帐户的“关键字”值。 |
| **[!UICONTROL 匹配类型(AMO ID)]** | 分配给您的关键字的关键字匹配类型。 值通常为广泛、精确或无值（如果广告类型没有匹配类型）。 |
| **[!UICONTROL 广告类型(AMO ID)]** | 投放的广告类型，通常为&quot;文字广告&quot;。 |
| **[!UICONTROL 广告标题(AMO ID)]** | 广告中使用的Title对象。 |
| **[!UICONTROL 广告描述(AMO ID)]** | 广告中使用的Ad Description对象。 |
| **[!UICONTROL 广告显示URL (AMO ID)]** | 广告中使用的广告显示URL对象。 |
| **[!UICONTROL 广告目标URL (AMO ID)]** | 分配给您的广告的登陆页面URL或最终URL。 |
| **[!UICONTROL 网络(AMO ID)]** | 为广告提供服务的网络。 对于 Advertising Analytics，该值始终为“搜索”。 |
| **[!UICONTROL 投放位置(AMO ID)]** | 托管式投放网站（适用于内容网络）。 仅托管投放使用此维度。 |
| **[!UICONTROL 产品目标(AMO ID)]** | PLA广告中使用的产品目标的名称（不是实际购买的产品）。 |
| **[!UICONTROL 优化(AMO ID)]** | Advertising Analytics未使用。 它仅供Adobe Advertising客户使用。 |
| **[!UICONTROL 设备(AMO ID)]** | 今天未使用。 用于为指示的广告目标设备类型（例如移动设备、桌面，而非访客的实际设备）提供潜在未来产品增强功能的占位符。 |

### 量度

>[!IMPORTANT]
>
>Advertising Analytics 提供的指标（如下所列）是来自搜索引擎的概要级别的数据。 它们未连接到Analytics访客资料。 它们仅连接到AMO ID变量及其关联的分类维度。 因此，不应根据 AMO ID 维度以外的任何维度/区段对这些指标进行报告。 这样做会导致Analytics为数据显示零。 您可以将它们与其他指标一起纳入计算指标中，但这些计算指标也只应按照 AMO ID 维度进行划分。
>
>这些指标是每日收集的数据，因此不会有当天的数据。 此外，也不应在低于每日的粒度上报告这些事件。
>
>登陆页面上设置 AMO ID 时，会设置一个 AMO ID 实例数指标（即点进次数）。 此指标是在发生登陆页面点击时实时捕获的，可用来与其他也在登陆页面上设置的维度一起进行划分。

| 量度名称 | 定义 |
| --- | --- |
| **[!UICONTROL AMO展示次数]** | 搜索引擎报告的广告展示次数。 |
| **[!UICONTROL AMO点击次数]** | 搜索引擎报告的广告点击次数。 |
| **[!UICONTROL AMO成本]** | 搜索引擎所报告的每个关键词/广告的已付成本。 |
