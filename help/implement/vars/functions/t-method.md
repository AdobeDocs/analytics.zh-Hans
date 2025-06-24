---
title: t
description: 向 Adobe 发送页面查看跟踪调用。
feature: Appmeasurement Implementation
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 56%

---

# t()

`t()` 方法是 Adobe Analytics 的一个重要核心组件。它将获取页面上定义的所有 Analytics 变量，将其编译为图像请求，并将该数据发送到 Adobe 数据收集服务器。

例如，请考虑以下 JavaScript 代码：

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

运行 `t()` 方法可获取所有已定义的 Analytics 变量，并根据这些变量制定 URL。某些 Analytics 变量可确定图像的 URL，而其他变量则可确定查询字符串参数值。

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20item
```

Adobe 会接收图像请求，然后解析请求标头、URL 和查询字符串参数。然后，数据收集服务器会返回透明的 1x1 像素图像，该图像会隐式显示在您的网站上。

## 使用Web SDK扩展发送事件

使用操作配置向Adobe发送XDM事件数据。 数据流接收此数据，应用任何配置的映射，并将该数据转发到Adobe Analytics（如果它是向此数据流添加的服务）。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
1. 在[!UICONTROL 操作]下，单击所需的操作或单击&#x200B;**“+”**&#x200B;图标以添加操作。
1. 将[!UICONTROL 扩展]下拉列表设置为&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**，将[!UICONTROL 操作类型]设置为&#x200B;**[!UICONTROL 发送事件]**。

## 手动发送事件以实施Web SDK

使用`sendEvent`命令将数据发送到Adobe。 数据流接收此数据，应用任何配置的映射，并将该数据转发到Adobe Analytics（如果它是向此数据流添加的服务）。

```js
alloy("sendEvent", {
  "xdm": {}
});
```

有关详细信息，请参阅Web SDK文档中的[`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview)。

## 使用Adobe Analytics扩展的“页面查看跟踪”调用

Adobe Experience Platform数据收集中的Adobe Analytics扩展有一个专用位置，用于设置页面查看跟踪调用。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
1. 在[!UICONTROL 操作]下，单击所需的操作或单击&#x200B;**“+”**&#x200B;图标以添加操作。
1. 将[!UICONTROL 扩展]下拉列表设置为&#x200B;**[!UICONTROL Adobe Analytics]**，将[!UICONTROL 操作类型]设置为&#x200B;**[!UICONTROL 发送信标]**。
1. 单击 `s.t()` 单选按钮。

## AppMeasurement中的s.t()方法和Analytics扩展自定义代码编辑器

当您要向 Adobe 发送跟踪调用时，请调用 `s.t()` 方法。

```js
s.t();
```

或者，您也可以将对象用作参数来覆盖变量值。有关更多信息，请参阅[变量覆盖](../../js/overrides.md)。

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>AppMeasurement 的早期版本使用几行代码调用此函数。过去，其他代码可适应不同浏览器的解决方法。现代浏览器中的标准化和最佳实践不再需要此代码块。现在只需要方法调用 `s.t()`。
