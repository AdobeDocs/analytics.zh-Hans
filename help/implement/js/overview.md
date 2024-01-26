---
title: 使用JavaScriptAppMeasurement实施Adobe Analytics
description: 了解如何在没有标签管理系统的情况下使用 JavaScript 实施 Adobe Analytics。
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 42%

---

# 使用JavaScriptAppMeasurement实施Adobe Analytics

AppMeasurement for JavaScript 一直以来都是实施 Adobe Analytics 的常用方法。但是，随着标记管理系统的日益普及，建议使用 [Adobe Experience Platform 中的标记](../launch/overview.md)来实施。

实施任务的高级概述：

![如何通过Javascript的AppMeasurement实施AdobeAnalytics，如本节所述。](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>任务</b></th><th style="width:20%"><b>更多信息</b></th>
</tr>

<tr>
<td>1</td><td>确保您拥有 <b>定义了报表包</b></td><td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">报告包管理器</a></td>
</tr>

<tr>
<td>2</td><td><b>下载所需的JavaScript代码以进行AppMeasurement</b> 代码管理器中的。 解压缩文件。</td><td><a href="../../admin/admin/code-manager-admin.md">代码管理器</a></td>
</tr>

<tr>
<td>3</td><td><b>添加 <code>AppMeasurement.js</code> 到您网站的模板文件</b>. 该代码包含向Adobe发送数据所需的库。

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>在中定义配置变量 <code>AppMeasurement.js</code></b>. 实例化Analytics对象后，这些变量可确保数据收集设置正确无误。

```JavaScript
// Instantiate the Analytics tracking object with report suite ID
var s_account = "examplersid";
var s=s_gi(s_account);
 
// Make sure data is sent to the correct tracking server
s.trackingServer = "example.data.adobedc.net";
```

</td><td><a href="../vars/config-vars/configuration-variables.md">配置变量</a></td>
</tr>

<tr>
<td>5</td><td><b>在网站的页面代码中定义页面级变量</b>. 这些变量可确定发送给Adobe的特定维度和量度。

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">页面变量</a></td>
</tr>

<tr>
<td>6</td><td><b>使用将数据发送到Adobe <code>t()</code> 方法</b>，则表示已定义了所有页面变量。

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">t()方法</a></td>
</tr>

<tr>
<td>7</td><td><b>将您的实施</b>推向生产环境之前，对其进行扩展和验证。</b></td><td></td>
</tr>

</table>

## 其他资源

- [变量、函数、方法及插件概述](../vars/overview.md)
