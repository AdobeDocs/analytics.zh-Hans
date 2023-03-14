---
title: tl
description: 向 Adobe 发送链接跟踪调用。
feature: Variables
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
source-git-commit: 8ff414efff302adfee42f192e781a8dec5c42902
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 80%

---

# tl

`tl()` 方法是 Adobe Analytics 的一个重要核心组件。它将获取页面上定义的所有 Analytics 变量，将其编译为图像请求，并将该数据发送到 Adobe 数据收集服务器。它的工作方式与 [`t()`](t-method.md) 方法类似，但此方法不会增加页面查看次数。它对于跟踪链接和其他不会被视为完整页面加载的元素很有用。

如果已启用 [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) 或 [`trackExternalLinks`](../config-vars/trackexternallinks.md)，AppMeasurement 会自动调用 `tl()` 方法来发送下载链接和退出链接跟踪数据。如果贵组织希望对要跟踪的链接及其行为增强控制，则可以手动调用 `tl()` 方法。只能手动跟踪自定义链接。

## 使用Web SDK进行链接跟踪

Web SDK不区分页面查看调用和链接跟踪调用；两者都使用 `sendEvent` 命令。 如果您希望Adobe Analytics将给定XDM事件计为链接跟踪调用，请确保您的XDM数据包含或映射到 `web.webInteraction.name`， `web.webInteraction.URL`、和 `web.webInteraction.type`.

* 链接名称映射到 `web.webInteraction.name`.
* 链接URL映射到 `web.webInteraction.URL`.
* 链接类型映射到 `web.webInteraction.type`. 有效值包括 `other`（自定义链接）、`download`（下载链接）和 `exit`（退出链接）。

```js
alloy("sendEvent", {
  "xdm": {
    "web": {
      "webInteraction": {
        "name": "My Custom Link",
        "URL": "https://example.com",
        "type": "other"
      }
    }
  }
});
```

## 使用Adobe Analytics扩展进行链接跟踪

Adobe Analytics扩展有一个专门用于设置链接跟踪调用的位置。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
1. 下 [!UICONTROL 操作]，单击所需的操作或单击 **&#39;+&#39;** 图标以添加操作。
1. 设置 [!UICONTROL 扩展] 下拉至 **[!UICONTROL Adobe Analytics]**，以及 [!UICONTROL 操作类型] 到 **[!UICONTROL 发送信标]**.
1. 单击 `s.tl()` 单选按钮。

不能在Analytics扩展中设置任何可选参数。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.tl()方法

当您要向 Adobe 发送跟踪调用时，请调用 `s.tl()` 方法。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### 链接对象（必需）

链接对象参数可确定浏览器在离开页面之前是否需要等待长达 500 毫秒。如果发送图像请求的时间早于 500 毫秒，则页面会立即导航到点击的链接。

>[!NOTE]
>
>AppMeasurement 会自动为退出链接启用 [`useBeacon`](../config-vars/usebeacon.md) 变量，这使得现代浏览器不再需要此参数。此参数在 AppMeasurement 的早期版本中比较常用。

* `this`：最长等待 500 毫秒，以便给 AppMeasurement 一些时间来发送图像请求。默认值。
* `true`：不等待。

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### 链接类型（必需）

链接类型参数是一个单字母字符串，可确定链接跟踪调用的类型。具有三个有效值。

* `o`：该链接是一个[自定义链接](/help/components/dimensions/custom-link.md)。
* `d`：该链接是一个[下载链接](/help/components/dimensions/download-link.md)。
* `e`：该链接是一个[退出链接](/help/components/dimensions/exit-link.md)。

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### 链接名称（推荐）

链接名称参数是一个可确定链接跟踪维度项目的字符串。当在报告中使用[自定义链接](/help/components/dimensions/custom-link.md)、[下载链接](/help/components/dimensions/download-link.md)或[退出链接](/help/components/dimensions/exit-link.md)维度时，此字符串中包含维度项目。如果未设置此参数，则使用 [linkURL](../config-vars/linkurl.md) 变量。

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### 变量覆盖（可选）

允许您更改单次调用的变量值。有关更多信息，请参阅[变量覆盖](../../js/overrides.md)。

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## 示例和用例

直接在 HTML 链接中发送基本链接跟踪调用：

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

使用 JavaScript 通过方法参数进行基本链接跟踪调用：

```JavaScript
s.tl(true,"o","Example link");
```

### 在自定义函数中进行链接跟踪调用

您可以将链接跟踪代码合并到页面上或链接 JavaScript 文件中定义的独立 JavaScript 函数中。然后，可以在每个链接的 onClick 函数中进行调用。在 JavaScript 文件中设置以下内容：

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

如果已启用 `trackDownloadLinks` 或 `trackExternalLinks`，则在正确的过滤器匹配的情况下，AppMeasurement 会自动进行链接跟踪调用。如果您还为这些链接点击手动调用 `s.tl()`，则可以向 Adobe 发送重复数据。重复数据会虚增报表数量，使其不太准确。

例如，以下函数将为同一链接点击（手动和自动下载链接）发送两个链接跟踪调用：

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

您可以使用以下修改的函数防止出现重复的链接跟踪调用。它首先会检查链接对象是否存在，并且仅在链接对象为空字符串时才发送手动链接跟踪调用。

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
