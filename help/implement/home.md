---
title: 实施 Adobe Analytics
description: 在您的网站、属性或应用程序上实施 Adobe Analytics。
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: d2c291f7db465034ffadc4a2c1caf9639caf2a1d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 79%

---

# 实施 Adobe Analytics

![横幅](../../assets/doc_banner_implement.png)

下面是 Adobe Analytics 的视频概述：

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Adobe 需要在您的网站或应用程序上实施相应代码，才能将数据发送到 Adobe 的数据收集服务器。以下步骤说明了典型实施的工作原理。

1. 访客访问您的站点时，会向您的 Web 服务器发送一个请求。
2. 您站点的 Web 服务器随之会发送页面代码信息，这样相关页面就显示在浏览器中了。
3. 加载页面，并运行 Analytics JavaScript 代码。
4. JavaScript代码向Adobe数据收集服务器发送1x1像素图像请求。 您在实施中定义的页面数据将作为此图像请求中某个查询字符串的一部分发送。
5. Adobe的数据收集服务器返回请求的图像。
6. Adobe服务器将收集的数据解析并存储在报表包中。
7. 报告包数据会填充您可以在 Web 浏览器中访问的报告。


Adobe根据平台和贵组织的需求，提供了多种实施此代码的方法。

* **Web SDK扩展**:当前用于实施Adobe Analytics的标准化和推荐方法。 在 Adobe Experience Platform 数据收集中安装 Web SDK 扩展，在每个页面上使用加载器标签，并以组织方便的格式将数据发送到 Adobe Experience Platform Edge。Experience Edge 以正确的格式将传入数据转发到 Adobe Analytics。
* **Web SDK**:如果您不想使用“标记”，则可以在网站上手动加载Web SDK库。 在每个页面上引用 Web SDK 库，并将所需的跟踪调用发送到 Adobe Experience Edge。
* **Adobe Analytics 扩展**：在 Adobe Experience Platform 数据收集中安装 Adobe Analytics 扩展。该方法会在每个页面上设置一个加载器标记，并使用 Analytics 扩展来确定每个变量的定义方式。
* **旧版 JavaScript**：实施 Adobe Analytics 的历史手动方法。概述实施中使用的变量和设置，对于使用自定义代码规则的 实施很有用。
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
