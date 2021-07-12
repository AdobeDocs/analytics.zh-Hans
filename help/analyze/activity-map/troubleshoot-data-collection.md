---
title: Activity Map数据收集疑难解答
description: 确定在图像请求中看不到Activity Map数据的原因
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---

# Activity Map数据收集疑难解答

如果看不到Activity Map维度的数据，请使用此页面帮助确定原因。

## 使用调试器确认数据收集

首先，确保AppMeasurement正确收集Activity Map数据。

1. 下载并安装[Adobe Experience Cloud Debugger Chrome扩展](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hans)。
2. 导航到您的网页，然后单击链接。
3. 加载后续页面时，打开调试器。 验证您是否看到夹在`activitymap.`和`.activitymap`之间的Activity Map上下文数据变量：

![调试器数据](assets/debugger.png)

## Activity Map数据不存在的可能原因

检查以下每个组件，确保Activity Map组件存在：

* **AppMeasurement版本**:v1.6及更高版本支持Activity Map。当您升级到最新稳定版本的AppMeasurement时，会解决许多边缘案例问题。
* **Activity Map模块**:检查文 `AppMeasurement_Module_Activity_Map` 件中是否存在模 `AppMeasurement.js` 块。如果您的实施使用Adobe Experience Platform Launch，请确保在&#x200B;**[!UICONTROL 链接跟踪]**&#x200B;下配置Analytics扩展时选中&#x200B;**[!UICONTROL 启用ClickMap]**。
* **`s_sq` Cookie**:Activity Map取决于 `s_sq` 数据收集Cookie。
   * 确保正确设置了`cookieDomainPeriods`变量，特别是对于区域域（如`*.co.uk`或`*.co.jp`）。
   * 确保将`linkInternalFilters`变量设置为所需值。 如果点击的链接与内部过滤器不匹配，则Activity Map会将其视为退出链接，并且不收集数据。
* **Activity Map叠加正在运行**:启用Activity Map叠加后，AppMeasurement不会跟踪网页的点击数据。
