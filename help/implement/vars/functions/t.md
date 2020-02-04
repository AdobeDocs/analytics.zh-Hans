---
title: t
description: 向Adobe发送页面查看跟踪调用。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# t

该方 `t` 法是Adobe Analytics的一个重要核心组件。 它将获取页面上定义的所有Analytics变量，将其编译为图像请求，并将该数据发送到Adobe数据收集服务器。

例如，请考虑以下JavaScript代码：

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension value";

// Compile the variables on the page into an image request to Adobe
s.t();
```

运行该方 `t` 法会定义所有Analytics变量，并根据这些变量制定URL。 某些Analytics变量决定图像的URL，而其他变量则决定查询字符串参数值。

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe接收图像请求，然后分析请求标题、URL和查询字符串参数。 然后，数据收集服务器返回透明的1x1像素图像，该图像在您的站点上不可见地显示。

## Adobe Experience Platform Launch中的页面查看跟踪调用

Launch有一个专用位置，用于设置页面查看跟踪调用。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击“+”图标
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型”设置为] “发送信标”。
6. Click the `s.t()` radio button.

## s.t()方法（在AppMeasurement和Launch自定义代码编辑器中）

当您要 `s.t()` 向Adobe发送跟踪调用时，请调用该方法。

```js
s.t();
```

或者，您也可以将对象用作参数来覆盖变量值。 有关更 [多信息](../../js/overrides.md) ，请参阅变量覆盖。

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

> [!NOTE] AppMeasurement的早期版本使用几行代码调用此函数。 以前，附加的代码可以满足不同浏览器的解决办法。 现代浏览器中的标准化和最佳实践不再需要此代码块。 现在只需要方 `s.t()` 法调用。
