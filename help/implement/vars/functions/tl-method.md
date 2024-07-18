---
title: tl
description: 向 Adobe 发送链接跟踪调用。
feature: Variables
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
role: Admin, Developer
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 62%

---

# tl

`tl()` 方法是 Adobe Analytics 的一个重要核心组件。它将获取页面上定义的所有 Analytics 变量，将其编译为图像请求，并将该数据发送到 Adobe 数据收集服务器。它的工作方式与 [`t()`](t-method.md) 方法类似，但此方法不会增加页面查看次数。它对于跟踪链接和其他不会被视为完整页面加载的元素很有用。

如果已启用 [`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) 或 [`trackExternalLinks`](../config-vars/trackexternallinks.md)，AppMeasurement 会自动调用 `tl()` 方法来发送下载链接和退出链接跟踪数据。如果贵组织希望对要跟踪的链接及其行为增强控制，则可以手动调用 `tl()` 方法。只能手动跟踪自定义链接。

## 使用Web SDK进行链接跟踪

Web SDK不区分页面查看调用和链接跟踪调用；两者都使用`sendEvent`命令。

如果您使用XDM对象并希望Adobe Analytics将给定事件计为链接跟踪调用，请确保您的XDM数据包括：

* 链接名称：已映射到`xdm.web.webInteraction.name`。
* 链接URL：映射到`xdm.web.webInteraction.URL`。
* 链接类型：映射到`xdm.web.webInteraction.type`。 有效值包括 `other`（自定义链接）、`download`（下载链接）和 `exit`（退出链接）。

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

如果您使用数据对象，并且希望Adobe Analytics将给定事件计为链接跟踪调用，请确保您的数据对象包括：

* 链接名称：已映射到`data.__adobe.analytics.linkName`。
* 链接URL：映射到`data.__adobe.analytics.linkURL`。
* 链接类型：映射到`data.__adobe.analytics.linkType`。 有效值包括 `o`（自定义链接）、`d`（下载链接）和 `e`（退出链接）。

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "linkName": "My custom link",
        "linkURL": "https://example.com",
        "linkType": "o"
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
1. 在[!UICONTROL 操作]下，单击所需的操作或单击&#x200B;**“+”**&#x200B;图标以添加操作。
1. 将[!UICONTROL 扩展]下拉列表设置为&#x200B;**[!UICONTROL Adobe Analytics]**，将[!UICONTROL 操作类型]设置为&#x200B;**[!UICONTROL 发送信标]**。
1. 单击 `s.tl()` 单选按钮。

您不能在Analytics扩展中设置任何可选参数。

## AppMeasurement中的s.tl()方法和Analytics扩展自定义代码编辑器

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

您可以将链接跟踪代码合并到一个独立的JavaScript函数中。 然后，可以在每个链接的`onClick`函数中进行调用。 在 JavaScript 文件中设置以下内容：

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

>[!NOTE]
>间接调用`tl()`方法可能会降低Activity Map叠加报表的便利性。 必须单击每个链接才能使用链接元素注册函数。 但是，Workspace中的Activity Map维度也受到相同的跟踪。

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

### 将`tl()`方法用于Activity Map

您可以使用`tl()`方法来跟踪自定义元素并配置动态内容的叠加图呈现。 `linkName`参数还用于设置[Activity Map链接](/help/components/dimensions/activity-map-link.md)维度。

如果从HTML元素的单击事件直接调用`tl()`方法，则Activity Map可以在加载网页时显示该元素的叠加图。 例如：

```html
<a href="index.html" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

如果不是从HTML元素的单击事件直接调用`tl()`方法，则Activity Map只能在单击该元素后显示叠加。 例如：

```html
<a href="index.html" onclick="someFn(event);">Example link text</a>
<script>
  function someFn (event) {
    s.tl(event.srcElement,'o','Example custom link');
  }
</script>
```
