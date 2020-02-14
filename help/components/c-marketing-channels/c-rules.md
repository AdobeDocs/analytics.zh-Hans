---
title: 营销渠道的处理规则
description: 营销渠道处理规则决定访客点击是否符合分配到渠道的标准。这些规则处理访客在网站上的每次点击。当规则不符合渠道标准时，或者如果规则配置不正确，系统会将该点击分配到“未识别渠道”。
translation-type: tm+mt
source-git-commit: c10a12781a8fe52b7b897cd337dc686aa0bbb240

---


# 营销渠道的处理规则

营销渠道处理规则决定访客点击是否符合分配到渠道的标准。这些规则处理访客在网站上的每次点击。当规则不符合渠道标准时，或者如果规则配置不正确，系统会将该点击分配到“未识别渠道”。

以下是创建规则的重要指示：

* 将规则按所需处理顺序排序。
* 在列表末尾，纳入一条通用规则，如“其他”。该规则用于识别外部流量而非内部流量。

   请参阅[未识别渠道](/help/components/c-marketing-channels/c-faq.md)。

> [!NOTE] 尽管这些规则不会影响营销渠道以外的报表，但却会影响营销渠道数据收集。通过这些规则收集的数据全部为永久性数据，数据收集后再更改的规则不具有可回溯性。It is strongly recommended to review and consider all circumstances before saving [!UICONTROL Marketing Channel Processing Rules] to mitigate data being collected in incorrect channels.

## 先决条件

* 查看营销渠道入 [门中的概念信息](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。
* 创建一个或更多渠道，以便您将规则分配给它们。See [Add marketing channels.](/help/components/c-marketing-channels/c-channels.md)

## 创建营销渠道处理规则

创建营销渠道处理规则，这些规则决定访客点击是否符合分配到渠道的标准。

此步骤使用电子邮件规则作为示例。该示例假定您已经将电子邮件渠道添加到“营销渠道管理器”页面上的渠道列表中。

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. 选择报表包。

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

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
>* [常见问题和示例](/help/components/c-marketing-channels/c-faq.md)


## 营销渠道规则标准

此参考数据表定义您在“营销渠道处理规则”页面上可选择的字段、选项和点击属性。

| 术语 | 定义 |
|--- |--- |
| 全部 | 当编号规则中所有规则都正确时激活此渠道。 |
| 任何 | 当规则集中任何规则都正确时激活此渠道。仅当编号规则中存在一条以上规则时，此选项才可用。 |
| AMO ID | Advertising Cloud 和 Advertising Analytics 集成使用的主要跟踪代码。如果启用其中一个集成，可以使用跟踪代码前缀来标识特定于 Advertising Cloud 的渠道。对于搜索，使用以“AL”开头的“AMO ID”；对于显示，使用以“AC”开头的“AMO ID”；对于社交，使用以“AO”开头的“AMO ID”。在营销渠道中使用 AMO ID 时，点击/成本/展示次数量度可归因于正确的渠道（未配置时，这些量度将转至“直接”或“无”）。 |
| AMO ED ID | Advertising Cloud 使用的辅助跟踪代码。此跟踪代码的主要用途是用作将数据发送回 Ad Cloud 的键值。但是，如果您希望将显示点进次数和显示视图点进次数作为两个单独的营销渠道，还可以使用此代码来标识它们。可以通过为显示点进次数设置以“:d”结尾的“AMO EF ID”的营销渠道逻辑，或者为显示视图点进次数设置以“:i”结尾的“AMO EF ID”的营销渠道逻辑来实现此操作。如果您不希望将显示拆分为两个渠道，可以改为使用 AMO ID 维度。 |
| 转化变量 | 由为本报表包启用的 eVar 组成，并且只在通过网页上的 Adobe 代码设置变量时才适用。请参阅实施指南。 |
| 存在 | 可使用若干选项，包括：<ul><li>**不存在**：指定请求上不存在点击属性。例如在反向链接域中，如果用户键入一个 URL 或单击一个书签，则该反向链接域属性不存在。</li><li>**为空**：指定点击属性存在，通常为 eVar 或查询字符串参数，但没有任何与点击属性相关的值。</li><li>**不包含**：例如，您可以指定反向链接域不包含特定值（这与使用选项 &quot;包含&quot;.)</li></ul> |
| 将渠道识别为 | 将规则与您添加到“营销渠道管理器”页面上的营销渠道相关联。请参阅添加营销渠道。 |
| 匹配付费搜索检测规则 | Adobe 检测的付费搜索。付费搜索是指公司向列出它们网站的搜索引擎支付费用。付费搜索通常出现在搜索结果顶部或右侧。 |
| 匹配免费搜索检测规则 | Adobe 报表检测的免费搜索。 |
| 引用网站与内部 URL 筛选器匹配 | 按照“管理工具”中对报表包的定义，页面 URL 与内部 URL 筛选器匹配的访问。 |
| 引用网站与内部 URL 筛选器不匹配 | 按照“管理工具”中对报表包的定义，引用 URL 与内部 URL 筛选器不匹配。您可以将此设置与“页面 URL”和“存在”一起使用来设置一个通用规则，这样就不会有访问登陆报表中的未识别渠道区域。 |
| 忽略与内部 URL 过滤器匹配的点击量 | （关于反向链接）只跟踪来自外部引用网站的点击量。通常，将此设置保留为启用状态，除非您希望包括内部流量。 |
| 是访问第一页 | Adobe 报表检测到的访问第一页。 |
| 页面 | 网站上使用 Adobe 网络信标标记的网页名称。该值等同于 s.pageName。示例包括 `Home Page` 和 `About Us`。 |
| 页面域 | 访客所登陆页面的域，如 `products.example.co.uk`。 |
| 页面域和路径 | The domain and path, such as `products.example.co.uk/mens/pants/overview.html` . |
| 页面根目录域 (TLD+1) | 访客所登陆页面的根目录域，如 example.co.uk。 |
| 页面 URL | 网站上网页的 URL。 |
| 反向链接域 | 访客访问您的网站之前来自的域，例如反向链接来自 `abcsite.com` 和 `xyzsite.com`。 |
| 查询字符串参数 | If a page URL on your site looks like `https://example.com/?page=12345&cat=1`, then page and cat are both query string parameters. (请参阅 `https://en.wikipedia.org/wiki/Query_string`.)  您只可为每个规则集指定一个查询字符串参数。To add additional query string parameters, use `ANY` as your operator, then add new query string parameters to the rule. |
| 反向链接 | 访客在访问您的网站前所在的网页位置（完整的 URL）。反向链接存在于所定义域的外部。 |
| 引荐域和路径 | 引荐域和 URL 路径的组合。示例包括：    `www.example.com/products/id/12345` 或 `ad.example.com/foo` |
| 引荐参数 | 反向链接 URL 上的查询字符串参数。例如，如果您的访客来自 `example.com/?page=12345&cat=1`，则 page 和 cat 为引荐参数。 |
| 引荐根目录域 | 引荐的根目录域。反向链接存在于所定义域的外部。 |
| 搜索引擎 | Google 或 Yahoo! 等引导访客进入您网站的搜索引擎。 |
| 搜索关键词 | 用于在搜索引擎上执行搜索的单词。 |
| 搜索引擎 + 关键词 | 唯一识别搜索引擎的搜索关键词和搜索引擎组合。例如，如果您搜索 computer 这个词，搜索引擎和关键词识别如下： `Search Tracking Code = "<search_type>:<search engine>:<search keyword>" where    search_type = "n" or "p", search_engine = "Google", and search_keyword = "computer"`**注意：**n = 免费；p = 付费 |
| 将渠道值设置为 | 除了解哪些营销渠道为网站带来访客外，您还可以知道访客的网站活动应归功渠道中哪些横幅广告、搜索关键词或电子邮件促销活动。此 ID 是一个与渠道一起存储的渠道值。通常此值为嵌入在登陆页或反向链接 URL 中的促销活动 ID；在其他情况下，它是搜索引擎和搜索关键词的组合，或是准确从特定渠道中识别访客的反向链接 URL。 |

## 内部（会话刷新）渠道

内部渠道（通常又称为“会话刷新”）由对网站的访问组成，这些访问的反向链接 URL 与在 Admin Console 中设置的内部 URL 过滤器相匹配，这意味着访客从网站内部开始其访问。

![](assets/int-channel1.png)

### 覆盖最佳实践

最好取消选中“直接”和“内部”渠道的覆盖最近联系选项，以便这些渠道不能从其他持久保留的最近联系渠道获得点数（或相互获得点数）。

>[!NOTE] 本文档假定“直接”和“会话刷新”已取消选中覆盖设置。

![](assets/int-channel2.png)

### 参与期

访客的首次联系和最近联系渠道在该浏览器上处于非活动状态 30 天后会进行重置。

>[!NOTE] 30 天是默认设置，可根据需要通过“管理员”设置进行修改。

如果访客频繁使用网站，则参与窗口将随着这些访问渠道一起滚动。渠道必须处于非活动状态 30 天后，该期限才会到期，并且渠道才会重置。示例：

* 第 1 天：用户通过“显示”访问网站。首次联系和最近联系渠道将设置为“显示”。

* 第 2 天：用户通过“免费搜索”访问网站。首次联系仍为“显示”，最近联系将设置为“免费搜索”。

* 第 35 天：用户已经 33 天没有访问过该网站，现在使用他们在浏览器中打开的选项卡重新访问该网站。假设参与期为 30 天，此时，该窗口将关闭，并且营销渠道 Cookie 将过期。由于用户来自内部 URL，因此首次联系和最近联系渠道将被重置，并且都将设置为“会话刷新”。

### 首次联系与最近联系之间的关系

要了解首次联系与最近联系之间的交互情况，并确认是否可以按预期进行覆盖，您可以提取与最近联系渠道报表相关的首次联系渠道报表，并在其中添加关键成功量度（请参阅下面的示例）。该示例展示了首次联系与最近联系渠道之间的交互情况。

![](assets/int-channel3.png)

首次联系等于最近联系的相交区域以橙色突出显示。只有同时作为首次联系渠道时，“直接”和“会话刷新”才能获得最近联系点数，因为它们不能从其他持久保留的渠道（以灰色突出显示的行）获得点数。

### 为什么会出现会话刷新？

我们知道，仅当最近联系会话刷新也是首次联系渠道时，才会出现最近联系会话刷新，因此，以下场景解释了会话刷新如何成为首次联系渠道。

**场景 1：会话超时**

访客访问网站，然后在浏览器中保持打开选项卡，以备日后使用。访客的参与期到期（或访客主动删除其 Cookie），他们使用打开的选项卡再次访问网站。由于反向链接 URL 是内部域，访问将被分类为“会话刷新”。

**场景 2：并非所有网站页面都已标记**

访客登陆未标记的页面 A，然后移至已标记的页面 B。页面 A 将被视为内部反向链接，并且该访问将被分类为“会话刷新”。

**场景 3：重定向**

如果未将重定向设置为将反向链接数据传递到新登陆页面，则真正的登入反向链接数据将会丢失，并且此时重定向页面（可能是内部页面）将显示为反向链接域。该访问将被分类为“会话刷新”。

**场景 4：跨域流量**

访客从一个触发包 A 的域移动到另一个触发包 B 的域。如果在包 B 中，内部 URL 过滤器包括第一个域，则包 B 中的访问将被记录为内部访问，因为营销渠道将其视为第二个包中的新访问。该访问将被分类为“会话刷新”。

**场景 5：登入页面加载时间较长**

访客登陆具有大量内容的页面 A，且 Adobe Analytics 代码位于页面底部。在加载所有内容（包括 Adobe Analytics 图像请求）之前，访客单击了页面 B。页面 B 触发其 Adobe Analytics 图像请求。由于页面 A 的图像请求从未加载，因此在 Adobe Analytics 中，第二个页面将显示为访问的首次点击，而页面 A 将作为反向链接。该访问将被分类为“会话刷新”。

**场景 6：在访问网站期间清除 Cookie**

访客访问网站，并在会话期间清除了其 Cookie。此时，首次联系和最近联系渠道都将重置，并且访问将被分类为“会话刷新”（因为反向链接将是内部链接）。
