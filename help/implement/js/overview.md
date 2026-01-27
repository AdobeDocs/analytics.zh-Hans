---
title: 使用 AppMeasurement for JavaScript 实施 Adobe Analytics
description: 了解如何在没有标记管理系统的情况下使用 JavaScript 实施 Adobe Analytics。
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
role: Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 100%

---

# 使用 AppMeasurement for JavaScript 实施 Adobe Analytics

AppMeasurement for JavaScript 一直以来都是实施 Adobe Analytics 的常用方法。但是，随着标记管理系统的日益普及，建议使用 [Adobe Experience Platform 中的标记](../launch/overview.md)来实施。

实施任务的高级概述：

![如何用 AppMeasurement for Javascript 实施 Adobe Analytics，如这部分所述。](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>任务</b></th><th style="width:20%"><b>更多信息</b></th>
</tr>

<tr>
<td>1</td><td>确保您已<b>定义了报告包</b>。</td><td><a href="../../admin/tools/manage-rs/report-suites-admin.md">报告包管理器</a></td>
</tr>

<tr>
<td>2</td><td>从代码管理器<b>为 AppMeasurement 下载所需的 JavaScript 代码</b>。解压缩文件。</td><td><a href="../../admin/tools/code-manager-admin.md">代码管理器</a></td>
</tr>

<tr>
<td>3</td><td><b>将 <code>AppMeasurement.js</code> 添加到您网站的模板文件中</b>。此代码包含向 Adobe 发送数据所需的库。

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>在 <code>AppMeasurement.js</code></b> 中定义配置变量。Analytics 对象实例化后，这些变量可确保数据收集设置正确无误。

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
<td>5</td><td><b>在网站的页面代码中定义页面级变量</b>。此类变量可确定发送给 Adobe 的具体维度和量度。

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">页面变量</a></td>
</tr>

<tr>
<td>6</td><td>定义所有页面级变量后，<b>使用 <code>t()</code> 方法将数据发送到 Adobe</b>。

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">t() 方法</a></td>
</tr>

<tr>
<td>7</td><td><b>将您的实施</b>推向生产环境之前，对其进行扩展和验证。</b></td><td></td>
</tr>

</table>

## 其他资源

- [变量、函数、方法及插件概述](../vars/overview.md)
