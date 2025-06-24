---
title: trackExternalLinks
description: 对退出链接启用或禁用自动链接跟踪。
feature: Appmeasurement Implementation
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 60%

---

# trackExternalLinks

Adobe 提供跟踪出站链接的功能，无需为每个退出链接手动设置 [`tl()`](../functions/tl-method.md) 方法。如果要对退出链接使用自动链接跟踪，则启用此变量。

启用此功能后，AppMeasurement 会将任何点击的链接 URL 与 [`linkInternalFilters`](linkinternalfilters.md) 和 [`linkExternalFilters`](linkexternalfilters.md) 中的值进行比较。如果存在匹配项，则会自动触发退出链接跟踪调用。

## 使用Web SDK扩展启用或禁用点击收集

配置Web SDK时，使用[!UICONTROL 启用“单击数据收集”]复选框。 此复选框处理退出链接和下载链接。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击[!UICONTROL Adobe Experience Platform Web SDK]下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 在[!UICONTROL 数据收集]下，单击&#x200B;**[!UICONTROL 启用“单击数据收集”]**&#x200B;复选框。

## 启用或禁用手动实施Web SDK的点击收集

使用[`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans#clickCollectionEnabled)配置SDK。 字段是一个布尔值，用于确定是否自动收集与链接点击关联的数据。 其默认值为 `true`。如果要禁用自动链接跟踪，则将此值设置为`false`。 此设置处理下载链接和退出链接的自动链接跟踪。

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## 使用Adobe Analytics扩展跟踪出站链接

“跟踪出站链接”是配置 Adobe Analytics 扩展时位于[!UICONTROL 链接跟踪]折叠面板下的复选框。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;**配置**&#x200B;按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示[!UICONTROL 跟踪出站链接]复选框。

单击此复选框可启用自动退出链接跟踪。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.trackExternalLinks

`s.trackExternalLinks` 是一个布尔值，用于启用或禁用自动退出链接跟踪。如果您不想跟踪出站链接，或希望手动调用 `tl()` 方法以跟踪退出链接，则将此变量设置为 `false`。

```js
s.trackExternalLinks = true;
```
