---
description: 变量及其限制概览。
keywords: Analytics实施；变量；限制；限制
seo-description: 变量及其限制概览。
seo-title: 变量和限制
solution: Analytics
subtopic: 变量
title: 变量和限制
topic: 开发人员和实施
uuid: 028677a7-2132-4ee7-9cc1-697c2c09b087
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 变量和限制

变量及其限制概览。

>[!NOTE]
>
>See [Configuration Variables](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00) and [Page Variables](../../../implement/js-implementation/c-variables/page-variables.md#concept_37933DFF2FC547A0A3B296D5E646B6A3) for an in-depth look at the most common Analytics variables.

下面的表格提供了有关 [!DNL Analytics] 变量的概览信息：

| 变量 | 描述 |
|---|---|
| s_account | 确定用于存储和报告数据的报表包。 |
| browserHeight | 显示浏览器窗口的高度。 |
| browserWidth | 显示浏览器窗口的宽度。 |
| campaign | 识别将访客吸引到您网站的营销活动。此&#x200B;*`campaign`*&#x200B;的值通常取自查询字符串参数。 |
| channel | 通常用于确定网站的某个区域。例如，某商家的网站可能设有电器、玩具或服装等区域。某个媒体网站可能设有新闻、体育或商业信息等区域。 |
| charSet | 将网页字符集转换为 UTF-8。 |
| colorDepth | 显示用于在屏幕的每个象素中显示颜色的位数。 |
| connectionType | 指示（在 Microsoft Internet Explorer 中）浏览器的配置是 LAN 还是调制解调器连接。 |
| cookieDomainPeriods | 通过确定页面 URL 中域名的句点数来确定将设置 [!DNL Analytics][!UICONTROL  访客 ID] (s_vi) Cookie 的域。For `www.mysite.com`, *`cookieDomainPeriods`* should be "2." For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3." |
| cookieLifetime | JavaScript 和 [!DNL Analytics] 服务器使用此变量来确定 Cookie 的有效期。 |
| cookiesEnabled | 指示第一方会话 Cookie 是否是通过 JavaScript 设置的。 |
| currencyCode | 确定收入进入 [!DNL Analytics] 数据库时应用的兑换率。[!DNL Analytics] 数据库以您所选择的货币存储所有货币额。If that currency is the same as that specified in *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied. |
| dc | 让您可以设置接收数据的数据中心。 |
| doPlugins | *`doPlugins`* 是 *`s_doPlugins`* 对函数的引用。It allows the *`s_doPlugins`* function to be called at the appropriate location within the JavaScript file. |
| dynamicAccountList | 动态选择接收发送数据的报表包。此&#x200B;*`dynamicAccountList`*&#x200B;变量包含用于确定目标报表包的规则。 |
| dynamicAccountMatch | 使用 DOM 对象检索&#x200B;*`dynamicAccountList`*&#x200B;中所有规则都适用的 URL 的区域。This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' |
| dynamicAccountSelection | 让您可以根据每个页面的 URL 动态选择报表包。 |
| dynamicVariablePrefix | 允许部署标记动态填充的变量。Cookie、请求头和图像查询字符串参数均适用于动态填充。 |
| eVarN | 用于生成 [!DNL Analytics][!UICONTROL  转化模块]中的自定义报表。为访客设置 eVar 值之后，[!DNL Analytics] 会自动记忆该值直到它过期。eVar 值有效期间，访客遇到的任何成功事件将计入该 eVar 值。 |
| events | 记录常见购物车成功事件和自定义成功事件。 |
| fpCookieDomainPeriods | 通过确定页面中域名的句点数来确定将设置 [!DNL Analytics] Cookie（而非[!UICONTROL 访客 ID] (s_vi) Cookie）的域。 |
| hierN | 确定页面在网站层级中的位置。该变量最适用于网站结构超过三层的网站。 |
| homepage | 指示（在 Internet Explorer 中）当前页面是否已被设置为用户的主页。 |
| javaEnabled | 指示 Java 是否已在浏览器中启用。 |
| javascriptVersion | 显示浏览器支持的 JavaScript 版本。 |
| linkDownloadFileTypes | 一种文件扩展名的逗号分隔列表。如果您网站上包含的链接可转到具有任何此类扩展名的文件，则这些链接的 URL 会显示在[!UICONTROL 文件下载]报表中。 |
| linkExternalFilters | 如果您的网站包含许多指向外部网站的链接，并且您不希望跟踪所有退出链接，则可使用&#x200B;*`linkExternalFilters`*&#x200B;报告退出链接的特定子集。 |
| linkInternalFilters | 确定网站上的哪些链接是退出链接。它是以逗号隔开的过滤器列表，显示属于网站一部分的链接。 |
| linkLeaveQueryString | 确定[!UICONTROL 退出链接]和[!UICONTROL 文件下载]报表中是否应包含查询字符串。 |
| linkName | 用于[!UICONTROL 链接跟踪]的可选变量，可确定自定义链接、下载链接或退出链接的名称。此&#x200B;*`linkName`* 通常不需要变量，因为 *`tl()`* 函数中的第三个参数替换它。 |
| linkTrackEvents | 包含应随自定义、下载和退出链接一起发送的事件。只有当&#x200B;*`linkTrackVars`*&#x200B;中包含“events”时才需考虑此变量。 |
| linkTrackVars | 一种将随自定义、退出和下载链接一起发送的变量的逗号分隔列表。如果&#x200B;*`linkTrackVars`*&#x200B;设置为 ""，则所有含值的变量都将随链接数据一起发送。 |
| linkType | 链接跟踪中使用的可选变量，可以确定要显示“链接名称”或 URL 的报表（自定义、下载或退出链接）。*`linkType`* 通常不需要，因为 *`tl()`* 函数中的第二个参数替换它。 |
| mediaLength | 指定正在播放的媒体的总长度。 |
| mediaName | 指定视频或媒体项目的名称。此变量只能通过[!UICONTROL 数据插入 API] 和[!UICONTROL 完全处理数据源]来使用。 |
| mediaPlayer | 指定用于播放视频或媒体项目的播放器。 |
| mediaSession | 指定所播放视频或媒体资产的区段。 |
| Media.trackEvents | 会确定点击媒体时应发送哪些事件。此变量仅适用于 JavaScript 和 [!UICONTROL ActionSource]。 |
| Media.trackVars | 确定点击媒体时应发送哪些变量。此变量仅适用于 JavaScript 和 [!UICONTROL ActionSource]。 |
| mobile | 控制使用 Cookie 和订户 id 确定访客的订单。 |
| s_objectID | 一种全局变量，应在链接的 [!UICONTROL onClick] 事件中设置。通过为链接或页面的链接位置创建唯一对象 ID，可改善访客点击图跟踪或使用访客点击图报告链接类型或位置，而非链接 URL。 |
| pageName | 包含网站中每个页面的名称。如果&#x200B;*`pageName`*&#x200B;为空，则在 [!DNL Analytics] 中使用 URL 表示页面名称。 |
| pageType | 仅用于指定 404（页面未找到）错误页面。该变量只有一个可能值：errorPage。在 404 错误页面上，*`pageName`*&#x200B;变量不应被填充。 |
| pageUrl | 在少数情况下，页面的 URL 不是您想在 [!DNL Analytics] 中报告的 URL。To accommodate these situations, [!DNL Analytics] offers the *`pageURL`* variable, which overrides the actual URL of the page. |
| 插件 | 在 Netscape 和基于 Mozilla 的浏览器上，列出浏览器中安装的插件。 |
| products | 用于跟踪产品和产品类别及购买数量和购买价格。The *`products`*&#x200B;变量应始终结合成功事件进行设置。Optionally, the *`products`* variable can track custom numeric and currency events, as well as [!UICONTROL Merchandising] eVars. |
| propN | 用于在 [!DNL Analytics][!UICONTROL  流量模块]中生成自定义报表。[!UICONTROL prop] 可用作计数器(计数页面查看的发送次数），在路径报表或关联报表中使用。 |
| purchaseID | 用于避免订单被 [!DNL Analytics] 计数多次。Whenever the purchase event is used on your site, you should use the *`purchaseID`* variable. |
| referrer | 还原丢失的反向链接信息。 |
| resolution | 显示访客用于查看网页的显示器分辨率。 |
| server | 显示网页的域（显示访客访问的域）或提供页面的服务器（用于快速了解负载平衡）。 |
| state | 捕获网站访客所在的州。 |
| trackDownloadLinks | 如果您想要跟踪那些指向网站上可下载文件的链接，请设置&#x200B;*`trackDownloadLinks`* 如果要跟踪站点上可下载文件的链接，则为“true”。If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* determines which links are downloadable files. |
| trackExternalLinks | If *`trackExternalLinks`* is 'true,' *`linkInternalFilters`* and *`linkExternalFilters`* determines whether any link clicked is an exit link. |
| trackingServer | 用于第一方 Cookie 实施，以指定写入图像请求和 Cookie 的域。用于非安全页面。 |
| trackingServerSecure | 用于第一方 Cookie 实施，以指定写入图像请求和 Cookie 的域。用于安全页面。 |
| trackInlineStats | 确定是否收集访客点击图数据。 |
| transactionID | 将离线数据关联至在线交易（如在线生成的商机或购买）。每个发送到 Adobe 的独特&#x200B;*`transactionID`*&#x200B;均会被记录，以备该交易离线信息的[!UICONTROL 数据源]上载。请参阅[数据源指南](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)。 |
| s_usePlugins | 如果&#x200B;*`s_doPlugins`* 函数可用并且包含有用的代码， [!UICONTROL s_ usePlugins] 应设置为“true”。[!UICONTROL 当usePlugins] 为“true”时， *`s_doPlugins`* 在每个图像请求之前调用函数。 |
| visitorID | Visitors may be identified by the *`visitorID`* tag, or by IP address/User Agent. The *`visitorID`* may be up to 100 alphanumeric characters and must not contain a hyphen. |
| visitorNamespace | If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. 该变量用于确定设置 Cookie 的域。如果更改&#x200B;*`visitorNamespace`*，则所有在 [!DNL Analytics] 中报告的访客都可能会变成新访客。简而言之，未经 Adobe 顾问批准不要更改此变量。 |
| zip | 捕获网站访客所在地的邮政编码。 |

