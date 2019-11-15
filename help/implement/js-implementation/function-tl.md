---
description: 您可以根据 JavaScript AppMeasurement 文件中设置的参数自动跟踪文件下载和退出链接。
keywords: Analytics Implementation
solution: Analytics
subtopic: Link tracking
title: s.tl() 函数 - 链接跟踪
topic: Developer and implementation
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.tl() 函数 - 链接跟踪

如果您的组织希望更好地控制要跟踪的链接及其行为，则建议使用手动链接跟踪。使用 s.tl() 函数来手动发送包含所需确切内容的链接跟踪图像请求。如果只需要使用基本链接跟踪，则请参阅[配置变量](c-variables/configuration-variables.md)下的 `s.trackDownloadLinks` 和 `s.trackExternalLinks`。无法自动跟踪自定义链接。

> [!NOTE] 链接跟踪代码通常特定于您的网站和报告需求。Adobe 建议您借鉴以前的实施经验或咨询实施顾问，以了解如何根据您的业务需求使用此功能。

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

第一个参数可确定浏览器在离开页面之前是否需要最长等待 500 毫秒。如果发送图像请求的时间早于 500 毫秒，则页面会立即导航到点击的链接。

* `this`：最长等待 500 毫秒，以便给 AppMeasurement 一些时间来发送图像请求。默认值。
* `true`：不等待。如果链接离开页面，可能不会发送图像请求。

仅当链接离开页面时，才需要延迟。

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType（必填）

第二个参数具有三个有效值，具体取决于您要捕获的链接类型。它可确定 Adobe Analytics 中图像请求填充的维度。

* `d`: 文件下载
* `e`: 退出链接
* `o`：自定义链接

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName（必填）

此变量可以是任何自定义值，其长度最多为 100 个字符。它可确定报表中的维度值。

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides（可选）

允许您更改单次调用的变量值。如果使用 doneAction 参数并且没有变量覆盖，则请使用 `null`。

### doneAction（可选）

指定在跟踪链接调用完成后要执行的导航操作。需要使用 `s.useForcedLinkTracking` 和 `s.forcedLinkTrackingTimeout`。doneAction 变量可以是字符串 `navigate`，这会导致该方法将 `document.location` 设置为 `linkObject` 的 href 属性。doneAction 变量还可以是允许进行高级自定义的函数。

如果为锚记 事件中的 `onClick``false`doneAction 分配值，则必须在 `s.tl` 调用后返回 ，以防止默认的浏览器导航。要生成默认行为的镜像并导航 href 属性指定的 URL，请提供字符串 `navigate` 作为 doneAction。或者，您可以提供自己的函数，并将此函数作为 doneAction 传递来处理导航事件。

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## 将 JavaScript 函数与链接跟踪结合使用

您可以将链接跟踪代码合并到页面上或链接 JavaScript 文件中定义的独立 JavaScript 函数中。然后，可以在每个链接的 onClick 函数中进行调用。

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

在自动文件下载或退出链接跟踪通常会捕获链接的情况下，可能会将链接计为两次。例如，如果您自动跟踪 PDF 下载，以下 `s.tl` 调用会导致下载计数重复：

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
