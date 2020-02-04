---
title: 使用 AJAX 实施
description: 了解如何使用AJAX在站点上实施Adobe Analytics。
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# 使用 AJAX 实施

AJAX是一种使用JavaScript和HTML来清除和生成内容而无需加载新页面的做法。

Adobe Analytics通常依赖页面重新加载来重置Analytics跟踪对象。 每次导航到其他URL时，所有Analytics变量都会重置，并且可以再次定义。 在站点上使用AJAX时，请围绕缺少页面刷新调整实施，以确保点击之间的数据不会错误地保留。

一旦您制定了清除变量值的措施，在使用AJAX的站点上实施Adobe Analytics与其他实施方法大体相同。

## 确定交互和点击类型

由于使用AJAX的页面通常不会重新加载，因此用户可以对您的站点进行多个交互。 实施Adobe Analytics时，请确保将页面查看与链接跟踪调用区分开来。 对于用户在您的网站上进行的每次交互，请考虑以下问题：

*当用户与我的站点交互时，该交互是否会改变页面上的内容以确定为新页面？*

* 如果答案是“ **是**”，请考虑使用页面查看跟踪调用(`s.t()`)。
* 如果答案为否 ****，请考虑使用链接跟踪调用(`s.tl()`)跟踪该交互。

> [!NOTE] 并非需要记录所有交互或点击。 请仔细考虑哪些操作最重要，并相应地将数据发送到Adobe。

## 清除每页上的变量

变量值在使用AJAX的页面上会一直存在，因为页面不会重新加载。 因此，需要特殊调整以清除变量值，这样它们就不会在点击中错误地保留。 Adobe提供了一 [`clearVars`](../vars/functions/clearvars.md) 个函数以轻松清除变量值。 确保在将每次点击发送到Adobe之后以及在为下一次点击设置变量值之前使用此函数。

> [!TIP] 该函 `clearVars()` 数在H代码中不可用。 如果尚未升级到AppMeasurement，请将每个Analytics变量值设置为空字符串。

## 示例

以下示例使用简单的JavaScript清除现有变量值，设置新值，然后向Adobe发送图像请求：

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
