---
title: AppMeasurement for JavaScript
description: 了解如何使用JavaScript在无标签管理系统的情况下实施Adobe Analytics。
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# AppMeasurement for JavaScript

AppMeasurement for javaScript历来是实施Adobe Analytics的常用方法。 但是，随着标签管理系统的日益普及，建议 [使用Adobe Experience Platform Launch](../launch/overview.md) 。

## 使用JavaScript向Adobe发送数据的整个工作流程

1. 加载文 `AppMeasurement.js` 件。 此文件包含向Adobe发送数据所需的库。

   ```html
   <script src="AppMeasurement.js"></script>
   ```

2. 在中定义配置变量 `AppMeasurement.js`。 实例化Analytics对象时，这些变量可确保数据收集设置正确无误。 有关 [可定义的变量的完整列表](../vars/config-vars/configuration-variables.md) ，请参阅配置变量。

   ```js
   // Instantiate the Analytics tracking object with report suite ID
   var s_account = "examplersid";
   var s=s_gi(s_account);
   // Make sure data is sent to the correct location
   s.trackingServer = "example.omtrdc.net";
   ```

3. 在站点的页面代码中定义页面级别变量。 这些变量决定发送给Adobe的特定维度和指标。 有关 [可定义的变量的完整列表](../vars/page-vars/page-variables.md) ，请参阅页面变量。

   ```js
   s.pageName = "Example page";
   s.eVar1 = "Example eVar";
   s.events = "event1";
   ```

4. 定义所有页面级变量后，使用函数将数据发送到Adobe `t` 。 请参 [阅](../vars/functions/t.md) t以了解更多信息。

   ```js
   s.t();
   ```
