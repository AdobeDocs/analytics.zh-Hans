---
description: 您可以根据 JavaScript AppMeasurement 文件中设置的参数自动跟踪文件下载和退出链接。
keywords: Analytics 实施
seo-description: 您可以根据 JavaScript AppMeasurement 文件中设置的参数自动跟踪文件下载和退出链接。
seo-title: s.tl() 函数 - 链接跟踪
solution: Analytics
subtopic: 链接跟踪
title: s.tl() 函数 - 链接跟踪
topic: 开发人员和实施
uuid: f28f071a-8820-4f74-89cd-fd233a21f22
translation-type: tm+mt
source-git-commit: 1ed1c6cd3fd6d29fa156cd4b2c4bdfe9120b3c61

---


# s.tl() 函数 - 链接跟踪

如果您的组织希望对要跟踪的链接及其行为拥有更多控制权，建议手动跟踪链接。 使用s.tl()函数手动发送具有所需精确内容的链接跟踪图像请求。 如果需要基本链接跟踪，请参阅配置变 `s.trackDownloadLinks` 量 `s.trackExitLinks` 和 [配置变量](c-variables/configuration-variables.md)。 无法自动跟踪自定义链接。

> [!NOTE] 链接跟踪代码通常与您的网站和报告需求密切相关。 Adobe建议以前的实施经验或实施顾问了解如何根据您的业务需求使用此功能。

## 语法和示例

基本语法：

`s.tl(`**`this`**`,`**`linkType`**`,`**`linkName`**`,`**`variableOverrides`**`,`**`doneAction`**`);`

基本示例：

```HTML
<!-- Basic HTML link example-->
<a href="example.html" onClick="s.tl(this,'o','Example link');">Click here</a>
```

```JavaScript
// Basic JavaScript link example
s.tl(this,'o','Example Link');
```

### this/true（必填）

第一个参数确定浏览器在离开页面前是否等待500毫秒。 如果图像请求在500毫秒之前发送，则页面会立即导航到单击的链接。

* `this`:等待500毫秒，为AppMeasurement留出时间以发送图像请求。 默认值。
* `true`:不要等。 如果链接从页面导航离开，则可能不会发送图像请求。

仅当链接离开页面时，才需要延迟。

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType（必需）

第二个参数具有三个有效值，具体取决于要捕获的链接类型。 它确定图像请求在Adobe Analytics中填充的维度。

* `d`: 文件下载
* `e`: 退出链接
* `o`:自定义链接

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName（必需）

此参数可以是最多100字节的任何自定义值。 它决定报表中的维值。

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides（可选）

允许您更改单个调用的变量值。 如果您使用doneAction参数且没有变量覆盖，请使用 `null`。

### doneAction（可选）

指定在跟踪链接调用完成后要执行的导航操作。 需要使用 `s.useForcedLinkTracking` 和 `s.forcedLinkTrackingTimeout`。 The doneAction variable can be the string `navigate`, which causes the method to set `document.location` to the href attribute of `linkObject`. doneAction 变量还可以是允许进行高级自定义的函数。

如果为锚记 事件中的 `onClick``false`doneAction 分配值，则必须在 `s.tl` 调用后返回 ，以防止默认的浏览器导航。To mirror the default behavior and follow the URL specified by the href attribute, provide a string of `navigate` as the doneAction. 或者，您可以提供自己的函数，并将此函数作为 doneAction 传递来处理导航事件。

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## 将JavaScript函数与链接跟踪结合使用

您可以将链接跟踪代码合并到页面上定义的自包含JavaScript函数或链接的JavaScript文件中。 然后，可在每个链接的onClick函数中进行调用。

```JavaScript
// Set in AppMeasurement file or page code
function trackClickInteraction(name){
    s.linkTrackVars='eVar16,eVar17';
    s.eVar16 = name;
    s.eVar17 = s.pageName;
    s.tl(true,'o',name);
}
```

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

## 避免重复链接计数 {#section_9C3F73DE758F4727943439DED110543C}

如果链接通常通过自动文件下载或退出链接跟踪来捕获，则链接可能会重复计数。 For example, if you are tracking PDF downloads automatically, an `s.tl` call results in a duplicate download count:

```JavaScript
function trackDownload(obj) {}
    s.tl(obj,'d','PDF Document');
}
```

为确保不会发生链接重复计数的情况，请使用下列经过修改的 JavaScript 函数：

```JavaScript
function linkCode(obj) {
    var lt = obj.href != null ? s.lt(obj.href) : "";
    if (lt=="") {
        s.tl(obj,'d','PDF Document');
    }
}
```
