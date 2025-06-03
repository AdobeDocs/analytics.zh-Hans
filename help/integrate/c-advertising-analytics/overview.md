---
description: 了解您可以使用Advertising Analytics执行的所有操作，包括所需的权限以及可用的维度和量度。
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 70%

---

# Advertising Analytics

通过Advertising Analytics，您可以在Adobe Analytics中并排查看所有Google广告和Microsoft Advertising付费搜索数据。 以前，必须在Google Advertising Cloud (AMO)或每个相应的广告界面中查看任何Microsoft Ads或Advertising数据。 您现在可以直接从搜索引擎以及AMO ID实例（点击实例）获取展示次数、点击次数和成本数据。

将这些来自搜索引擎的数据集中到 Adobe Analytics 之后，您即可使用 Analysis Workspace 的强大功能对同样的数据进行分析。Workspace中新增的[付费搜索性能](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md)模板有助于进行此分析。

![](assets/aa_aw.png)

此集成针对以下受众：

* 需要为付费搜索营销人员搜集性能报告的&#x200B;**分析师**。
* 要寻找这些问题的答案的&#x200B;**付费搜索营销人员**：我将多少流量发送到我们的网站？其中形成客户转化的流量有多少？成本效益高的广告促销活动有哪些？


## 先决条件 {#prerequisites}

* Advertising Analytics 仅适用于 Adobe Analytics [Select](https://www.adobe.com/cn/data-analytics-cloud/analytics/select.html)、[Prime](https://www.adobe.com/cn/data-analytics-cloud/analytics/prime.html) 和 [Ultimate](https://www.adobe.com/cn/data-analytics-cloud/analytics/ultimate.html) 三种 SKU 版本。
* 非 Advertising Cloud 和非 AMO 的客户都可以使用此功能。
* 您必须是Adobe Analytics管理员才能访问Advertising Analytics，或者您属于已被[授予对Advertising Analytics的访问权限](/help/integrate/c-advertising-analytics/overview.md#permissions)的产品配置文件。
* 对于您想要在其中查看Google广告或Microsoft Advertising搜索数据的任何报表包，必须[为Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)启用这些报表包&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL Advertising Analytics配置]**。
* 您需要用户登录凭据（如 Google 帐户 ID 和密码），且该用户对您想要与 Adobe Analytics 集成的搜索帐户须拥有编辑权限。
* 对于Microsoft Advertising，您还需要[[!UICONTROL 帐户ID]和[!UICONTROL 经理帐户ID]](c-adanalytics-workflow/aa-locate-account-id.md)。

## Advertising Analytics 权限 {#permissions}

Analytics具有自动授予Analytics管理员的两个权限。 然后，管理员可以选择向非管理员授予这些权限。

| 权限 | 定义 | 登录到 Adobe Experience Cloud 后授予权限 |
| --- | --- | --- |
| Advertising Analytics 管理 | 允许用户设置/编辑/查看广告搜索帐户。 | 登录到[adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL 产品] > [!UICONTROL Adobe Analytics] > [!UICONTROL 产品配置文件] > [!UICONTROL 权限]选项卡> [!UICONTROL Analytics工具] > [!UICONTROL Advertising Analytics管理] |
| Advertising Analytics 配置 | 允许用户将报表包配置为可以使用 Advertising Analytics。 | 登录到[adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL 产品] > [!UICONTROL Adobe Analytics] > [!UICONTROL 产品配置文件] > [!UICONTROL 权限]选项卡> [!UICONTROL Analytics工具] > [!UICONTROL Advertising Analytics配置] |

## Advertising Analytics维度和量度 {#dimensions-metrics}

Advertising Analytics可将以下维度和量度添加到Analysis Workspace、Report Builder和Analytics报表API。

### 维度

>[!IMPORTANT]
>
>这项集成可通过 AMO ID 变量的分类创建一组新维度。这些新的维度不会影响或修改您现有的营销渠道或促销活动跟踪变量维度。当访客通过付费搜索广告登陆网站时，AMO ID 会连接到访客配置文件。因此，AMO 维度不仅可用于划分由此集成提供的 AMO 指标，还可以划分由访客在下游捕获的任何数据（访问次数、访客数、页面查看次数、跳出率、订单数、收入、自定义事件数等等）。在报告其他本地指标时，它们也可以按照其他维度进行划分。
>
>这些指标的分类每天更新一次。因此，如果您在搜索引擎中更改元数据，那么您可能要在这些分类更新后的第二天才能看到这些更改。

| 分类（维度）名称 | 定义 |
| --- | --- |
| **[!UICONTROL 关键字MatchType (AMO ID)]** | 关键字匹配类型。这些值通常为广泛、短语、精确；或者如果广告类型没有匹配类型，则没有值。 |
| **[!UICONTROL 广告平台(AMO ID)]** | 搜索引擎名称。值可以包括“Google AdWords”或“Microsoft Bing Ads”。 |
| **[!UICONTROL 帐户(AMO ID)]** | 正在跟踪的搜索引擎帐户名称。 |
| **[!UICONTROL 促销活动(AMO ID)]** | 搜索引擎帐户中的促销活动名称。 |
| **[!UICONTROL 广告组(AMO ID)]** | 搜索引擎促销活动中的广告组名称。 |
| **[!UICONTROL 广告(AMO ID)]** | 广告中使用的广告标题 + 广告描述。 |
| **[!UICONTROL 关键字(AMO ID)]** | 来自您的搜索引擎帐户的“关键字”值。 |
| **[!UICONTROL 匹配类型(AMO ID)]** | 分配给关键字的关键字匹配类型。这些值通常为广泛、短语、精确；或者如果广告类型没有匹配类型，则没有值。 |
| **[!UICONTROL 广告类型(AMO ID)]** | 投放的广告类型，通常为&quot;文字广告&quot;。 |
| **[!UICONTROL 广告标题(AMO ID)]** | 广告中使用的“标题”对象。 |
| **[!UICONTROL 广告描述(AMO ID)]** | 广告中使用的“广告描述”对象。 |
| **[!UICONTROL 广告显示URL (AMO ID)]** | 广告中使用的“广告显示 URL”对象。 |
| **[!UICONTROL 广告目标URL (AMO ID)]** | 分配给您的广告的登陆页面 URL 或最终 URL。 |
| **[!UICONTROL 网络(AMO ID)]** | 用于投放广告的网络。对于 Advertising Analytics，该值始终为“搜索”。 |
| **[!UICONTROL 投放位置(AMO ID)]** | 托管投放网站（适用于内容网络）。只有托管投放才会使用此维度。 |
| **[!UICONTROL 产品目标(AMO ID)]** | PLA 广告（非购买的实际产品）上使用的产品目标的名称。 |
| **[!UICONTROL 优化(AMO ID)]** | Advertising Analytics 不使用此功能。此功能仅由 Advertising Cloud 客户使用。 |
| **[!UICONTROL 设备(AMO ID)]** | 当前未使用。这是一个占位符，用于将来可能针对广告（非访客的实际设备）的指定目标设备类型（例如移动设备、桌面设备）实施的产品增强功能。 |

### 量度

>[!IMPORTANT]
>
>Advertising Analytics 提供的指标（如下所列）是来自搜索引擎的概要级别的数据。它们未连接到 Analytics 访客配置文件。它们仅连接到 AMO ID 变量及其关联的分类维度。因此，不应根据 AMO ID 维度以外的任何维度/区段对这些指标进行报告。这样做会导致 Analytics 将这些数据都显示为零。您可以将它们与其他指标一起纳入计算指标中，但这些计算指标也只应按照 AMO ID 维度进行划分。
>
>这些指标是每日收集的数据，因此不会有当天的数据。也不应以低于每日的粒度对其进行报告。
>
>登陆页面上设置 AMO ID 时，会设置一个 AMO ID 实例数指标（即点进次数）。此指标是在发生登陆页面点击时实时捕获的，可用来与其他也在登陆页面上设置的维度一起进行划分。

| 量度名称 | 定义 |
| --- | --- |
| **[!UICONTROL AMO展示次数]** | 搜索引擎所报告的广告展示次数。 |
| **[!UICONTROL AMO点击次数]** | 搜索引擎所报告的广告点击次数。 |
| **[!UICONTROL AMO成本]** | 搜索引擎所报告的每个关键字/广告的成本花费。 |
