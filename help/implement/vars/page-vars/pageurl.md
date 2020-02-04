---
title: pageUrl
description: 覆盖站点上自动收集的页面URL。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# pageUrl

AppMeasurement会在每次点击时自动收集页面URL。 如果要覆盖由AppMeasurement自动收集的页面URL，可使用此变量。 在大多数情况下，您无需设置此变量。

> [!NOTE] 此变量不是Analysis Workspace中的可用维。 它仅在数据仓库和数据源中可用。 如果要在Analysis Workspace中将页面URL用作维度，请考虑在每次点击时 `pageURL` 将变量传递到eVar中。

有时URL大于255字节。 AppMeasurement对图 `g` 像请求中URL的前255字节使用查询字符串参数。 如果URL大于255字节，则URL的其余部分存储在查询字符串 `-g` 参数中。 URL中的协议和查询字符串包含在此变量中。

## Adobe Experience Platform Launch中的页面URL

Launch会自动填充页面URL。 但是，您可以在配置Analytics扩展时（全局变量）或根据规则设置页面URL覆盖。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到“ [!UICONTROL 页面URL] ”部分。

可以将页面URL设置为任何字符串值。

## AppMeasurement和Launch自定义代码编辑器中的s.pageURL

变 `s.pageURL` 量是包含页面URL的字符串。 AppMeasurement会自动收集此变量，但您可以根据需要覆盖其值。

```js
s.pageURL = "https://example.com";
```

如果要将页面URL用作报表中的维，请考虑在实施中使用以下内容：

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```
