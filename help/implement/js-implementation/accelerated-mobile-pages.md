---
description: 在 Adobe Analytics 中实施“加速移动网页”(AMP) 项目。
keywords: Analytics Implementation;amp;amp-analytics;adobeanalytics template;adobeanalytics_nativeConfig template;click tracking;visitor inflation;id service
solution: Analytics
title: Accelerated Mobile Pages（“加速移动网页”项目）
topic: Developer and implementation
uuid: c86e4a80-7191-4ee7-ab20-787730026c4b
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Accelerated Mobile Pages（“加速移动网页”项目）

在 Adobe Analytics 中实施“加速移动网页”(AMP) 项目。

AMP 是一个[开源项目](https://www.ampproject.org/)，能够帮助您构建可快速呈现静态内容的网页。对于那些希望立即创建移动优化内容并快速在各处上载的发布者而言，此功能将是理想之选。主题包括：

* [工作原理](/help/implement/js-implementation/accelerated-mobile-pages.md#section_21C2836D63104794BCEBEECB6593AFBF)
* [将 amp-analytics 标记与“adobeanalytics”模板结合使用](/help/implement/js-implementation/accelerated-mobile-pages.md#section_2E4EBF4EF623440D95DE98E78C47244E)
* [将 amp-analytics 标记与“adobeanalytics_nativeConfig”模板结合使用](/help/implement/js-implementation/accelerated-mobile-pages.md#section_3556B68304A4492991F439885727E9FF)
* [概要](/help/implement/js-implementation/accelerated-mobile-pages.md#section_4D8ED26084F249738A5C2BC66B933A07)
* [常见问题解答](/help/implement/js-implementation/accelerated-mobile-pages.md#section_5F57AA2DE0C5452FB65241058A924C73)

**其他文档和示例**

* 外部开源 AMP 项目[文档](https://www.ampproject.org/docs/get_started/about-amp.html)
* 设置[示例](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml)

## 工作原理 {#section_21C2836D63104794BCEBEECB6593AFBF}

AMP 把一些经过特殊标记的 HTML 页面，缓存在参与此项目的技术合作伙伴和发布者设立的不同内容分发网络 (CDN) 中。这样就可以从距离最近的来源以最低的延迟分发 AMP 内容。不过，分析工作会为此迎来挑战，因为您永远无法百分百确定从哪儿加载发布者的内容，而且第三方 Cookie 也会给访客身份识别带来困难。

此外，为了大幅缩减页面数据量并提高页面加载速度，AMP 限制使用 JavaScript 和 Cookie。尽管这种做法有利于移动设备，但是由于数据处理量减少，这给准确测量独特访客数以及了解如何获取并留住用户带来了困难。

为了解决这些问题，Adobe 与 AMP 合作伙伴及发布者联合推出了两个选项（都用到了 `amp-analytics` 标记），发布者可从中选取最适合其业务需求的选项。第一种方法是使用 `"adobeanalytics"` 跟踪模板，直接从 AMP 内构建 Analytics 请求。第二种方法是使用 `"analytics_nativeConfig"` 跟踪模板，此跟踪模板会使用一个包含您在普通网站上部署的 AppMeasurement 代码的 iFrame。下表为您展示了两种方法各自的优缺点。

|  | **adobeanalytics 模板** | **adobeanalytics_nativeConfig 模板** |
|---|---|---|
| 访客/访问计数（在现有的报表包中） | 虚增较高 | 虚增极低 |
| 使用单独的报表包 | 推荐 | 不需要 |
| 新访客与回访者的对比 | 不受支持 | 受支持 |
| 访客 ID 服务 | 不受支持 | 受支持 |
| 视频与链接跟踪 | 部分支持 | 尚不支持 |
| 实施难度 | 有些困难 | 相对简单 |
| [!DNL Experience Cloud] 集成 | 不受支持 | 受支持，但有注意事项 |

## 将 amp-analytics 标记与“adobeanalytics”模板结合使用 {#section_2E4EBF4EF623440D95DE98E78C47244E}

`"adobeanalytics"` 跟踪模板可利用 `amp-analytics` 标记直接构建跟踪请求。在 `"adobeanalytics"` 标记中使用 `amp-analytics` 模板，您可以指定能够触发特定页面事件的点击请求，例如当页面变得可见或单击时触发（将来可以触发视频查看等）。通过指定一个选择器，可自定义若干个单击事件，以应用到某些元素 ID 或类中。通过使用专为 `"adobeanalytics"` 设计的 [!DNL Adobe Analytics] 模板，Adobe 可轻松进行设置。将 `type="adobeanalytics"` 添加至 amp-analytics 标记后，即可加载该模板。

在下列代码示例中，定义了两个触发程序：`pageLoad` 和 `click`。触发器 `pageLoad` 将在文档变得可见时触发，而且它将把 `pageName` 变量作为已定义的变量包含在 `vars section` 中。第二个触发程序 `click` 会在单击按钮时触发。对于此事件，`eVar 1` 将被设置为值 `button clicked`。

```
  <amp-analytics type="adobeanalytics"> 
  <script type="application/json"> 
  { 
        "requests": { 
      "myClick": "${click}&v1=${eVar1}", 
  }, 
  "vars": { 
      "host": "metrics.example.com", 
      "reportSuites": "reportSuiteID", 
      "pageName": "Adobe Analytics Using amp-analytics tag" 
  }, 
    "triggers": { 
      "pageLoad": { 
        "on": "visible", 
        "request": "pageView" 
      }, 
      "click": { 
        "on": "click", 
        "selector": "button", 
        "request": "myClick", 
        "vars": { 
          "eVar1": "button clicked" 
        } 
      } 
    } 
  } 
  </script> 
  </amp-analytics> 
```

在 `click` 触发程序中，您可以指定一个选择器，以确保无论何时单击特定的 DOM 元素（在本例中是单击任意按钮），都会触发 `buttonClick` 请求，且经过自动设置后，将此点击表示为非过渡事件（例如，`trackLink` 调用）。

此外，`amp-analytics` 支持若干变量替换，因此 AMP 能够提供它感知到的数据值。更多信息，请访问 [amp-analytics 变量文档](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md)。

请注意，如果您要整合任何技术或 DOM 变量（例如，浏览器、屏幕大小、设备、反向链接，等等），则必须显式地将它们添加到任意请求中，因为它们无法自动生成。您可以在[此处](https://marketing.adobe.com/resources/help/en_US/sc/implement/query_parameters.html)找到用于跟踪的各个查询字符串参数的文档。

如果您查看由 amp-analytics 创建的点击事件，会发现在各个请求中，Adobe 都已经包含了 `vid` 查询参数。我们基于内建的 AMP 函数来设置 `vid`，以设置一个名为 `adobe_amp_id` 的自定义 Analytics Cookie ID。此 ID 独立于 [!DNL Adobe Analytics] 在其他地方设置的任何其他 ID（例如，`s_vi cookie`），并且会在接收点击事件的任意报表包中创建新访客。

下面是一些需要注意的事项。如上所述，使用 amp-analytics 标记时，访客将独立于普通的跟踪，而且由于可从任意内容分发网络加载 AMP，因此访客在任意一个 CDN 中查看此 AMP 后，您都将获得一个独特访客（鉴于之前提到的访客虚增）。因此 Adobe 建议，如果您要将 `"adobeanalytics"` 与 `amp-analytics` 模板结合使用，可将数据放入特定于 AMP 的单独报表包中。此外，[!DNL Experience Cloud] ID 服务（以前称为 *`visitor ID service`*）不支持使用此方法，因此如果您的业务现在或将来需要其他的 [!DNL Experience Cloud] 集成，那么可能并不适合采用这种选项。

最后，同时也是最重要的，此 `amp-analytics` 解决方案要求您在 `vars` 区段指定的跟踪服务器必须与您主站点上的跟踪服务器相同，以确保遵守您现有的隐私政策控制。否则，您必须专门为 AMP 创建单独的隐私政策。

## 将 amp-analytics 标记与“adobeanalytics_nativeConfig”模板结合使用 {#section_3556B68304A4492991F439885727E9FF}

`"adobeanalytics_nativeConfig"` 标记更容易实施，因为它使用的标记方法与您在普通网页上使用的方法相同。要完成此操作，请将下列内容添加至您的 `amp-analytics` 标记中：

```
<amp-analytics type="adobeanalytics_nativeConfig"> 
 <script type="application/json"> 
 { 
  "requests": { 
   "base": "https://${host}", 
   "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}" 
  }, 
  "vars": { 
   "host": "statshost.publishersite.com" 
  }, 
  "extraUrlParams": { 
   "pageName": "Adobe Analytics Using amp-analytics tag", 
   "v1": "eVar1 test value" 
  } 
 } 
 </script> 
</amp-analytics>  
```

这种方法会通过添加至 `iframeMessage` 请求参数的特别查询字符串参数，将数据发送至实用工具网页。在本例中，请注意我们已经将 `ampdocUrl AMP` 变量和 `documentReferrer` 添加至查询字符串参数 `pageURL`，并与上述 `iframeMessage` 请求一一对应。其他查询字符串参数可以随意命名，只要将 [!DNL stats.html] 页面（如下所示）配置为从这些参数中收集合适的数据即可。

`"adobeanalytics_nativeConfig"` 模板还能基于 amp-analytics 标记的 `extraUrlParams` 部分中列出的变量，添加查询字符串参数。在本例中，您可以看到我们已经指定了 `pageName` 和 `v1` 参数，它们将被我们的 [!DNL stats.html] 页面使用。

请注意，您每次只能使用一个 `amp-analytics` 模板，不能在同一个 AMP 中既使用 `"adobeanalytics"` 模板，又使用 `"adobeanalytics_nativeConfig"` 模板。如果您试图这样做，则可能会在浏览器控制台中看到错误消息，并造成访客数量虚增。

```
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
</head> 
<body> 
<script> 
var v_orgId = "1234567@PublisherOrg"; 
var s_account = "reportSuite"; 
var s_trackingServer = "metrics.publisher.com"; 
var s_visitorNamespace = "publisherNamespace"; 
var visitor = Visitor.getInstance(v_orgId); 
visitor.trackingServer = s_trackingServer; 
var s = s_gi(s_account); 
s.account = s_account; 
s.trackingServer = s_trackingServer; 
s.visitorNamespace = s_visitorNamespace; 
s.visitor = visitor; 
s.pagename = s.Util.getQueryParam("pageName"); 
s.eVar1=s.Util.getQueryParam("v1"); 
s.campaign=s.Util.getQueryParam("campaign"); 
s.pageURL=s.Util.getQueryParam("pageURL"); 
s.referrer=s.Util.getQueryParam("ref"); 
s.t(); 
</script> 
</body> 
</html> 
```

如上所示，您可以使用或链接至您现有的 [!DNL VisitorAPI.js] 和 [!DNL AppMeasurement.js]（如我们的示例中所示），或者您现有的实施所使用的任何脚本文件，然后添加正确的配置参数。要将正确的值捕获到正确的变量中，您可以使用提供的 `s.Util.getQueryParam` 函数来获取您从 `iframeMessage` URL 传入的值，并设置合适的变量，就像您在常规页面中的操作一样。If you use tag management software like Adobe's [ [!DNL Dynamic Tag Manager] ](https://www.adobe.com/solutions/digital-marketing/dynamic-tag-management.html), the query string parameters should be straightforward to capture. 在本例中，`s.pageName` 被设置为我们传入查询字符串参数 `pageName` 的值。在这里，我们将页面名称设置为 *`Adobe Analytics Example 2`*。

>[!IMPORTANT]
>
>由于对 AMP 框架中的 iFrame 存在限制，所以必须将您的 [!DNL stats.html] 页面托管到 AMP 本身所托管的域之外的子域中。AMP 框架不允许 iFrame 来自 AMP 页面本身所在的子域。例如，如果您的 AMP 托管在 [!DNL amp.example.com]，请务必将您的 [!DNL stats.html] 页面托管到其他子域中，例如 [!DNL ampmetrics.example.com] 或类似的子域。

由于实用工具页面托管在您的初始站点中，因此无需额外的操作，即可在所有 AMP 中支持您现有的隐私政策。这就意味着如果最终用户选择不再跟踪您的主要站点，他们同时也就无法再跟踪您的任何 AMP，这无需执行其他步骤。使用此实用工具页面还意味着 AMP 能够支持 Adobe 的 [!DNL Experience Cloud] ID 服务，这样您就能够将您在 AMP 中捕获的测量数据集成到 [!DNL Experience Cloud] 的其他部分（例如，使用 [!DNL Adobe Audience Manager] 的定位广告）。

重申一遍，如果贵组织尚未使用 [!DNL Experience Cloud] ID 服务（或者拥有类似于 Adobe [!DNL Dynamic Tag Manager] 的标签管理软件），那么您可以随意标记 [!DNL stats.html] 页面。将您现有的实施作为参考点。与标准实施唯一的不同在于，您将从 amp-analytics `iframeMessage` URL（或者 [!DNL document.URL] 页面中的 [!DNL stats.html]）为您要设置的各个变量获取适用的数据点。此外，如果您要使用任何[特定于 AMP 的变量](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md)（如上所述），例如 AMP 反向链接或 AMP 页面 URL，请像上述示例中展示的一样，将这些变量包含在 iframeMessage 对象中。

尽管这个解决方案非常灵活，但也有一些注意事项。由于 `amp-analytics``iframeMessage`   的内在限制，只能在页面加载时加载一次。这意味着无法使用 `"adobeanalytics_nativeConfig"` 模板进行链接跟踪或视频跟踪。与此同时，有一些 DOM 值通常是由我们的 [!DNL AppMeasurement] 代码自动捕获的，例如 `referrer`（这会影响搜索引擎关键词报告、反向链接和反向链接类型报告，或者可能包含营销活动跟踪代码），但必须使用任何`iframeMessage`可用[￼的·AMP·变量手动传递至·](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md)￼。因此，如果要将 AMP 数据放入现有的报表包，Adobe 则建议设置一个值为 AMP 的自定义变量，这样您就可以在查看上述报表时对 AMP 流量进行分段。尽管如此，浏览器、设备、屏幕大小或分辨率等标准技术报告应该能够自动工作。

最后，由于 iFrame 会作为一个单独的页面进行加载，而且会在该页面上充分执行 JavaScript，因此 AMP 包含的数据量不像 AMP 标准预期的那样少。要说明的是，这并不会影响页面加载时间（iFrame 会在完成页面加载后进行加载），但是 CPU 和网络的工作量会稍微多一些，因此可能会影响页面滚动的流畅性。在实际操作中没有很大影响，不过我们正在与 Google 合作，希望能够最大限度地降低这种方法对用户体验的影响。

## 概要 {#section_4D8ED26084F249738A5C2BC66B933A07}

如果您需要跟踪点击事件，而且不介意将访客计为网站外全新的访客，请使用 `"adobeanalytics"` 跟踪模板，而且我们建议您将数据放入 *`separate report suite`*。如果您需要使用 [!DNL Experience Cloud] ID 服务，但不希望访客或访问次数出现虚增，而且您同意仅在页面加载时触发 Analytics，那么我们建议您使用 `"adobeanalytics_nativeConfig"` 解决方案。

Adobe Analytics 很高兴能够与 Google、我们的发布者建立合作伙伴关系，为移动网页的发布者带来业界领先的分析能力，并实现速度惊人的用户体验。尽管这两种解决方案目前都各有取舍，但是我们仍然致力于打造最佳的长期解决方案，以满足客户不断变化的分析需求。

AMP 项目发展迅速、变化频繁，因此请经常回访[此处](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml)以检查示例更新。对于入门而言，我们在本文中介绍的信息应该已经足够了，然而随着我们进一步改进我们的集成，而且逐渐会有更多的发布者采用 AMP，这势必还会发生一些变化。

如有任何疑问或问题，请联系 Adobe 咨询人员或客户关怀团队。

## 常见问题解答 {#section_5F57AA2DE0C5452FB65241058A924C73}

<table id="table_9A2ED5E482E8423CB54F99613C04BEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Is video tracking available for either the <code> "adobeanalytics" </code> or <code> "adobeanalytics_nativeConfig" </code> template? </p> </td> 
   <td colname="col2"> <p> 很遗憾，尚不可用。AMP 标准仅支持适用于“可见”、“单击”和“计时器”的触发程序，尚不支持能够被 amp-analytics 标记监听的用于视频跟踪的显式触发程序。Also, because the <code> "adobeanalytics_nativeConfig" </code> tag can only be loaded once, it is not compatible with video viewing which occurs after the AMP has loaded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>您提到相比之下，“<code> adobeanalytics_nativeConfig </code>”模板的访客虚增较低。这是什么意思？What would cause visitor inflation in either the <code> "adobeanalytics" </code> or the <code> "adobeanalytics_nativeConfig" </code> solution? </p> </td> 
   <td colname="col2"> <p>The <code> "adobeanalytics" </code> template does not allow Adobe Analytics to set a visitor identification cookie; this means all visits and visitors to your AMP page will be treated as a new and independent visit and visitor in your report suite. </p> <p>The <code> "adobeanalytics_nativeConfig" </code> template, however, allows the Adobe Analytics visitor identification cookie to be set in nearly all cases, except for new visitors using the Safari browser. 这意味着，Safari的任何以前未访问过出版商站点的访客在Adobe Analytics报告中将被夸大。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我是否应该为 AMP 使用单独的报表包？ </p> </td> 
   <td colname="col2"> <p>如果您要使用 adobeanalytics 模板，那么鉴于存在访客/访问次数虚增的问题，我们建议您为 AMP 使用单独的报表包。但是，我们还会在 amp-analytics 标记模板中将 JavaScript 版本设置为“AMP vX.X”，这样您就可以在必要时，将这部分流量从合并的报表包中分割出去。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="keyword">Experience Cloud</span> ID 服务是什么？我需要这项服务吗？ </p> </td> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/"  >Identity Service</a>（以前称为 <span class="term"> 访客 ID 服务</span>）启用了 <span class="keyword">Experience Cloud</span> 核心服务，并允许不同 Adobe <span class="keyword">Experience Cloud </span> 解决方案集成之间的集成。如果您集成了 <span class="keyword">Adobe 受众管理器</span>或 <span class="keyword">Adobe Target</span>，那么您可以使用此服务。此服务也是众多即将推出的 <span class="keyword">Adobe Analytics</span> 功能的基础。如果您现在或将来需要 ID 服务支持，我们建议您使用 <code> iframeMessage </code> 解决方案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>For the <code> "adobeanalytics_nativeConfig" </code> template, where should I host my utility page? </p> </td> 
   <td colname="col2"> <p>AMP 标准不允许 iFrame 从 AMP 本身所在的域和子域加载。因此，我们建议您将实用工具页面托管到主站点之外的子域，特别是如果您的公司拥有自己的计划用于缓存 AMP 的 CDN。为了实现最大的兼容，请选择 AMP 内容所在的地方之外的子域，例如 <span class="filepath">ampmetrics.publisher.com</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>这是不是类似于 <span class="keyword">Facebook Instant Articles</span>？我该如何在 Facebook Instant Articles 中设置 <span class="keyword">Adobe Analytics</span>？ </p> </td> 
   <td colname="col2"> <p> Facebook Instant Articles 支持一种与上述 nativeConfig 解决方案类似的解决方案。事实上，上面创建的 stats.html 页面能够同时满足对 AMP 和 FIA 的分析需求。有关在 FIA 中实施跟踪的更多信息，请参阅： <a href="/help/implement/js-implementation/analytics-facebook-instant-articles.md"  > Facebook Instant Articles（即时文章） </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

