---
title: 实施 Adobe Analytics
description: 在您的网站、属性或应用程序上实施 Adobe Analytics。
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 79%

---

# 实施 Adobe Analytics

![横幅](../../assets/doc_banner_implement.png)

下面是 Adobe Analytics 的视频概述：

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Adobe 需要在您的网站或应用程序上实施相应代码，才能将数据发送到 Adobe 的数据收集服务器。以下步骤说明了典型实施的工作原理。

1. 访客访问您的站点时，会向您的 Web 服务器发送一个请求。
2. 您站点的 Web 服务器随之会发送页面代码信息，这样相关页面就显示在浏览器中了。
3. 加载页面，并运行 Analytics JavaScript 代码。JavaScript 代码将图像请求发送至 Adobe 数据收集服务器。您在实施中定义的页面数据将作为此图像请求中某个查询字符串的一部分发送。

4. Adobe 返回透明的像素图像。
5. Adobe 服务器会将收集的数据存储在一个或多个&#x200B;*报表包* 中。
6. 报表包数据会填充您可以在 Web 浏览器中访问的报表。

   JavaScript 代码执行非常迅速，不会显著影响页面加载时间。通过这种方法，您可以统计访客点击&#x200B;**[!UICONTROL 重新加载]**&#x200B;或&#x200B;**[!UICONTROL 后退]**&#x200B;以抵达某个页面时所显示的页面数量，因为即使页面是从缓存中获取，JavaScript 仍可以运行。

Adobe Analytics 需要在您的网站、移动应用程序或其他应用程序中实施相应代码，才能将数据发送到数据收集服务器。根据平台和贵组织的需求，可以通过多种方法来实施相应代码。

* **Web SDK**:实施Adobe Analytics的标准化和推荐方法。 在Adobe Experience Platform数据收集中安装Web SDK扩展，在每个页面上使用加载器标记，并以便于贵组织使用的格式将数据发送到Adobe Experience Platform Edge。 Experience Edge以正确的格式将传入数据转发到Adobe Analytics。
* **Adobe Analytics扩展**:在Adobe Experience Platform数据收集中安装Adobe Analytics扩展。 在每个页面上放置一个加载器标记，然后使用Analytics扩展确定每个变量的定义方式。
* **旧版 JavaScript**：实施 Adobe Analytics 的历史手动方法。概述实施中使用的变量和设置，对于使用自定义代码规则的标记实施很有用。
* **Mobile SDK**：专用库，可轻松将数据从您的移动设备应用程序中发送到 Adobe。

## 重要 Analytics 实施文章

* [负责现有的 Adobe Analytics 实施](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [在 Experience Platform 中创建标记属性](launch/create-analytics-property.md)
* [AppMeasurement 更新](appmeasurement-updates.md)

## 更多 Analytics 用户指南

[Analytics 用户指南](https://experienceleague.adobe.com/docs/analytics.html)

## 重要 Analytics 资源

* [联系客户关怀团队](https://experienceleague.adobe.com/?support-solution=Analytics#support)
* [Analytics 论坛](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics 资源](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
