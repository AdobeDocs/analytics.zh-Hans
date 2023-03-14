---
title: Activity Map数据收集疑难解答
description: 确定为什么在图像请求中看不到Activity Map数据
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Activity Map数据收集疑难解答

如果您没有看到Activity Map维的数据，请使用此页帮助确定原因。

## 使用调试器确认数据收集

首先，确保AppMeasurement正确收集Activity Map数据。

1. 下载并安装 [Adobe Experience Cloud Debugger Chrome扩展](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html).
2. 导航到您的网页，然后单击链接。
3. 加载后续页面时，打开调试器。 验证您是否看到Activity Map上下文数据变量夹在 `activitymap.` 和 `.activitymap`：

![Debugger数据](assets/debugger.png)

## Activity Map数据不存在的可能原因

检查以下各项，确保Activity Map组件存在：

* **AppMeasurement版本**：v1.6及更高版本支持Activity Map。 当您升级到最新稳定版本的AppMeasurement时，许多边缘案例问题都已得到解决。
* **Activity Map模块**：检查 `AppMeasurement_Module_Activity_Map` 模块存在于您的 `AppMeasurement.js` 文件。 如果您的实施使用Adobe Experience Platform收集数据，请确保 **[!UICONTROL 启用ClickMap]** 在以下内容下配置Analytics扩展时，将选中 **[!UICONTROL 链接跟踪]**.
* **此 `s_sq` Cookie**：Activity Map取决于 `s_sq` 用于数据收集的Cookie。
   * 确保 `cookieDomainPeriods` 变量设置正确，尤其是对于区域域，例如 `*.co.uk` 或 `*.co.jp`.
   * 确保 `linkInternalFilters` 变量设置为所需的值。 如果点击的链接与内部过滤器不匹配，Activity Map会将其视为退出链接，因此不会收集数据。
* **Activity Map叠加正在运行**：启用Activity Map叠加后，AppMeasurement不会跟踪您网页的点击数据。
