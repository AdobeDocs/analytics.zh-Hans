---
title: 将AppMeasurement与iframe结合使用
description: 在iframe中访问iframe或父页面中的Adobe Analytics变量。
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
translation-type: tm+mt
source-git-commit: 40bf2bbb522a94a678d0da1a645d83a5121c93d0
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 6%

---

# 将AppMeasurement与iframe结合使用

您可以从子和父数据帧中引用AppMeasurement变量。 必须在AppMeasurement库所在的位置定义所有变量。 以下示例说明如何在iframe内外设置基本的AppMeasurement变量和方法。

如果使用Adobe Experience Platform Launch，请确保跟踪器对象可全局访问。 请参阅启动用户指南中的[Adobe Analytics扩展概述](https://docs.adobe.com/content/help/zh-Hans/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html)。

>[!CAUTION]
>
>避免在父页面和iframe上都包含AppMeasurement库。 这样做会导致发送多个图像请求、增加报告和增加可计费服务器调用的风险。

## 访问驻留在iframe中的AppMeasurement

您可以通过iframe对象访问AppMeasurement变量。 这些示例设置[pageName](../vars/page-vars/pagename.md)并使用两种不同方法调用[t()方法](../vars/functions/t-method.md)引用iframe对象。

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## 从iframe中访问AppMeasurement

您可以从iframe中访问父页面上的AppMeasurement变量。 此示例设置[pageName](../vars/page-vars/pagename.md)并使用[`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp)属性调用[t()方法](../vars/functions/t-method.md)。

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## 使用`postMessage`和事件侦听器

或者，也可以使用`postMessage`和事件侦听器设置变量。 此方法不需要对iframe的直接引用。

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

* 与其他JavaScript代码一样，iframe只能在域和协议匹配时进行通信。 如果iframe内容位于父级以外的其他域上，则这些示例不起作用。
* 如果AppMeasurement驻留在iframe中，则[`referrer`](../vars/page-vars/referrer.md)变量将设置为父URL，而不是实际的引荐URL。 您可以手动设置`referrer`变量来解决此问题。
* [Adobe Experience Cloud调试器](https://docs.adobe.com/content/help/zh_CN/debugger/using/experience-cloud-debugger.html)无法识别在iframe中触发的图像请求。
* Activity Map不会在文件中单击的链接上显示热图。 此时会高亮显示整个iframe。
