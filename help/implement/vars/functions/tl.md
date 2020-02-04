---
title: tl
description: 向Adobe发送链接跟踪调用。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# tl

该方 `tl` 法是Adobe Analytics的一个重要核心组件。 它将获取页面上定义的所有Analytics变量，将其编译为图像请求，并将该数据发送到Adobe数据收集服务器。 它的工作方式与方 `t` 法类似，但此方法不会增加页面查看次数。 它对于跟踪链接和其他不会被视为完整页面加载的元素很有用。

如果启 `trackDownloadLinks` 用或 `trackExternalLinks` 启用了该功能，AppMeasurement会自动调用方法来 `tl` 发送下载链接和退出链接跟踪数据。 如果您的组织希望对要跟踪的链接及其行为拥有更多控制权，则可以手动调用 `tl` 该方法。 只能手动跟踪自定义链接。

## Adobe Experience Platform Launch中的链接跟踪调用

Launch有一个专用位置，可设置链接跟踪调用。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击“+”图标
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型”设置为] “发送信标”。
6. Click the `s.tl()` radio button.

不能在启动项中设置任何可选参数。

## s.tl()方法（在AppMeasurement和Launch自定义代码编辑器中）

当您要 `s.tl()` 向Adobe发送跟踪调用时，请调用该方法。

```js
s.tl();
```

或者，此方法接受多个参数：

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### 链接对象

链接对象参数确定浏览器在离开页面前是否等待500毫秒。 如果发送图像请求的时间早于 500 毫秒，则页面会立即导航到点击的链接。

> [!NOTE] AppMeasurement会自动为退出链 `useBeacon` 接启用变量，这使得现代浏览器不再需要此参数。 此参数在AppMeasurement的早期版本中更常用。

* `this`：最长等待 500 毫秒，以便给 AppMeasurement 一些时间来发送图像请求。默认值。
* `true`：不等待。

```JavaScript
// Include a 500ms delay
s.tl(this);

// Do not include a 500ms delay
s.tl(true);
```

### 链接类型

链接类型参数是一个单字母字符串，它决定链接跟踪调用的类型。 它与设置变量相 `linkType` 同。

```js
// Send a custom link
s.tl(true,"o");

// Send a download link
s.tl(true,"d");

// Send an exit link
s.tl(true,"e");
```

### 链接名称

链接名称参数是确定链接跟踪维值的字符串。 它与设置变量相 `linkName` 同。

```js
s.tl(true,"d","Example download link");
```

### 变量覆盖

允许您更改单次调用的变量值。有关更 [多信息](../../js/overrides.md) ，请参阅变量覆盖。

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## 示例和用例

直接在HTML链接中发送基本链接跟踪调用：

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

使用JavaScript进行基本的链接跟踪调用：

```JavaScript
s.tl(true,"o","Example Link");
```

### 在自定义函数中进行链接跟踪调用

您可以将链接跟踪代码合并到页面上或链接 JavaScript 文件中定义的独立 JavaScript 函数中。然后，可以在每个链接的 onClick 函数中进行调用。在JavaScript文件中设置以下内容：

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

然后，您可以在需要跟踪给定链接时调用该函数：

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

### 避免跟踪重复链接

如果 `trackDownloadLinks` 或启 `trackExternalLinks` 用了该功能，则正确的过滤器匹配时，AppMeasurement会自动发出链接跟踪调用。 如果您也手动调用这 `s.tl()` 些链接点击，则可以向Adobe发送重复数据。 重复数据会夸大报告编号，使其不太准确。

例如，以下函数将发送两个链接跟踪调用，用于同一链接单击（手动和自动下载链接）:

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

您可以使用以下修改的函数帮助防止重复的链接跟踪调用。 它首先检查链接对象是否存在，并且仅在链接对象为空字符串时发送手动链接跟踪调用。

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
