---
title: 使用 AMP 实施
description: 在 AMP 页面上实施 Adobe Analytics。
feature: Implementation Basics
exl-id: 51a2662e-2a24-48f1-b17a-d1e1a57a394b
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 70%

---

# 使用 AMP 实施

[AMP](https://amp.dev) 是一个开源 HTML 框架，为创建可快速且顺畅加载的网页提供了一种简单的方法。

由于 Adobe Analytics 使用 JavaScript 库编译和发送图像请求，因此需要在您的实施中进行一些调整，才能在使用 AMP 的页面上将数据发送到 Adobe。

## 确定在使用 AMP 的页面上实施 Adobe Analytics 的方法

Adobe 创建了两种在使用 AMP 的页面上实施 Adobe Analytics 的方法。这两种方法都使用 `<amp-analytics>` HTML 标记。有关详细信息，请参阅AMP文档中的[amp-analytics](https://amp.dev/documentation/components/amp-analytics)。

* **使用`"adobeanalytics"`模板**：直接在页面上构造Analytics请求
* **使用`"analytics_nativeConfig"`模板**：使用包含您在普通网站上部署的相同AppMeasurement代码的iframe

下表比较了这两种方法：

|   | **`"adobeanalytics"`模板** | **`"adobeanalytics_nativeConfig"`模板** |
|---|---|---|
| 现有报表包中的访客/访问计数 | 虚增较高 | 虚增极低 |
| 使用单独的报表包 | 建议 | 不需要 |
| 新访客与回访者的对比 | 不受支持 | 受支持 |
| 访客 ID 服务 | 不受支持 | 受支持 |
| 视频和链接跟踪 | 部分支持 | 尚不支持 |
| 实施难度 | 困难 | 相对简单 |
| Adobe Experience Cloud 集成 | 不受支持 | 部分支持 |

权衡利弊，以便您能够为组织选择最佳的实施方法。

>[!WARNING]
>
>请不要在同一个使用 AMP 的页面上同时使用 `"adobeanalytics"` 和 `"adobeanalytics_nativeConfig"` 模板。如果尝试这样做，浏览器控制台中可能会生成错误，并导致访客数加倍。

## 方法1：将`<amp-analytics>`标记与`"adobeanalytics"`模板一起使用

`"adobeanalytics"` 跟踪模板可利用 `<amp-analytics>` HTML 标记直接构建跟踪请求。您可以指定在发生特定页面事件（如页面可见或单击时）时触发的点击请求。通过指定一个选择器，可自定义若干个单击事件，以应用到某些元素 ID 或类中。将 `type="adobeanalytics"` 添加至 amp-analytics 标记后，即可加载该模板。

在下列代码示例中，定义了两个触发程序：`pageLoad` 和 `click`。当文档变为可见并包含在 `vars` 部分中定义的 `pageName` 变量时，`pageLoad` 触发程序将触发。第二个触发程序 `click` 在单击按钮时触发。为此事件设置了`eVar1`变量，其值为`button clicked`。

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.data.adobedc.net",
        "reportSuites": "reportSuiteID1,reportSuiteID2",
        "pageName": "Adobe Analytics Using amp-analytics tag"
      },
      "triggers": {
        "pageLoad": {
          "on": "visible",
          "request": "pageview"
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

`<amp-analytics>`标记支持变量替换，因此AMP能够提供它感知到的数据值。 有关详细信息，请参阅GitHub上`amp-analytics`[&#128279;](https://github.com/ampproject/amphtml/blob/main/extensions/amp-analytics/analytics-vars.md)支持的变量。

>[!NOTE]
>
>使用此方法发送到Adobe的图像请求不包含许多默认报表的数据（例如，浏览器、屏幕大小或反向链接）。 如果要在点击中包含此信息，请确保将这些信息作为图像请求查询字符串的一部分包含。 有关图像请求查询参数及其相关变量的完整列表，请参阅[数据收集查询参数](../validate/query-parameters.md)。

Adobe 使用内置的 AMP 函数识别访客，并设置 `adobe_amp_id` Cookie。此访客ID对于由Adobe Analytics设置的任何其他ID都是唯一的。 访客从中检索内容的每个CDN都会计入一个不同的独特访客，这可能会导致访客计数虚增。 由于AMP识别独特访客的方式，强烈建议对AMP页面使用单独的报表包。 不支持Adobe Experience Cloud ID服务。

此解决方案要求您在 `host` 属性中指定的跟踪服务器必须与您主站点上的跟踪服务器相同，以确保遵守您现有的隐私管控政策。否则，请为使用 AMP 的页面创建单独的隐私政策。

## 方法2：将`<amp-analytics>`标记与`"adobeanalytics_nativeConfig"`模板一起使用

`"adobeanalytics_nativeConfig"` 标记更容易实施，因为它使用的标记方法与您在普通网页上使用的方法相同。在 `amp-analytics` 标记中添加以下项：

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.data.adobedc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

还需要在 Web 服务器上托管的 HTML 页面：

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
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
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

这种方法会通过添加至 `iframeMessage` 请求参数的查询字符串参数，将数据发送至实用工具网页。这些查询字符串参数可以随意命名，只要将 `stats.html` 页面配置为从这些参数中收集数据即可。

`"adobeanalytics_nativeConfig"`模板还基于`<amp-analytics>`标记的`extraUrlParams`部分中列出的变量，添加了查询字符串参数。 上例中包含 `pageName` 和 `v1` 参数。

>[!IMPORTANT]
>
>必须将您的 `stats.html` 页面托管在不同于托管 AMP 的域的子域上。AMP 框架不允许 iFrame 来自 AMP 页面本身所在的子域。例如，如果 AMP 托管在 `amp.example.com` 上，则要将 `stats.html` 页面托管在不同的子域（如 `ampmetrics.example.com`）上。

使用此方法时，若用户在主站点上选择退出跟踪，也会在所有 AMP 页面上选择退出跟踪。使用此实用工具页面还意味着 AMP 可以支持 Adobe Experience Cloud ID 服务。无需使用单独的报表包。

此方法无法用于链接跟踪和视频跟踪。AMP 中的 `iframeMessage` 标记在每页上只能加载一次，因此在加载此框架后，您将无法发送任何其他图像请求。运行此方法还需要更多处理资源，这可能会影响滚动性能。此方法不会影响页面加载时间，因为所有资源均以异步方式加载。

## 常见问题解答

**如何区分我的数据中的 AMP 访客和其他访客？**

对于所有 AMP 页面，[!UICONTROL JavaScript 版本]维度会收集类似于 `AMP vX.X` 的值。您还可以将自定义维度设置为“AMP”，以便对这些访客进行分段。

**此实施方法与 Facebook Instant Articles 有何异同？**

Facebook Instant Articles 支持类似于 `"adobeanalytics_nativeConfig"` 方法的解决方案。在此方法中，`stats.html` 页面可同时满足您对 AMP 和 FIA 的分析需求。有关在 FIA 上实施跟踪的更多信息，请参阅 [Facebook Instant Articles](fb-instant-articles.md)。
