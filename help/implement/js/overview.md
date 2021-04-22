---
title: AppMeasurement for JavaScript
description: 了解如何在没有标签管理系统的情况下使用 JavaScript 实施 Adobe Analytics。
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '149'
ht-degree: 100%

---

# AppMeasurement for JavaScript

AppMeasurement for JavaScript 一直以来都是实施 Adobe Analytics 的常用方法。但是，随着标签管理系统的日益普及，建议使用 [Adobe Experience Platform Launch](../launch/overview.md) 来实施。

## 使用 JavaScript 向 Adobe 发送数据的整个工作流

1. 加载 `AppMeasurement.js` 文件。此文件包含向 Adobe 发送数据所需的库。

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. 在 `AppMeasurement.js` 中定义配置变量。实例化 Analytics 对象后，定义的配置变量可确保数据收集设置正确无误。有关可定义变量的完整列表，请参阅[配置变量](../vars/config-vars/configuration-variables.md)。

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.data.adobedc.net";
   ```

3. 在网站的页面代码中定义页面级变量。此类变量可确定发送给 Adobe 的具体维度和量度。有关可定义变量的完整列表，请参阅[页面变量](../vars/page-vars/page-variables.md)。

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. 定义所有页面级变量后，使用 `t()` 方法将数据发送到 Adobe。有关更多信息，请参阅 [t](../vars/functions/t-method.md)。

   ```js
   s.t();
   ```
