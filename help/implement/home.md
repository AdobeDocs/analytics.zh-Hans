---
title: 实施 Adobe Analytics
description: 在您的网站、属性或应用程序上实施 Adobe Analytics。
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: b157674adf67fa6ef0f2e75775d0ec888cff3cba
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 55%

---

# 实施 Adobe Analytics

![横幅](../../assets/doc_banner_implement.png)

Adobe 需要在您的网站或应用程序上实施相应代码，才能将数据发送到 Adobe 的数据收集服务器。以下步骤说明了典型实施的工作原理。

1. 访客访问您的站点时，会向您的 Web 服务器发送一个请求。
2. 您站点的 Web 服务器随之会发送页面代码信息，这样相关页面就显示在浏览器中了。
3. 加载页面，并运行 Analytics JavaScript 代码。JavaScript 代码将图像请求发送至 Adobe 数据收集服务器。 您在实施中定义的页面数据将作为此图像请求中某个查询字符串的一部分发送。

4. Adobe 返回透明的像素图像。
5. Adobe 服务器会将收集的数据存储在一个或多个&#x200B;*报告包* 中。
6. 报告包数据会填充您可以在 Web 浏览器中访问的报告。

JavaScript 代码执行非常迅速，不会显著影响页面加载时间。通过这种方法，您可以统计访客点击&#x200B;**[!UICONTROL 重新加载]**&#x200B;或&#x200B;**[!UICONTROL 后退]**&#x200B;以抵达某个页面时所显示的页面数量，因为即使页面是从缓存中获取，JavaScript 仍可以运行。

Adobe Analytics 需要在您的网站、移动应用程序或其他应用程序中实施相应代码，才能将数据发送到数据收集服务器。根据平台和贵组织的需求，可以通过多种方法来实施相应代码。

## 网站实施方法

对于您的&#x200B;**网站**，可以使用以下实现方法：

* **Web SDK 扩展**：这是一种在为新客户实施 Adobe Analytics 时推荐使用的标准化方法。 添加 **Adobe Experience Platform Web SDK扩展** 在Adobe Experience Platform数据收集中 **标记**，然后在每个页面上放置一个加载器标记。 标记会将数据发送到Adobe Experience Platform **边缘网络**，会将相关数据转发到Adobe Analytics。
  ![Web SDK扩展](./assets/websdk-extension-implementation.png)
请参阅 [如何使用Adobe Analytics Web SDK扩展实施Adobe Experience Platform。](./aep-edge/overview.md)以了解详细信息。

* **Web SDK**：如果您不想使用 Adobe Experience Platform 数据收集，可以在您的站点上手动加载 Web SDK 库。 在每个页面上引用 Web SDK 库 (`alloy.js`)，并将所需的跟踪调用以您组织方便的格式发送到 Adobe Experience Platform **Edge Network**。 Edge Network将该数据转发到Adobe Analytics。
  ![Web SDK](./assets/websdk-implementation.png)
请参阅 [如何使用Adobe Experience Platform Web SDK实施Adobe Analytics](./aep-edge/overview.md) 以了解更多信息。

* **Analytics扩展**：添加 **Adobe Analytics扩展** 在Adobe Experience Platform数据收集中 **标记**，然后在每个页面上放置一个加载器标记。 标记会将数据直接发送到Adobe Analytics。 如果您希望标记带来便利，但不希望使用Edge Network基础架构，请使用此实施方法。
  ![Adobe Analytics扩展](./assets/analytics-extension-implementation.png)
请参阅 [如何使用Adobe Analytics扩展实施Analytics](launch/overview.md) 以了解更多信息。

* **旧版 JavaScript**：实施 Adobe Analytics 的历史手动方法。引用AppMeasurement库(`AppMeasurement.js`)，然后在JavaScript中设置变量和设置。
  ![如何使用旧版JavaScript实施Adobe Analytics](./assets/appmeasurement-implementation.png)
此实施方法可用于使用自定义代码的实施，非常适用于不在其他位置提供的实施类型，例如 [AMP页面](other/amp.md).

以下决策流可帮助您选择实施方法：

![用于选择实施方法的决策树，如本节所述。](./assets/decision-tree.png)


>[!TIP]
>
>请联系您的Adobe客户团队，以获取有关根据您的当前情况选择实施方面的建议和最佳实践。

## 移动应用程序实施方法

对于您的&#x200B;**移动应用程序**，可以使用以下实现方法：

* **Mobile SDK 扩展**：这是一种在您的移动应用程序中实施 Adobe Analytics 时推荐使用的标准化方法。 使用专用库，可轻松将数据从您的移动应用程序中发送到 Adobe。 添加 **Adobe Experience Platform移动SDK扩展** 在Adobe Experience Platform数据收集中 **标记**，然后在应用程序中实施移动SDK库。 您可以使用SDK导入库、注册扩展和加载标记配置。 将数据发送到Adobe Experience Platform **边缘网络**； Edge随后将该数据转发到Adobe Analytics。
  ![Mobile SDK 扩展](./assets/mobilesdk-extension.png)

  有关详细信息，请参阅[使用 Adobe Experience Platform Mobile SDK 实施 Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md)。

* **Analytics扩展**：添加 **Adobe Analytics扩展** 在Adobe Experience Platform数据收集中 **标记**，并在应用程序中实施移动SDK库。 您可以使用SDK导入库、注册扩展和加载标记配置。 此实施方法会将数据直接发送到Adobe Analytics。 如果您希望使用Adobe Experience Platform数据收集的便利性，但不希望使用Adobe的Experience Platform边缘网络基础架构，则建议您这样做。
  ![Analytics 扩展](./assets/mobilesdk-analytics-extension.png)

  有关详细信息，请参阅[使用 Analytics 扩展实施 Adobe Analytics](../implement/aep-edge/mobile-sdk/overview.md)。


>[!CAUTION]
>
>对版本 4 Mobile SDK 的支持于 2021 年 8 月 31 日终止。 有关更多信息，请参阅[版本 4 Mobile SDK 支持终止常见问题解答](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/v4-faq/)。

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
