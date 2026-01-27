---
title: Activity Map 快速入门
description: Activity Map 叠加和维度快速入门。
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: a7670fcda3e8e6af0c036c8b263746e142278255
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 100%

---

# Activity Map 快速入门

Adobe Analytics 中的 Activity Map 由四个主要元素组成：

* **报告包设置**：您必须在报告包设置中启用 Activity Map。启用后，报告包会为 Activity Map 维度和量度创建多个保留的变量。
* **实施**：收集您的网站或属性上的 Activity Map 数据。自定义如何收集数据，可以提高报告的质量和体验。
* **Workspace 维度和量度**：如果您的实施配置正确，您就可以在 Analysis Workspace 中使用 Activity Map 维度和量度。
* **叠加**：Adobe 提供一个浏览器扩展，可用于在您网站的上下文中查看 Activity Map 数据。此功能不适用于 Web SDK 实施。

## 启用报告包设置

报告包必须启用 Activity Map 报告，然后您才能开始收集数据。如果您的实施将 Activity Map 数据发送到一个未启用 Activity Map 报告的报告包，点击中就不会包含 Activity Map 数据。

**[!UICONTROL 管理员]** > **[!UICONTROL 报告包]** > 选择报告包 > **[!UICONTROL 编辑设置]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map 报告]** > **[!UICONTROL 启用 Activity Map 报告]**

启用 Activity Map 报告后会创建多个后端保留的变量。更多信息请参阅 Adobe Analytics 管理员指南中的 [Activity Map 报告](/help/admin/tools/manage-rs/edit-settings/activity-map.md)。

## 代码安装

您的实施必须正确配置，才能将 Activity Map 数据发送到 Adobe。如果用 Web SDK 实施 Adobe Analytics，叠加浏览器扩展就不可用。

+++Web SDK 标记扩展

Activity Map 数据收集需要 **[!UICONTROL Adobe Experience Platform Web SDK]** 扩展 v2.23 或更高版本。v2.16 及以下的扩展版本的支持受限。这些以前的扩展版本通过一个与您的其余数据不同的单独的事件发送 Activity Map 数据。这个额外的事件会增加您发送到 Adobe Analytics 或 Adobe Experience Platform 的点击数。

**[!UICONTROL 点击数据收集]**&#x200B;配置设置会处理 Activity Map 数据收集，通常在默认情况下会启用该设置。您可以检查确保在扩展的配置设置中启用了它：

1. 登录到 [experience.adobe.com](https://experience.adobe.com)
1. 在右上方的快速访问菜单或产品选择器中选择&#x200B;**[!UICONTROL 数据收集]**。
1. 在左侧导航菜单中选择&#x200B;**[!UICONTROL 标记]**。
1. 选择要编辑的标记。
1. 在左侧导航菜单中选择&#x200B;**[!UICONTROL 扩展]**。
1. 在已安装扩展的列表中选择 **[!UICONTROL Adobe Experience Platform Web SDK]**，然后选择右侧的&#x200B;**[!UICONTROL 配置]**。
1. 找到带有[!UICONTROL 数据收集]标签的部分，并确保勾选复选框&#x200B;**[!UICONTROL 启用点击数据收集]**。
1. 选择&#x200B;**[!UICONTROL 保存]**。
1. 如果需要，可将您的更改构建为库，将更改发布到生产环境。

更多信息请参阅[配置 Web SDK 标记扩展](https://experienceleague.adobe.com/cn/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection)。

+++

+++Web SDK JavaScript 库（`alloy.js`）

Activity Map 数据收集需要 Web SDK JavaScript 库 v2.20 或更高版本。v2.15 及以下版本的库的支持受限。这些以前的库版本通过一个与您的其余数据不同的单独的事件发送 Activity Map 数据。这个额外的事件会增加您发送到 Adobe Analytics 或 Adobe Experience Platform 的点击数。

Web SDK 配置变量 [`clickCollectionEnabled`](https://experienceleague.adobe.com/cn/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) 会处理 Activity Map 数据的自动收集。除非明确禁用，否则在默认情况下会启用。

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Adobe Analytics 标记扩展

**[!UICONTROL 使用 Activity Map]** 配置设置会处理 Activity Map 数据收集，通常在默认情况下会启用该设置。它适用于所有 v1.9.0 或更高版本的标记扩展。您可以检查确保在扩展的配置设置中启用了它：

1. 登录到 [experience.adobe.com](https://experience.adobe.com)
1. 在右上方的快速访问菜单或产品选择器中选择&#x200B;**[!UICONTROL 数据收集]**。
1. 在左侧导航菜单中选择&#x200B;**[!UICONTROL 标记]**。
1. 选择要编辑的标记。
1. 在左侧导航菜单中选择&#x200B;**[!UICONTROL 扩展]**。
1. 在已安装扩展的列表中选择 **[!UICONTROL Adobe Analytics]**，然后选择右侧的&#x200B;**[!UICONTROL 配置]**。
1. 确保勾选复选框&#x200B;**[!UICONTROL 使用 Activity Map]**。
1. 选择&#x200B;**[!UICONTROL 保存]**。
1. 如果需要，可将您的更改构建为库，将更改发布到生产环境。

更多信息请参阅 [Adobe Analytics 扩展概述](https://experienceleague.adobe.com/cn/docs/experience-platform/tags/extensions/client/analytics/overview)。

+++

+++Adobe Analytics JavaScript 库（`AppMeasurement.js`）

Activity Map 模块会处理 Activity Map 数据收集，它包含在所有 v1.6 或更高版本的 AppMeasurement 库中。您可以检查 `AppMeasurement.js` 文件，以确保包含。

1. 导航到 GitHub 上的[最新 Adobe Analytics AppMeasurement 发行版本](https://github.com/adobe/appmeasurement/releases/latest)。
1. 下载压缩的 AppMeasurement 库文件，然后打开其中包含的 `AppMeasurement.js`。
1. Activity Map 模块包含在此文件的顶部附近。确保此模块包含在您的网站使用的 AppMeasurement 库中。

+++

## 可用的维度

如果您同时为报告包和实施启用了 Activity Map，您就可以在 Analysis Workspace 中开始使用以下维度：

* [[!UICONTROL Activity Map 链接]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Activity Map 区域]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Activity Map 页面]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL 按区域划分的 Activity Map 链接]](/help/components/dimensions/activity-map-link-by-region.md)

## 下载并安装浏览器扩展或附加组件

除了 Analysis Workspace 中可用的维度之外，您还可以以网站上的叠加方式查看 Activity Map 数据。要查看这样的叠加，请下载并安装 Activity Map 浏览器扩展或附加组件。

**[!UICONTROL 工具]** > **[!UICONTROL Activity Map]** > **[!UICONTROL 下载 Activity Map]**

此链接会将您转到受支持的浏览器扩展或附加组件市场，您可以在那里安装。安装好的扩展或附加组件会显示在浏览器的右上方，您可以在那里登录并启用叠加。
