---
title: 实施 Adobe Analytics
description: 在您的网站、属性或应用程序上实施 Adobe Analytics。
feature: Implementation Basics
source-git-commit: d9a5d8a15b9e108af795cdfb7ed5481d51311328
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 40%

---

# 实施 Adobe Analytics

![横幅](../../assets/doc_banner_implement.png)

Adobe 需要在您的网站或应用程序上实施相应代码，才能将数据发送到 Adobe 的数据收集服务器。以下步骤说明了典型实施的工作原理。

1. 访客访问您的站点时，会向您的 Web 服务器发送一个请求。
2. 您站点的 Web 服务器随之会发送页面代码信息，这样相关页面就显示在浏览器中了。
3. 加载页面，并运行 Analytics JavaScript 代码。JavaScript代码向Adobe数据收集服务器发送图像请求。 您在实施中定义的页面数据将作为此图像请求中某个查询字符串的一部分发送。

4. Adobe 返回透明的像素图像。
5. Adobe 服务器会将收集的数据存储在一个或多个&#x200B;*报告包* 中。
6. 报告包数据会填充您可以在 Web 浏览器中访问的报告。

JavaScript 代码执行非常迅速，不会显著影响页面加载时间。通过这种方法，您可以统计访客点击&#x200B;**[!UICONTROL 重新加载]**&#x200B;或&#x200B;**[!UICONTROL 后退]**&#x200B;以抵达某个页面时所显示的页面数量，因为即使页面是从缓存中获取，JavaScript 仍可以运行。

Adobe Analytics 需要在您的网站、移动应用程序或其他应用程序中实施相应代码，才能将数据发送到数据收集服务器。根据平台和贵组织的需求，可以通过多种方法来实施相应代码。

## 网站实施方法

对于 **网站**，可使用以下实施方法：

* **Web SDK扩展**:为新客户实施Adobe Analytics时推荐的标准化方法。 安装 **AEP Web SDK扩展** 在Adobe Experience Platform数据收集中 **标记**，请在每个页面上使用加载器标记，并将数据发送到Adobe Experience Platform **边缘网络** 格式，便于贵组织使用。 边缘网络以正确的格式将传入数据转发到Adobe Analytics。
   ![Web SDK扩展](./assets/websdk-extension-implementation.png)
请参阅 [使用Adobe Experience Platform Web SDK扩展实施Adobe Analytics](./aep-edge/overview.md) 以了解更多信息。

* **Web SDK**：如果您不想使用 Adobe Experience Platform 数据收集，可以在您的站点上手动加载 Web SDK 库。 引用Web SDK库(`alloy.js`)，并将所需的跟踪调用发送到Adobe Experience Platform **边缘网络** 格式，便于贵组织使用。 边缘网络以正确的格式将传入数据转发到Adobe Analytics。
   ![Web SDK](./assets/websdk-implementation.png)
请参阅 [使用Adobe Experience Platform Web SDK实施Adobe Analytics](./aep-edge/overview.md) 以了解更多信息。


* **Analytics扩展**:安装 **Adobe Analytics扩展** 在Adobe Experience Platform数据收集中 **标记**. 在每个页面上放置一个加载器标记，然后使用Adobe Analytics扩展确定每个变量的定义方式。 如果您确实希望标记的方便性，但不想使用边缘网络基础结构，请使用此实施方法。
   ![Adobe Analytics扩展](./assets/analytics-extension-implementation.png)
请参阅 [使用Analytics扩展实施Adobe Analytics](launch/overview.md) 以了解更多信息。

* **旧版 JavaScript**：实施 Adobe Analytics 的历史手动方法。引用AppMeasurement库(`AppMeasurement.js`)，然后概述实施中使用的变量和设置。
   ![旧版JavaScript](./assets/appmeasurement-implementation.png)
此实施方法对于使用自定义代码的实施非常有用，在您（想要）使用以下代码时，仍建议使用此实施方法：

   * [点击级别的activity map数据](../analyze/activity-map/activity-map.md),

   * [流媒体测量](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=zh-Hans),

   * [实时流API或实时流触发器](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md),

   * [AMP页面跟踪](./other/amp.md)
   请参阅 [使用AppMeasurement for JavaScript实施Adobe Analytics](js/overview.md) 以了解更多信息。

以下决策流程可能有助于您选择实施方法：

![决策树](./assets/decision-tree.png)


>[!TIP]
>
>请联系Adobe，以获取根据当前情况选择实施的建议和最佳实践。

## 移动设备应用程序实施方法

对于 **移动设备应用程序**，可使用以下实施方法：

* **Mobile SDK扩展**:在移动设备应用程序中实施Adobe Analytics的标准化方法和推荐方法。 使用专用库轻松地将数据从移动设备应用程序内发送到Adobe。 安装 **Adobe Experience Platform Mobile SDK扩展** 在Adobe Experience Platform数据收集中 **标记** 并在您的应用程序中实施正确的代码以导入库、注册扩展和加载标记配置。 这会向Adobe Experience Platform发送数据 **边缘网络** 格式，便于贵组织使用。 Experience Edge 以正确的格式将传入数据转发到 Adobe Analytics。
   ![Mobile SDK扩展](./assets/mobilesdk-extension.png)

   请参阅 [使用Adobe Experience Platform Mobile SDK实施Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md) 以了解更多信息。

* **Analytics扩展**:安装 **Adobe Analytics扩展** 在Adobe Experience Platform数据收集中 **标记**，并在应用程序中实施正确的代码以导入库、注册扩展和加载标记配置。 使用Analytics扩展确定每个变量的定义方式。 如果您确实希望Adobe Experience Platform数据收集的方便性，但不想使用Adobe的Experience Platform边缘网络基础架构，请使用此实施方法。
   ![Analytics 扩展](./assets/mobilesdk-analytics-extension.png)

   请参阅 [使用Analytics扩展实施Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md) 以了解更多信息。


>[!CAUTION]
>
>2021年8月31日终止支持版本4 Mobile SDK。 有关更多信息，请参阅[版本 4 Mobile SDK 支持终止常见问题解答](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/)。

## 重要 Analytics 实施文章

* [负责现有的 Adobe Analytics 实施](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [在 Experience Platform 中创建标记属性](launch/create-analytics-property.md)
* [AppMeasurement 更新](appmeasurement-updates.md)

## 更多 Analytics 用户指南

[Analytics 用户指南](https://experienceleague.adobe.com/docs/analytics.html)

## 重要 Analytics 资源

* [联系客户关怀团队](https://experienceleague.adobe.com/?support-solution=Analytics#support)
* [Analytics 论坛](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community)
* [Adobe Analytics 资源](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666)
