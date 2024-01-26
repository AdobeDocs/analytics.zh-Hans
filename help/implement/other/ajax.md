---
title: 使用 AJAX 实施
description: 了解如何在使用 AJAX 的网站上实施 Adobe Analytics。
feature: Implementation Basics
exl-id: 3286bf97-3a66-4f68-9053-bf84269962fd
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 100%

---

# 使用 AJAX 实施

AJAX 是一种使用 JavaScript 和 HTML 来清除和生成内容的做法，不会加载新页面。

Adobe Analytics 通常需要通过重新加载页面来重置 Analytics 跟踪对象。每次导航到其他 URL 时，所有 Analytics 变量都会重置，并且可再次定义。在网站上使用 AJAX 时，请针对缺乏页面刷新调整实施，以确保数据不会在点击之间错误地保留。

一旦您设定了清除变量值的措施，在使用 AJAX 的网站上实施 Adobe Analytics 与其他实施方法大体相同。

## 确定交互和点击类型

由于使用 AJAX 的页面通常不会重新加载，因此用户可以在您的网站上进行多种交互。实施 Adobe Analytics 时，请确保将页面查看与链接跟踪调用区分开来。对于用户在您的网站上进行的每次交互，请考虑以下问题：

*当用户与我的网站交互时，该交互是否会导致页面上的内容发生足够大的变化，以致于能将该页面视为新页面？*

* 如果答案为&#x200B;**是**，请考虑使用页面查看跟踪调用 (`s.t()`)。
* 如果答案为&#x200B;**否**，请考虑使用链接跟踪调用 (`s.tl()`) 跟踪该交互。

>[!NOTE]
>
>并非需要记录所有交互或点击。请仔细考虑哪些操作是非常重要因而需要跟踪的，并据此将相应数据发送到 Adobe。

## 清除每个页面上的变量

因为使用 AJAX 的页面不会重新加载，因此变量值会一直保留在页面上。为此，需要进行特殊处理来清除变量值，以免变量值在点击之间错误地保留。为轻松清除变量值，Adobe 提供了 [`clearVars`](../vars/functions/clearvars.md) 函数。确保在将每个点击发送到 Adobe 之后以及在为下一个点击设置变量值之前使用此函数。

>[!TIP]
>
>`clearVars()` 函数在 H 代码中不可用。如果尚未升级到 AppMeasurement，请将每个 Analytics 变量值设置为空字符串。

## 示例

以下示例使用简单的 JavaScript 清除现有变量值，设置新值，然后向 Adobe 发送图像请求：

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

下面的示例显示了 JQuery `done` 函数的 `.ajax` 回调中的一个跟踪调用：

```js
$.ajax({
  url: "example.html",
  dataType: "html"
})
  .done(function( response ) {
    $( "#content" ).html( response );
  s.clearVars();
  s.pageName = $( "h1:first" ).text();
  s.t();
  });
```
