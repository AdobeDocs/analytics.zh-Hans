---
title: 将 AppMeasurement 与 iframe 一起使用
description: 访问 iframe 中的 Adobe Analytics 变量或者在 iframe 中时访问父页面
feature: Implementation Basics
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 100%

---

# 将 AppMeasurement 与 iframe 一起使用

您可从子和父 iframe 引用 AppMeasurement 变量。必须在与 AppMeasurement 库所在的相同位置定义所有变量。以下示例说明了如何在 iframe 内部和外部设置基本 AppMeasurement 变量和方法。

如果您使用 Adobe Experience Platform 中的标记，请确保跟踪器对象可全局访问。请参阅 [Adobe Analytics 扩展概述](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=zh-Hans)。

>[!CAUTION]
>
>避免在父页面和 iframe 中同时包括 AppMeasurement 库。这样做会带来发送多个图像请求的风险，虚增报表并增加计费的服务器调用数。

## 访问位于 iframe 中的 AppMeasurement

您可通过 iframe 对象访问 AppMeasurement 变量。这些示例设置 [pageName](../vars/page-vars/pagename.md) 并使用两种不同的方法引用 iframe 对象来调用 [t() 方法](../vars/functions/t-method.md)。

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## 从 iframe 内部访问 AppMeasurement

您可从 iframe 的内部访问父页面上的 AppMeasurement 变量。此示例设置 [pageName](../vars/page-vars/pagename.md) 并使用 [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp) 属性调用 [t() 方法](../vars/functions/t-method.md)。

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## 使用 `postMessage` 和事件监听器

或者，您可以使用 `postMessage` 和事件监听器来设置变量。此方法不需要直接引用 iframe。

```js
// Place this code in your parent window
function listenMessage(e) {
    if(e.data == "Example page view call") {
        s.pageName = "Page name using postMessage";
        s.t();
    }
}
window.addEventListener("message", listenMessage, false);

// Place this code in the iframe
window.top.postMessage("Example page view call","https://example.com");
```

## 限制

* 与其他 JavaScript 代码一样，iframe 只能在域和协议匹配时通信。如果 iframe 内容位于与父页面不同的域，这些示例无法使用。
* 如果 AppMeasurement 位于 iframe 中，则 [`referrer`](../vars/page-vars/referrer.md) 变量设置为父 URL，而不是实际的引用 URL。您可以手动设置 `referrer` 变量来解决此问题。
* [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hans) 不会识别在 iframe 中触发的图像请求。
* Activity Map 不显示在 iframe 中单击的链接的热图。而是改为突出显示整个 iframe。
