---
title: pageName
description: 您的网站中页面的名称。
feature: Variables
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 81%

---

# pageName

`pageName` 变量通常会存储给定页面的名称。确定哪些个人页面最受欢迎时，此量度非常有用。此变量填充[页面](/help/components/dimensions/page.md)维度。

如果给定的页面跟踪调用中未定义此变量，则将改用 [`pageURL`](pageurl.md) 变量。

>[!NOTE]
>
>Adobe 数据收集服务器从所有[链接跟踪](/help/implement/vars/functions/tl-method.md)图像请求中剥离此维度。如果您要在链接跟踪点击中显示此维度，请考虑将此维度复制到 [eVar](evar.md) 中。

## 使用Web SDK的页面名称

页面为 [已为Adobe Analytics映射](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在XDM字段下 `web.webPageDetails.name`.

## 使用Adobe Analytics扩展的页面名称

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置页面名称。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 设置 [!UICONTROL 扩展名] Adobe Analytics的下拉列表，以及 [!UICONTROL 操作类型] 到 [!UICONTROL 设置变量].
6. 找到[!UICONTROL 页面名称]部分。

您可以将页面名称设置为任何字符串值，包括数据元素。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.pageName

`s.pageName` 变量是一个字符串，通常包含页面名称。其值的最大长度为 100 字节；超出此长度的值会被截断。如果此变量为空，则此截断会包含返回 `pageURL` 的实例。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

如果使用`digitalData` [数据层](../../prepare/data-layer.md)：

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
