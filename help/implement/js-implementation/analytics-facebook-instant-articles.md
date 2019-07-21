---
description: 如何在 Facebook Instant Articles 中实施分析。
keywords: Analytics实施；嵌入；自定义变量；自定义事件；访客跟踪；跟踪；限制
seo-description: 如何在 Facebook Instant Articles 中实施分析。
seo-title: Facebook Instant Articles（即时文章）
solution: Analytics
title: Facebook Instant Articles（即时文章）
topic: 开发人员和实施
uuid: 04b6366b-7c52-4ae-b2 dd-bb6 b78 fd409 c
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Facebook Instant Articles（即时文章）

如何在 Facebook Instant Articles 中实施分析。

Facebook Instant Articles 是发布者在 Facebook 中创建快捷、交互式文章的一种新方法。Instant Articles 的内容加载速度比移动网页快 10 倍。

可将 Adobe Analytics 嵌入到 Facebook Instant Articles 中，以便在访客与内容进行交互时跟踪访客的行为。由于发布者内容是在 Facebook 应用程序中，而不是在发布者的网站上，因此标记方法与 Analytics 标准实施的方法略有不同。

## 步骤 1. 嵌入 Analytics HTML 页面 {#section_0DF847F8BA624CF8A239C10003A39E59}

创建 Facebook Instant Articles 内容时，您可以在 iFrame 中嵌入 Analytics HTML 内容。例如：

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html" height="0"></iframe>
```

## 步骤 2. 修改 Analytics HTML {#section_76707B51D63A47FF833C2D3FFF8412B4}

下面的 HTML 示例可用于从 Instant Articles 中捕获统计数据。此文件通常会托管在贵公司的某台 Web 服务器中。每次加载 Instant Article 时，该文件都会像第一步描述的那样，在 iFrame 中加载文件，这会触发向 Adobe 发送分析数据。

```
<html> 
    <head> 
        <title>Facebook Stats</title> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/VisitorAPI.js"></script> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/AppMeasurement.js"></script> 
    </head> 
    <body> 
        <script> 
            //Standard Variable Configuration 
   var v_orgId = "[your-marketing-cloud-org-id]@AdobeOrg"; 
   var s_account = "[your-report-suite-id]"; 
   var s_trackingServer = "[your-tracking-server]"; 
   var s_visitorNamespace = "[your-namespace]"; 
     
   //Instantiation 
   var visitor = Visitor.getInstance(v_orgId); 
   visitor.trackingServer = s_trackingServer; 
     
   var s = s_gi(s_account); 
   s.account = s_account; 
   s.trackingServer = s_trackingServer; 
   s.visitorNamespace = s_visitorNamespace; 
   s.visitor = visitor; 
     
   //Custom Variables 
   s.pageName = s.Util.getQueryParam("pageName"); 
   s.prop10 = "Facebook Instant Article"; 
       
   //Page View Image Request Call 
   s.t(); 
        </script> 
    </body> 
</html> 
```

**为具体的实施修改此 HTML 示例**

1. 建议将未修改的 VisitorAPI.js 和 AppMeasurement.js 的最新副本托管到贵公司 Web 服务器的常用目录中。

   如果需要，也可以从 Analytics UI 中的代码管理器下载这些文件。

1. 将 Analytics 实施标准配置变量包含在内：

   1. 您的 Experience Cloud 组织 ID。
   1. 从中捕获 Facebook Instant Articles 流量的报表包 ID。
   1. 贵公司的跟踪服务器域。
   1. 您的访客命名空间变量。**注意：**&#x200B;大多数值都可以在 Analytics 标准实施的过程中找到。如果需要，客户关怀团队或 Adobe 咨询人员可以帮助提供适当的值。

1. [设置自定义变量和事件跟踪](../../implement/js-implementation/analytics-facebook-instant-articles.md#section_932C41BD21154C25B99389299BDF3E0B)。
1. Include the page view image request syntax `( s.t())`.

## 步骤 3. 设置自定义变量和事件跟踪 {#section_932C41BD21154C25B99389299BDF3E0B}

您可以通过不同的方法，在您的分析 HTML 中跟踪自定义变量和事件。第一种方法是在您的自定义配置中包含 JavaScript 逻辑，这与 Analytics 标准实施时采取的方法类似。例如，要设置 prop 的值，只需使用您在普通的实施中使用的相同的语法即可。

```
s.prop10 = "Facebook Instant Article";
```

您也可以利用 iFrame `src` 属性中的查询字符串参数，动态地将变量发送至 iFrame。例如：

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html?prop1=dynamic%20article%20title&eVar1=facebook%20page%20name&pageName=your%20page%20name%20here&cmpId=your%20campaignID%20here" height="0"></iframe>
```

您可以使用默认 库中的 `Util.getQueryParam`[!DNL AppMeasurement] 函数，随后在分析 HTML JavaScript 的自定义变量区段中设置这些查询字符串参数，如下所示：

```
s.pageName = s.Util.getQueryParam("pageName"); 
s.campaign = s.Util.getQueryParam("cmpId"); 
s.eVar1 = s.Util.getQueryParam("eVar1"); 
s.prop1 = s.Util.getQueryParam("prop1"); 
```

## 访客跟踪 {#section_60F0C77659534949831E85B5FD9AE81E}

只要 Analytics HTML 页面托管在您的 Web 服务器中，Adobe 就能够在所有 Facebook Instant Articles 中支持您现有的隐私政策。这就意味着如果最终用户选择不再跟踪您的主要站点，他们同时也就无法再跟踪您的任何 Facebook Instant Articles，无需执行其他步骤。使用此实用程序页面还意味着支持标识服务(访客ID)，以便您能够将Facebook Instant Articles上捕获的指标和变量与Experience Cloud的其余部分相集成。(An example is for targeted advertising using [!DNL Adobe Audience Manager]).

## 跟踪的局限性 {#section_1EE1BB069A3148DB9446371AFE196567}

关于这种方法，有些问题应该注意。对于一般只能通过 Facebook Instant Articles 中的 JavaScript 访问的任意 DOM 值（例如，反向链接）而言，都不能在用于跟踪的 iFrame 中获取。但是，标准技术报告，例如浏览器、设备、屏幕大小或分辨率，应该能够正常工作。另外，可以通过引用实用工具页面中的 [!DNL document.referrer] 获取 pageURL。

## What's Next? {#section_A170A10E2A3642A784DF720195DA8B38}

[!DNL Adobe Analytics] 很高兴能够与 Facebook、我们的发布者建立合作伙伴关系，为使用移动网页的发布者带来业界领先的分析能力，并实现速度惊人的用户体验。我们致力于打造最佳的长期解决方案，以满足客户不断变化的分析需求。

Facebook Instant Articles 项目发展迅速、变化频繁，因此请经常回访我们的网站以检查更新。我们将进一步改进我们的集成，而且将来会有更多的发布者采用 Facebook Instant Articles，这势必还会发生一些变化。

如有任何疑问或问题，请联系 Adobe 咨询人员或客户关怀团队。
