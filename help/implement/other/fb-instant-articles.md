---
title: 使用Facebook Instant Articles实施
description: 在Facebook即时文章页面上实施Adobe Analytics。
translation-type: tm+mt
source-git-commit: 9d2007bead6a4963022f8ea884169802b1c002ff

---


# 使用Facebook Instant Articles实施

Facebook Instant Articles允许发布者在Facebook上构建快速的交互式文章。 Instant Articles 的内容加载速度比移动网页快 10 倍。

您可以将Adobe Analytics嵌入到Facebook Instant Articles中以跟踪访客行为。 由于发布者内容位于Facebook应用程序内，而不在发布者的网站上，因此标记方法与标准Analytics实施略有不同。

## 工作流

实施Adobe Analytics的总体工作流程如下：

1. 创建页 `stats.html` 面。 编码此页可从URL中提取查询字符串参数，并将每个参数分配给Analytics变量
1. 在Web服 `stats.html` 务器上托管页面
1. 通过引用iframe中的文件在Facebook即时文章上实 `stats.html` 施分析
1. 在iframe属性中包含查询字符串参 `src` 数

### 第1步：创建页 `stats.html` 面

下面的 HTML 示例可用于从 Instant Articles 中捕获统计数据。此文件通常会托管在贵公司的某台 Web 服务器中。每次加载即时文章时，它都会将文件加载到iframe中，这会触发向Adobe发送数据。

```html
<html>
  <head>
    <title>Facebook Stats</title>
      <script language="javaScript" type="text/javascript" src="VisitorAPI.js"></script>
      <script language="javaScript" type="text/javascript" src="AppMeasurement.js"></script>
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
      s.visitor = visitor;

      s.pageName = s.Util.getQueryParam("pageName");
      s.pageURL = document.referrer; // The referrer to the utility page is the parent frame
      s.campaign = s.Util.getQueryParam("cmpId");
      s.eVar1 = "Facebook Instant Article";
      s.eVar2 = s.Util.getQueryParam("eVar2");

      s.t();
    </script>
  </body>
</html>
```

### 第2步：在Web服 `stats.html` 务器上托管页面

Adobe建议将您的页 `stats.html` 面与最新版本的和一起 `AppMeasurement.js` 托管 `VisitorAPI.js`。 与组织中的相应工程团队合作，将此文件托管在正确的位置。

### 第3步：在每 `stats.html` 个Facebook即时文章页面上引用

创建Facebook Instant Article内容时，将分析HTML内容嵌入iframe中。 例如：

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### 第4步：设置自定义变量和事件跟踪

可通过两种不同的方法在分析HTML中跟踪自定义变量和事件：

* 在页面中直接包含变量值和 `stats.html` 事件。 此处定义的变量最适合所有Facebook Instant Articles的值，这些值通常相同。
* 将变量值包含为引用iframe的查询字符串的一部分。 此方法允许您将变量值从Facebook Instant Article发送到承载Analytics代码的iframe。

以下示例显示了查询字符串中包含的几个自定义变量。 其中的JavaScript `stats.html` 随后将使用检查查询字符串 `s.Util.getQueryParam()`。

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

> [!NOTE] 参照尺寸不会因为iframe的性质而自动跟踪。 如果要跟踪该维，请确保将该维作为查询字符串的一部分包含在其中。

## Facebook Instant Articles和隐私

只要Analytics HTML页面托管在您的Web服务器上，Adobe就支持您在所有Facebook Instant Articles中的现有隐私策略。 如果用户选择退出主站点上的跟踪，则他们也会选择退出所有Facebook Instant Articles上的跟踪。 该实用程序页面还支持Adobe Experience Cloud Identity Service，以便您将Facebook Instant Article数据与Experience cloud的其余部分相集成。
