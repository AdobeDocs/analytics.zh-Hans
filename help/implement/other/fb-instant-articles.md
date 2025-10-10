---
title: 使用 Facebook Instant Articles 实施
description: 在 Facebook Instant Articles 页面上实施 Adobe Analytics。
feature: Implementation Basics
exl-id: 2189f70d-32f0-4137-9d53-7acab0f15e6c
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 100%

---

# 使用 Facebook Instant Articles 实施

Facebook Instant Articles 允许发布者在 Facebook 上快速构建交互式文章。Instant Articles 的内容加载速度比移动网页快 10 倍。

您可以将 Adobe Analytics 嵌入到 Facebook Instant Articles 中以跟踪访客行为。由于发布者内容是在 Facebook 应用程序中，而不是在发布者的网站上，因此标记方法与 Analytics 标准实施的方法略有不同。

## 工作流

实施 Adobe Analytics 的完整工作流如下：

1. 创建 `stats.html` 页面。对此页进行编码，以便从 URL 中提取查询字符串参数，并将每个参数分配给 Analytics 变量
1. 将 `stats.html` 页面托管在 Web 服务器上
1. 通过在 iFrame 中引用 `stats.html` 文件在 Facebook Instant Articles 上实施 Analytics
1. 将查询字符串参数包含到 iFrame `src` 属性中

### 第 1 步：创建 `stats.html` 页面

下面的 HTML 示例可用于从 Instant Articles 中捕获统计数据。此文件通常会托管在贵公司的某台 Web 服务器中。每次加载 Instant Articles 时，它都会将相应文件加载到 iFrame 中，进而触发向 Adobe 发送数据的操作。

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
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
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

### 第 2 步：将 `stats.html` 页面托管在 Web 服务器上

Adobe 建议将您的 `stats.html` 页面与最新版本的 `AppMeasurement.js`和 `VisitorAPI.js` 一起托管。与组织中的相应工程团队合作，将此文件托管到正确的位置中。

### 第 3 步：在每个 Facebook Instant Articles 页面上引用 `stats.html`

创建 Facebook Instant Articles 内容时，您可以在 iFrame 中嵌入 Analytics HTML 内容。例如：

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### 第 4 步：设置自定义变量和事件跟踪

您可以通过两种不同方法，在您的 Analytics HTML 中跟踪自定义变量和事件：

* 直接将变量值和事件包含到 `stats.html` 页面中。此处定义的变量最适合存储通常对所有 Facebook Instant Articles 而言都相同的值。
* 将变量值包含到引用 iFrame 的查询字符串中。此方法允许您将变量值从 Facebook Instant Articles 发送到托管 Analytics 代码的 iFrame。

以下示例显示了查询字符串中包含的几个自定义变量。`stats.html` 中的 JavaScript 随后将使用 `s.Util.getQueryParam()` 检查查询字符串。

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>由于 iFrame 的性质，不会自动跟踪“反向链接”维度。如果要跟踪此维度，请确保将此维度包含到查询字符串中。

## Facebook Instant Articles 和隐私政策

只要 Analytics HTML 页面托管在您的 Web 服务器中，Adobe 就能够在所有 Facebook Instant Articles 中支持您现有的隐私政策。如果用户在主网站上选择退出跟踪，则他们也会在所有 Facebook Instant Articles 上选择退出跟踪。此实用程序页面还支持 Adobe Experience Cloud 身份标识服务，以便您可以将 Facebook Instant Articles 数据与 Experience Cloud 的其他服务相集成。
