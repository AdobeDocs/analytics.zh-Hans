---
title: pageUrl
description: 覆盖网站上自动收集的页面 URL。
feature: Variables
exl-id: 411f894d-c31f-4d07-9568-b0b02786735d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 84%

---

# pageUrl

AppMeasurement 会在每次点击时自动收集页面 URL。如果要覆盖由 AppMeasurement 自动收集的页面 URL，可使用此变量。在大多数情况下，您无需设置此变量。

>[!NOTE]
>
>此变量不是 Analysis Workspace 中的可用维度。它只能在 Data Warehouse 和数据馈送中使用。此外，Adobe 数据收集服务器从所有[链接跟踪](/help/implement/vars/functions/tl-method.md)图像请求中剥离此维度。如果您要在 Analysis Workspace 中使用页面 URL 作为维度，或者希望在链接跟踪点击中使用此维度，请考虑在每次点击中将 `pageURL` 变量传递到 [eVar](evar.md)。

## 使用Web SDK的页面URL

页面URL为 [已为Adobe Analytics映射](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在XDM字段下 `web.webPageDetails.URL`.

## 使用Adobe Analytics扩展的“页面URL”

Adobe Experience Platform数据收集中的Analytics扩展会自动填充页面URL。 但是，您可以在配置 Analytics 扩展时（全局变量）或根据规则设置页面 URL 覆盖。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到&#x200B;**[!UICONTROL 规则]**&#x200B;选项卡，然后单击所需的规则（或创建规则）。
4. 在&#x200B;**[!UICONTROL 操作]**&#x200B;下，单击现有的 **[!UICONTROL Adobe Analytics - 设置变量]**&#x200B;操作或单击“+”图标。
5. 将&#x200B;**[!UICONTROL 扩展]**&#x200B;下拉列表设置为 Adobe Analytics，将&#x200B;**[!UICONTROL 操作类型]**&#x200B;设置为&#x200B;**[!UICONTROL 设置变量]**。
6. 找到&#x200B;**[!UICONTROL 页面 URL]** 部分。

可以将页面 URL 设置为任何字符串值。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.pageURL

`s.pageURL` 变量是一个包含页面 URL 的字符串。AppMeasurement 会自动收集此变量，但您可以根据需要覆盖其值。

```js
s.pageURL = "https://example.com";
```

如果要在报表中将页面 URL 用作维度，请考虑在实施中使用以下内容：

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

如果使用`digitalData` [数据层](../../prepare/data-layer.md)：

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```
