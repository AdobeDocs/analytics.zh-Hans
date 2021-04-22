---
title: t
description: 向 Adobe 发送页面查看跟踪调用。
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '269'
ht-degree: 100%

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
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe 会接收图像请求，然后解析请求标头、URL 和查询字符串参数。然后，数据收集服务器会返回透明的 1x1 像素图像，该图像会隐式显示在您的网站上。

## Adobe Experience Platform Launch 中的“页面查看跟踪调用”

Launch 有一个专用位置，用于设置页面查看跟踪调用。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击“+”图标
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为“发送信标”。
6. 单击 `s.t()` 单选按钮。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.t() 方法

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
