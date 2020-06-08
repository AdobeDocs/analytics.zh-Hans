---
title: 营销渠道的处理规则
description: 营销渠道处理规则决定访客点击是否符合分配到渠道的标准。这些规则处理访客在网站上的每次点击。当规则不符合渠道标准时，或者如果规则配置不正确，系统会将该点击分配到“未识别渠道”。
translation-type: tm+mt
source-git-commit: 8e8eb2c7787f97104c983cc4b0f11e5ed57de069
workflow-type: tm+mt
source-wordcount: '2048'
ht-degree: 75%

---


# 营销渠道的处理规则

营销渠道处理规则通过处理访客在您的网站上进行的每次点击，确定访客点击是否满足分配给渠道的条件。 这些规则将按您指定的顺序处理，当符合某个规则时，系统将停止处理其余规则。

![](assets/buckets_2.png)

有关处理的附加说明：
* 通过这些规则收集的数据全部为永久性数据，数据收集后再更改的规则不具有可回溯性。强烈建议您首先仔细查看和考虑各种情况，然后再保存[!UICONTROL 营销渠道处理规则]来迁移错误渠道中收集的数据。
* 该报表一次最多可处理 25 个渠道。
* 规则可以访问已由 VISTA 设置的变量，但不能访问已被 VISTA 删除的数据。
* 两个营销渠道从不会接收相同事件的信用，如购买或点击次数。在这方面，营销渠道不同于 eVar（两个 eVar 可能会接收相同事件的信用）。
* 如果规则存在空白覆盖，您可能会看到“未识 [别渠道”。](/help/components/c-marketing-channels/c-faq.md)

## 先决条件

* 查看[营销渠道快速入门](/help/components/c-marketing-channels/c-getting-started-mchannel.md)中的概念信息。
* 创建一个或更多渠道，以便您将规则分配给它们。请参阅[添加营销渠道](/help/components/c-marketing-channels/c-channels.md)。

## 创建营销渠道处理规则

创建营销渠道处理规则，这些规则决定访客点击是否符合分配到渠道的标准。

此步骤使用电子邮件规则作为示例。该示例假定您已经将电子邮件渠道添加到“营销渠道管理器”页面上的渠道列表中。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
2. 选择报表包。

   如果您的报表包未定义渠道，则会显示[!UICONTROL “营销渠道：自动设置”]页面。

   请参阅[运行自动设置](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。

3. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 营销渠道]** > **[!UICONTROL 营销渠道处理规则]**。

   ![步骤结果](assets/marketing_channel_rules.png)

4. 从&#x200B;**[!UICONTROL 添加新的规则集]**&#x200B;菜单中，选择&#x200B;**[!UICONTROL 电子邮件]**。

   这样做不是在选择渠道，而是选择使用几个必要参数填充规则的模板。您可以根据需要修改此模板。

   ![步骤结果](assets/example_email.png)

5. 要继续创建规则，请单击&#x200B;**[!UICONTROL 添加规则]**。
6. 要对规则优先排序，请将其拖放到所需位置。
7. 单击&#x200B;**[!UICONTROL 保存]**。

继续在本页中查看有关渠道规则顺序的建议以及更多定义示例。

### 设置营销渠道值

**添[!UICONTROL 加规&#x200B;]**则设置渠道的值]**定义可用于该渠道的营销渠道详细信息维。 这使您能够细分营销渠道维度并查看有关渠道的更多详细信息。

建议将渠道值设置为用于定义渠道本身的相同标准。 例如，如果使用查询字符串参数定义渠道，则还应将查询字符串参数设置为渠道值。

### 规则条件

此参考表定义了可用于定义营销渠道处理规则的字段、选项和点击属性。

| 术语 | 定义 |
|--- |--- |
| 全部 | 当编号规则中所有规则都正确时激活此渠道。 |
| 任何 | 当规则集中任何规则都正确时激活此渠道。仅当编号规则中存在一条以上规则时，此选项才可用。 |
| AMO ID | Advertising Cloud 和 Advertising Analytics 集成使用的主要跟踪代码。如果启用其中一个集成，可以使用跟踪代码前缀来标识特定于 Advertising Cloud 的渠道。对于搜索，使用以“AL”开头的“AMO ID”；对于显示，使用以“AC”开头的“AMO ID”；对于社交，使用以“AO”开头的“AMO ID”。在营销渠道中使用 AMO ID 时，点击/成本/展示次数量度可归因于正确的渠道（未配置时，这些量度将转至“直接”或“无”）。 |
| AMO ED ID | Advertising Cloud 使用的辅助跟踪代码。此跟踪代码的主要用途是用作将数据发送回 Ad Cloud 的键值。但是，如果您希望将显示点进次数和显示视图点进次数作为两个单独的营销渠道，还可以使用此代码来标识它们。可以通过为显示点进次数设置以“:d”结尾的“AMO EF ID”的营销渠道逻辑，或者为显示视图点进次数设置以“:i”结尾的“AMO EF ID”的营销渠道逻辑来实现此操作。如果您不希望将显示拆分为两个渠道，可以改为使用 AMO ID 维度。 |
| 转化变量 | 由为本报表包启用的 eVar 组成，并且只在通过网页上的 Adobe 代码设置变量时才适用。请参阅实施指南。 |
| 存在 | 可使用若干选项，包括：<ul><li>**不存在**：指定请求上不存在点击属性。例如在反向链接域中，如果用户键入一个 URL 或单击一个书签，则该反向链接域属性不存在。</li><li>**为空**：指定点击属性存在，通常为 eVar 或查询字符串参数，但没有任何与点击属性相关的值。</li><li>**不包含**：例如，您可以指定反向链接域不包含特定值（这与使用选项“包含”。）</li></ul> |
| 将渠道识别为 | 将规则与您添加到“营销渠道管理器”页面上的营销渠道相关联。请参阅添加营销渠道。 |
| 匹配付费搜索检测规则 | Adobe 检测的付费搜索。付费搜索是指公司向列出它们网站的搜索引擎支付费用。付费搜索通常出现在搜索结果顶部或右侧。 |
| 匹配免费搜索检测规则 | Adobe 报表检测的免费搜索。 |
| 引用网站与内部 URL 筛选器匹配 | 按照“管理工具”中对报表包的定义，页面 URL 与内部 URL 筛选器匹配的访问。 |
| 引用网站与内部 URL 筛选器不匹配 | 按照“管理工具”中对报表包的定义，引用 URL 与内部 URL 筛选器不匹配。您可以将此设置与“页面 URL”和“存在”一起使用来设置一个通用规则，这样就不会有访问登陆报表中的未识别渠道区域。 |
| 忽略与内部 URL 过滤器匹配的点击量 | （关于反向链接）只跟踪来自外部引用网站的点击量。通常，将此设置保留为启用状态，除非您希望包括内部流量。 |
| 是访问第一页 | Adobe 报表检测到的访问第一页。 |
| 页面 | 网站上使用 Adobe 网络信标标记的网页名称。该值等同于 s.pageName。示例包括 `Home Page` 和 `About Us`。 |
| 页面域 | 访客所登陆页面的域，如 `products.example.co.uk`。 |
| 页面域和路径 | 域和路径，如 `products.example.co.uk/mens/pants/overview.html`。 |
| 页面根目录域 (TLD+1) | 访客所登陆页面的根目录域，如 example.co.uk。 |
| 页面 URL | 网站上网页的 URL。 |
| 反向链接域 | 访客访问您的网站之前来自的域，例如反向链接来自 `abcsite.com` 和 `xyzsite.com`。 |
| 查询字符串参数 | 如果您网站上的页面 URL 类似于 `https://example.com/?page=12345&cat=1`，则 page 和 cat 都是查询字符串参数。（请参阅 `https://en.wikipedia.org/wiki/Query_string`。）您只可为每个规则集指定一个查询字符串参数。要添加额外的查询字符串参数，可使用 `ANY` 作为您的运算符，然后将新的查询字符串参数添加到规则中。 |
| 反向链接 | 访客在访问您的网站前所在的网页位置（完整的 URL）。反向链接存在于所定义域的外部。 |
| 引荐域和路径 | 引荐域和 URL 路径的组合。示例包括：    `www.example.com/products/id/12345` 或 `ad.example.com/foo` |
| 引荐参数 | 反向链接 URL 上的查询字符串参数。例如，如果您的访客来自 `example.com/?page=12345&cat=1`，则 page 和 cat 为引荐参数。 |
| 引荐根目录域 | 引荐的根目录域。反向链接存在于所定义域的外部。 |
| 搜索引擎 | Google 或 Yahoo! 等引导访客进入您网站的搜索引擎。 |
| 搜索关键词 | 用于在搜索引擎上执行搜索的单词。 |
| 搜索引擎 + 关键词 | 唯一识别搜索引擎的搜索关键词和搜索引擎组合。例如，如果您搜索 computer 这个词，搜索引擎和关键词识别如下： `Search Tracking Code = "<search_type>:<search engine>:<search keyword>" where    search_type = "n" or "p", search_engine = "Google", and search_keyword = "computer"`**注意：**n = 免费；p = 付费 |
| 将渠道值设置为 | 除了解哪些营销渠道为网站带来访客外，您还可以知道访客的网站活动应归功渠道中哪些横幅广告、搜索关键词或电子邮件促销活动。此 ID 是一个与渠道一起存储的渠道值。通常此值为嵌入在登陆页或反向链接 URL 中的促销活动 ID；在其他情况下，它是搜索引擎和搜索关键词的组合，或是准确从特定渠道中识别访客的反向链接 URL。 |

## 营销渠道规则顺序和定义 {#channel-rules}

渠道规则将按您指定的顺序处理。 渠道订单的推荐方法是首先将付费或受管渠道（例如付费搜索、自然搜索、显示、电子邮件）放在位，以便他们接收信用，然后是有机渠道（例如直接、内部、引用域）。

以下是渠道规则和示例定义的建议顺序：

### 付费搜索 {#paid-search}

付费搜索是您向搜索引擎支付用于放置在搜索结果中的词或短语。 此渠道通常根据查询字符串参数(请参阅显示渠道示例)或付费搜索检测规则来定义。 此决定取决于您要记录的营销渠道详细信息。

#### 付费搜索检测

为了匹配付费搜索检测规则，营销渠道使用[!UICONTROL “付费搜索检测”]页面上配置的设置。（**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 付费搜索检测]**）。目标 URL 匹配该搜索引擎的现有付费搜索检测规则。

对于营销渠道规则，[!UICONTROL “付费搜索”]设置如下：

![](assets/example_paid_search.png)

有关详细信息，请参阅管理员中的[付费搜索检测](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html)。

### 免费搜索 {#natural-search}

免费搜索是指，在您无需为您的网站排名向搜索引擎支付费用的情况下，访客就能通过网络搜索找到您的网站。

分析没有免费搜索检测的功能。在设置了“付费搜索检测”之后，系统可以推断出如果一个搜索反向链接不是付费的，则它必然是免费搜索反向链接。有关详细信息，请参阅管理员中的[付费搜索检测](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html)。

对于营销渠道规则，“免费搜索”设置如下：

![](assets/example_natural_search.png)

### 显示 {#display}

这项规则识别来自横幅广告的访客。它是由目标 URL 中的查询字符串参数标识的，在此例中为 *`Ad_01`*。

![](assets/example_display.png)

### 电子邮件 {#email}

此规则标识来自电子邮件访客的活动。 它是由目标 URL 中的查询字符串参数标识的，在此例中为 *`eml`*:

![](assets/example_email.png)

### 附属活动 {#afilliates}

此规则标识源自指定引用域集的访客。 在规则中，您需要按如下所示列出要跟踪的附属活动域：

![](assets/example_affiliates.png)

### 其他活动 {#other-campaigns}

最佳实践是纳入“其他活动”渠道，遵守所有付费渠道规则。 此渠道充当未分类付费流量的“全包”。

![](assets/other-campaigns.png)

### 社交网站 {#social-networks}

这项规则识别来自 Facebook* 等社交网络的访客。该渠道通常更名为Organic Social。 其设置如下所示：

![](assets/example_social.png)

### 内部（会话刷新）渠道 {#internal}

此规则访客其引用URL与Admin Console中的内部URL过滤器设置相匹配，这意味着访客来自站点以开始其访问。 此渠道通常重命名为“会话刷新”。

![](assets/int-channel1.png)

请参 [阅内部（会话刷新）的原因](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-faq.html) ，以了解发生此渠道的原因。

### 直接 {#direct}

此规则标识没有引用域的访客，该引用域包括直接进入您的站点的访客，如从“收藏夹”链接或通过在其浏览器中粘贴链接。 此渠道通常重命名为直接输入／书签。

![](assets/example_direct.png)

### 引用域渠道 {#referring-domains}

引用域渠道标识具有引用域的访客。 内部域、直接域和引用域渠道共同充当所有尚未分类为渠道的其余点击的全部捕获。

![](assets/referring-domains.png)