---
description: 了解如何填充为营销渠道设置的不同规则的最佳实践和相关示例。
title: 营销渠道常见问题解答和示例
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 营销渠道常见问题解答和示例

See [Create Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md) for definitions of fields displayed on the [!UICONTROL Marketing Channel Processing Rules] page.

## 常见问题解答 {#faq}

营销渠道处理规则的每个实施可能因跟踪代码而异。 配置提供您需要的结果的规则可能需要一些创造性思维来解决问题。

**问题**:我的跟踪代码不遵循模式，并且我的关联公司渠道必须指定数千个。

* 使用消除过程。 如果您的电子邮件和关联公司渠道使用相同的查询字符串参数，但您只有几个电子邮件跟踪代码，则可以在定义电子邮件的规则集中指定电子邮件跟踪代码。 然后，将所有其他跟踪代码 *`affiliates.`*
* 在您的电子邮件系统中，为所有登陆页面 URL 添加一个查询字符串参数，例如 *`&ch=eml`*。创建一个规则集，用于检测 ch 查询参数是否等于 *`eml`*。如果该规则集中不包含 *`eml`*，则它是一个附属活动。

**问题**：反向链接域包含的数据比我预期的多。

* 在处理规则列表中，引用域可能过高。 它应该是最后一个（或最后一个）规则集之一，因为处理顺序很重要。

**问题**:我已创建了一个与查询字符串参数匹配的规则，但该规则无效。

* 确保在查询字符串参数字段（通常为字母数字值）中指定参数名称。 此外，请确保在运算符后指定参数值，如以下电子邮件规则示例所示。

   ![](assets/example_email.png)

**问题**:为什么我的所有最后点击流量都归因于内部域？

* 您有一个与内部流量匹配的规则。 请记住，这些规则会针对访客在您的网站上进行的每次点击，而不仅仅是第一次访问。 If you have a rule like *`Page URL exists`* without other criteria, that channel is matched on each successive hit on your site, because a page URL always exists.

**问题**:如何调试报告上未识别渠道中显示的流量？

* 规则按顺序处理。 如果没有符合特定标准，则点击量属于三个类别之一：

1. 无反向链接（一次直接的访问）。

2. 访问首页上的内部反向链接。

3. 页面处理故障。

确保您有渠道实现这三种可能性。 例如，创建如下规则：

1. **[!UICONTROL Referrer]** 以 **[!UICONTROL Does Not Exist]** 及 **[!UICONTROL Is First Page of Visit]**。 （请参阅[直接](/help/components/c-marketing-channels/c-faq.md)。）

2.  **[!UICONTROL Referrer Matches Internal URL Filters]** 和 **[!UICONTROL Is First page of Visit]**。（请参阅[内部](/help/components/c-marketing-channels/c-faq.md)。）

3. **[!UICONTROL Referrer]** 以 **[!UICONTROL Exists]** 及 **[!UICONTROL Referrer Does Not Match Internal URL Filters]**。

最后，创建一个捕 *获剩余点击* (如未识别的渠道中所述) [的其他渠道](/help/components/c-marketing-channels/c-faq.md#no-channel-identified)。

## No Channel Identified {#no-channel-identified}

如果您的规则没有捕获数据，或规则配置不正确，则报告会在报告的行中显 [!UICONTROL No Channel Identified] 示数据。 您可以在处理顺序的结 *尾创建*“其他”规则集，该规则集也标识内部流量。

![](assets/example_other.png)

This kind of rule serves as a catch-all to ensure that channel traffic always matches external traffic, and typically does not end up in **[!UICONTROL No Channel Identified]**. 要小心不要建立一个同时确定内部流量的规则。Setting the channel&#39;s value to **[!UICONTROL Referring Domain]** or to **[!UICONTROL Page URL]** are the most common, useful ways to create an effective Other rule.

>[!NOTE] 仍可能会有一些渠道流量被列入“未识别渠道”类别。例如：访客进入网站并将一个页面加入书签，同一访问中通过书签返回页面。 由于这不是访问的第一页，因此它不会在直接渠道中或在其他渠道中转到，因为没有引用域。

## 付费搜索 {#paid-search}

付费搜索是指您为放置在搜索结果中而向搜索引擎付费的单词或短语。 为匹配付费搜索检测规则，营销渠道使用在页面上配置的 [!UICONTROL Paid Search Detection] 设置。 ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). 目标URL与该搜索引擎的现有付费搜索检测规则匹配。

对于营销渠道规则， [!UICONTROL Paid Search] 设置如下：

![](assets/example_paid_search.png)

有关更 [多信息，请参阅](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) “管理员”中的付费搜索检测。

## 免费搜索 {#natural-search}

当访客通过Web搜索找到您的网站时，即发生自然搜索，该搜索引擎在您无需支付列表费用的情况下对您的网站进行排名。 您可以控制搜索引擎用于链接到站点的目标URL。 此URL允许Analytics识别搜索是否是自然的。

Analytics中没有自然的搜索检测。 在您设置“付费搜索检测”后，系统会知道，如果搜索推荐人不是付费搜索推荐人，它必须是自然的搜索推荐人。 对于自然搜索，目标URL与该搜索引擎的现有付费搜索检测规则不匹配。

对于营销渠道规则，“自然搜索”设置如下：

![](assets/example_natural_search.png)

有关详 [细信息，请参阅](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) “管理员”中的付费搜索检测。

## 关联公司 {#afilliates}

附属机构规则标识源自指定引用域集的访客。 在规则中，您将列表要跟踪的关联公司的域，如下所示：

![](assets/example_affiliates.png)

## 社交网站 {#social-networks}

此规则识别源自社交网络（如Facebook*）的访客。 这些设置可以如下：

![](assets/example_social.png)

## 显示 {#display}

此规则标识来自横幅广告的访客。 它由目标URL中的查询字符串参数标识，在本例中为 *`Ad_01`*。

![](assets/example_display.png)

## 内部 {#internal}

此规则标识源自与报表包的内部URL访客相匹配的推荐人的过滤器。

![](assets/example_internal.png)

## 电子邮件 {#email}

要设置此规则，请为电子邮件查询提供活动字符串参数。 在此示例中，参数为 *`eml`*:

![](assets/example_email.png)

如果规则包含跟踪代码，则每行输入一个值，如下所示：

![](assets/tracking_code.png)

## 直接 {#direct}

此规则标识没有引用域的访客。 此规则包括直接进入您的站点的访客，例如从“收藏夹”链接或通过在其浏览器中粘贴链接来访问。

![](assets/example_direct.png)

