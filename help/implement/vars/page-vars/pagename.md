---
title: pageName
description: 您的网站中页面的名称。
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 81%

---


# pageName

`pageName` 变量通常会存储给定页面的名称。确定哪些个人页面最受欢迎时，此量度非常有用。This variable populates the [Page](/help/components/dimensions/page.md) dimension.

如果给定的页面跟踪调用中未定义此变量，则将改用 [`pageURL`](pageurl.md) 变量。

>[!NOTE]
>
>Adobe数据收集服务器从所有链接跟踪图 [像请求中](/help/implement/vars/functions/tl-method.md) 去除此维。 如果希望此维显示在链接跟踪点击中，请考虑将此维复制到 [eVar](evar.md)。

## Adobe Experience Platform Launch 中的页面名称

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置页面名称。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 页面名称]部分。

您可以将页面名称设置为任何字符串值，包括数据元素。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.pageName

`s.pageName` 变量是一个字符串，通常包含页面名称。其值的最大长度为 100 字节；超出此长度的值会被截断。如果此变量为空，则此截断会包含返回 `pageURL` 的实例。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

如果使用数 `digitalData` 据 [层](../../prepare/data-layer.md):

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
