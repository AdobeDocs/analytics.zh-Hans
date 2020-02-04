---
title: 使用AMP实施
description: 在AMP页面上实施Adobe Analytics。
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# 使用AMP实施

[AMP](https://amp.dev) 是一个开放源HTML框架，它提供了创建快速、顺畅加载网页的直接方法。

由于Adobe Analytics使用JavaScript库编译和发送图像请求，因此实施过程中需要进行调整，才能使用AMP将数据发送到页面上的Adobe。

## 确定在使用AMP的页面上实施Adobe Analytics的方法

Adobe已创建两种方法来使用AMP在页面上实施Adobe Analytics。 二者都使用 `<amp-analytics>` HTML标记。 有关 [详细信息，请参阅ampproject GitHub上的amp](https://github.com/ampproject/amphtml/tree/master/extensions/amp-analytics) -analytics标签。

* **使用跟`"adobeanalytics"`踪模板**:直接在页面上构建Analytics请求
* **使用跟`"analytics_nativeConfig"`踪模板**:使用包含您在普通站点上部署的相同AppMeasurement代码的iframe

下表比较了这两种方法：

|  | **adobeanalytics 模板** | **adobeanalytics_nativeConfig 模板** |
|---|---|---|
| 现有报表包中的访客／访问计数 | 虚增较高 | 虚增极低 |
| 使用单独的报告套件 | 推荐 | 不需要 |
| 新访客与回访者的对比 | 不受支持 | 受支持 |
| 访客 ID 服务 | 不受支持 | 受支持 |
| 视频和链接跟踪 | 部分支持 | 尚不支持 |
| 实施难度 | 有些困难 | 相对简单 |
| Adobe Experience cloud集成 | 不受支持 | 部分支持 |

权衡组织内的利弊，确定要使用的方法。 有关 [示例代码](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web) ，请参阅Adobe GitHub存储库上的AMP示例。

> [!WARNING] 请勿使用AMP在同 `"adobeanalytics"` 一页 `"adobeanalytics_nativeConfig"` 面上同时使用和模板。 如果尝试这样做，您可以在浏览器控制台中生成错误，并将访客数加倍。

## 方法1:将amp-analytics标记与“adobeanalytics”模板一起使用

The `"adobeanalytics"` tracking template uses the `<amp-analytics>` HTML tag to construct a tracking request directly. 您可以指定在特定页面事件（如页面可见或单击时）触发的点击请求。 通过指定一个选择器，可自定义若干个单击事件，以应用到某些元素 ID 或类中。将 `type="adobeanalytics"` 添加至 amp-analytics 标记后，即可加载该模板。

在下列代码示例中，定义了两个触发程序：`pageLoad` 和 `click`。当文 `pageLoad` 档变为可见时，触发器将触发，并包 `pageName` 括在部分中定义的变 `vars` 量。 The second trigger `click` fires when a button is clicked. `eVar1` 为此事件设置值 `button clicked`。

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.sc.omtrdc.net",
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

In the `click` trigger, you can specify a selector to ensure that whenever the specific DOM element is clicked (in this case, any button), the `buttonClick` request is fired and is automatically set to denote this hit as a link tracking call.

此外，`amp-analytics` 支持若干变量替换，因此 AMP 能够提供它感知到的数据值。有关 [详细信息，请参阅GitHub上的amp-analytics](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) 中支持的变量。

> [!NOTE] 使用此方法发送到Adobe的图像请求不包括许多默认报告（例如，浏览器、屏幕大小或引用）的数据。 如果要在点击中包含此信息，请确保这些信息作为图像请求查询字符串的一部分包含在内。 有关详细信息，请参阅[数据收集查询参数](../validate/query-parameters.md)。

Adobe使用内置的AMP功能识别访客，并设置Cookie `adobe_amp_id`。 此访客ID对于Adobe Analytics设置的任何其他ID(例如 `s_vi` cookie)是唯一的。 使用此实施方法不支持Adobe Experience Cloud ID服务。

> [!NOTE] AMP使用CDN交付内容。 其结构化为计数访客从中检索内容的每个CDN的不同唯一访客，这会夸大唯一访客数。

由于AMP如何识别唯一访客，因此建议对AMP页面使用单独的报表包。

This solution requires that the tracking server you specify in the `host` property matches the tracking server on your main site, so that your existing privacy policy controls are respected. 否则，请使用AMP为页面创建单独的隐私策略。

## 方法2:将amp-analytics标记与“adobeanalytics_nativeConfig”模板一起使用

The `"adobeanalytics_nativeConfig"` tag is easier to implement, as it uses the same tagging methodology you use on your normal web pages. 在标记中添加以下 `amp-analytics` 内容：

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.sc.omtrdc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

还需要在Web服务器上托管的HTML页面：

```html
<html>
  <head>
    <title>Stats Example</title>
    <script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script>
    <script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid";
      var s_trackingServer = "example.sc.omtrdc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;
      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitorNamespace = s_visitorNamespace;
      s.visitor = visitor;
      s.pageName = s.Util.getQueryParam("pageName");
      s.eVar1 = s.Util.getQueryParam("v1");
      s.campaign = s.Util.getQueryParam("campaign");
      s.pageURL = s.Util.getQueryParam("pageURL");
      s.referrer = s.Util.getQueryParam("ref");
      s.t();
    </script>
  </body>
</html>
```

This approach sends data to a utility web page through query string parameters added to the `iframeMessage` request parameter. These query string parameters can be named whatever you like, as long as your `stats.html` page is configured to collect data from them.

`"adobeanalytics_nativeConfig"` 模板还能基于 amp-analytics 标记的 `extraUrlParams` 部分中列出的变量，添加查询字符串参数。在上例中，包括 `pageName` 和 `v1` 参数。

> [!IMPORTANT] 您 `stats.html` 的页面必须托管在与AMP本身托管的域不同的子域上。 AMP 框架不允许 iFrame 来自 AMP 页面本身所在的子域。例如，如果AMP托管在上， `amp.example.com`则将页面托 `stats.html` 管在单独的子域(如 `ampmetrics.example.com`)。

使用此方法，如果用户在主站点上退出跟踪，则他们也会选择不在所有AMP上进行跟踪。 使用此实用程序页面也意味着AMP可以支持Adobe Experience Cloud ID服务。 不需要单独的报告套件。

链接跟踪和视频跟踪不能与此方法一起使用。 AMP `iframeMessage` 中的标记每页只能加载一次，因此在加载帧后，您无法发送任何其他图像请求。 此方法还需要更多处理资源来运行，这会影响滚动性能。 此方法不会影响页面加载时间，因为所有资源都以异步方式加载。

## 常见问题解答

**视频跟踪是否可用于任一方法？**

不会。AMP标准仅支持“visible”、“click”和“timer”的触发器。 它尚不支持标签可监听的视频跟踪显 `amp-analytics` 式触发器。 此外，模 `"adobeanalytics_nativeConfig"` 板只能加载一次，因此在页面加载后无法进行后续图像请求。

**如何在我的数据中区分AMP访客和其他访客？**

对于所有AMP页面， [!UICONTROL JavaScript版本维度会收集一个类似于的值]`AMP vX.X`。 您还可以将自定义维度设置为“AMP”，以便对这些访客进行细分。

**此实施方法与Facebook Instant Articles相比如何？**

Facebook Instant Articles支持与方法类似的解决 `"adobeanalytics_nativeConfig"` 方案。 此方 `stats.html` 法的页面可同时满足您对AMP和FIA的分析需求。 有关在FIA上实施跟踪的更多信息，请参 [阅Facebook Instant Articles](fb-instant-articles.md)。
