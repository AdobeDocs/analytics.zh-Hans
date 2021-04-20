---
title: Activity Map数据收集疑难解答
description: 确定在图像请求中看不到Activity Map数据的原因
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 3%

---


# Activity Map数据收集疑难解答

如果看不到Activity Map维度的数据，请使用此页帮助确定原因。

## 使用调试器确认数据收集

首先，确保AppMeasurement正确收集Activity Map数据。

1. 下载并安装[Adobe Experience Cloud Debugger Chrome Extension](https://docs.adobe.com/content/help/zh_CN/debugger/using/experience-cloud-debugger.html)。
2. 导览至网页，然后单击链接。
3. 加载后续页面时，打开调试器。 验证您是否看到夹在`activitymap.`和`.activitymap`之间的Activity Map上下文数据变量：

![调试器数据](assets/debugger.png)

## Activity Map数据不存在的可能原因

检查以下各项，确保存在Activity Map组件：

* **AppMeasurement版本**:v1.6及更高版本支持Activity Map。升级到最新稳定版AppMeasurement时，会解决许多边缘案例问题。
* **Activity Map模块**:检查文 `AppMeasurement_Module_Activity_Map` 件中是否存在 `AppMeasurement.js` 模块。如果您的实施使用Adobe Experience Platform Launch，请确保在&#x200B;**[!UICONTROL 链接跟踪]**&#x200B;下配置Analytics扩展时选中&#x200B;**[!UICONTROL 启用ClickMap]**。
* **Cookie `s_sq`**:Activity Map取决 `s_sq` 于数据收集Cookie。
   * 确保正确设置`cookieDomainPeriods`变量，尤其是对于`*.co.uk`或`*.co.jp`等区域域。
   * 确保将`linkInternalFilters`变量设置为所需值。 如果单击的链接与内部过滤器不匹配，则Activity Map会将其视为退出链接且不收集数据。
* **Activity Map叠加正在运行**:启用Activity Map叠加后，AppMeasurement不会跟踪网页的点击数据。
