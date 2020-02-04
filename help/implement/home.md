---
title: 实施 Adobe Analytics
description: 在您的站点、属性或应用程序上实施Adobe Analytics。
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# 实施 Adobe Analytics

![横幅](../../assets/doc_banner_implement.png)

Adobe要求您的站点或应用程序上的代码将数据发送到Adobe的数据收集服务器。 以下步骤说明了典型实现的工作方式。

1. 访客访问您的站点时，会向您的 Web 服务器发送一个请求。
2. 您站点的 Web 服务器随之会发送页面代码信息，这样相关页面就显示在浏览器中了。
3. 加载页面，并运行 Analytics JavaScript 代码。JavaScript代码发送图像请求Adobe数据收集服务器。 您在实施中定义的页面数据将作为此图像请求中查询字符串的一部分发送。

4. Adobe 返回透明的像素图像。
5. Adobe服务器将收集的数据存储在报 *告套件中*。
6. 报表包数据会填充您可以在 Web 浏览器中访问的报表。

   JavaScript 代码执行非常迅速，不会显著影响页面加载时间。通过这种方法，您可以统计访客点击&#x200B;**[!UICONTROL 重新加载]**或**[!UICONTROL &#x200B;后退]**以抵达某个页面时所显示的页面数量，因为即使页面是从缓存中获取，JavaScript 仍可以运行。

Adobe Analytics需要您的网站、移动应用程序或其他应用程序中的代码才能将数据发送到数据收集服务器。 根据平台和贵组织的需求，可以通过多种方法来实现此代码。

* **Adobe Experience Platform Launch**:实施Adobe Analytics的标准化和推荐方法。 该方法会在每个页面上设置一个加载器标记，并使用 Launch 的界面来确定每个变量的定义方式。
* **动态标签管理**:Launch的前身。 DTM 使用类似的界面来实施 Analytics，但不再更新，也没有那么灵活。Adobe 建议使用 Launch 来实施 Adobe Analytics。
* **传统JavaScript**:实施Adobe Analytics的历史手动方法。 概述实施中使用的变量和设置，对于使用自定义代码规则的 Launch 实施很有用。
* **Mobile SDK**:专用库，可在您的移动应用程序中轻松将数据发送到Adobe。

## 重要 Analytics 实施文章

* [Adobe Debugger](validate/debugger.md)
* [在 Experience Platform Launch 中创建属性](launch/create-analytics-property.md)
* [AppMeasurement更新](appmeasurement-updates.md)

## 更多 Analytics 用户指南

[Analytics 用户指南](/help/landing/home.md)

## 重要 Analytics 资源

* [联系客户关怀团队](https://helpx.adobe.com/contact/enterprise-support.ec.html)
* [Analytics 论坛](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics 资源](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
