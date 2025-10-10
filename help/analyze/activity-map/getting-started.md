---
title: Activity Map快速入门
description: 开始使用Activity Map叠加和维度。
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# Activity Map快速入门

Adobe Analytics中的Activity Map包含四个主要元素：

* **报表包设置**：必须在报表包设置中启用Activity Map。 启用后，报表包将为Activity Map维度和量度创建多个保留变量。
* **实施**：收集网站或资产上的Activity Map数据。 自定义数据收集方式可以提高报表的质量和体验。
* **Workspace维度和量度**：当您的实施配置正确时，您可以在Analysis Workspace中使用Activity Map维度和量度。
* **覆盖**： Adobe提供了一个浏览器扩展，用于在您网站的上下文中查看Activity Map数据。

## 启用报表包设置

报表包必须启用Activity Map报表，然后才能开始收集数据。 如果您的实施将Activity Map数据发送到未启用Activity Map报表的报表包，则Activity Map数据不会包含在点击中。

**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** >选择报表包> **[!UICONTROL 编辑设置]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map报表]** > **[!UICONTROL 启用Activity Map报表]**

启用Activity Map报表会创建多个后端保留变量。 有关详细信息，请参阅《Activity Map管理指南》中的[Adobe Analytics报表](/help/admin/tools/manage-rs/edit-settings/activity-map.md)。

## 代码安装

必须正确配置您的实施，才能将Activity Map数据发送到Adobe。

+++Web SDK 标记扩展

Activity Map数据收集需要&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;扩展v2.23或更高版本。 低至v2.16的扩展版本具有有限的支持。 这些以前的扩展版本将Activity Map数据与您的其余数据以独立事件发送。 额外的事件会增加您发送到Adobe Analytics或Adobe Experience Platform的点击数。

**[!UICONTROL 单击数据收集]**&#x200B;配置设置处理Activity Map数据收集，默认情况下通常会启用该设置。 您可以检查以确保在扩展的配置设置中启用了它：

1. 登录到[experience.adobe.com](https://experience.adobe.com)
1. 在快速访问菜单或右上方的产品选择器中选择&#x200B;**[!UICONTROL 数据收集]**。
1. 在左侧导航菜单中选择&#x200B;**[!UICONTROL 标记]**。
1. 选择要编辑的所需标记。
1. 在左侧导航菜单中选择&#x200B;**[!UICONTROL 扩展]**。
1. 在已安装的扩展列表中选择&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**，然后选择右侧的&#x200B;**[!UICONTROL 配置]**。
1. 找到标记为[!UICONTROL 数据收集]的部分，并确保已启用复选框&#x200B;**[!UICONTROL 启用点击数据收集]**。
1. 选择&#x200B;**[!UICONTROL 保存]**。
1. 如果需要，可将更改生成到库并将更改发布到生产环境。

有关详细信息，请参阅[配置Web SDK标记扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection)。

+++

+++Web SDK JavaScript库(`alloy.js`)

Activity Map数据收集需要Web SDK JavaScript库v2.20或更高版本。 低于v2.15的库版本具有有限的支持。 这些以前的库版本会以与其余数据分开的事件发送Activity Map数据。 额外的事件会增加您发送到Adobe Analytics或Adobe Experience Platform的点击数。

Web SDK配置变量[`clickCollectionEnabled`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)处理Activity Map数据的自动收集。 除非明确禁用，否则默认情况下会启用该功能。

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Adobe Analytics标记扩展

**[!UICONTROL 使用Activity Map]**&#x200B;配置设置处理Activity Map数据收集，通常默认启用。 它适用于所有标记扩展v1.9.0或更高版本。 您可以检查以确保在扩展的配置设置中启用了它：

1. 登录到[experience.adobe.com](https://experience.adobe.com)
1. 在快速访问菜单或右上方的产品选择器中选择&#x200B;**[!UICONTROL 数据收集]**。
1. 在左侧导航菜单中选择&#x200B;**[!UICONTROL 标记]**。
1. 选择要编辑的所需标记。
1. 在左侧导航菜单中选择&#x200B;**[!UICONTROL 扩展]**。
1. 从已安装的扩展列表中选择&#x200B;**[!UICONTROL Adobe Analytics]**，然后选择右侧的&#x200B;**[!UICONTROL 配置]**。
1. 确保启用复选框&#x200B;**[!UICONTROL 使用Activity Map]**。
1. 选择&#x200B;**[!UICONTROL 保存]**。
1. 如果需要，可将更改生成到库并将更改发布到生产环境。

有关详细信息，请参阅[Adobe Analytics扩展概述](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/analytics/overview)。

+++

+++Adobe Analytics JavaScript库(`AppMeasurement.js`)

Activity Map模块处理Activity Map数据收集，并包含在所有AppMeasurement库v1.6或更高版本中。 您可以检查`AppMeasurement.js`文件以确保包含该文件。

1. 导航到GitHub上的[最新Adobe Analytics AppMeasurement版本](https://github.com/adobe/appmeasurement/releases/latest)。
1. 下载压缩的AppMeasurement库文件，然后打开包含在内的`AppMeasurement.js`。
1. Activity Map模块包含在此文件顶部附近。 确保此模块包含在您的网站使用的AppMeasurement库中。

+++

## 可用的维度

当您同时为报表包和实施启用了Activity Map时，您可以在Analysis Workspace中开始使用以下维度：

* [[!UICONTROL Activity Map链接]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Activity Map地区]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Activity Map页面]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL 按地区划分的Activity Map链接]](/help/components/dimensions/activity-map-link-by-region.md)

## 下载并安装浏览器扩展或加载项

除了Analysis Workspace中可用的维度之外，您还可以将Activity Map数据作为网站上的叠加图查看。 要查看此叠加，请下载并安装Activity Map浏览器扩展或加载项。

**[!UICONTROL 工具]** > **[!UICONTROL Activity Map]** > **[!UICONTROL 下载Activity Map]**

此链接会将您转到浏览器支持的扩展或加载项市场，您可以在其中安装该扩展。 安装后，扩展或加载项会显示在浏览器的右上方，您可以在此处登录并启用叠加。
