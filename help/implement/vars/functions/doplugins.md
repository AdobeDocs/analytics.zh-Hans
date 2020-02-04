---
title: doPlugins
description: 在编译点击并发送到Adobe之前配置逻辑。
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# doPlugins

该 `doPlugins` 变量充当“最后调用”，用于在您的实现中设置值。 如果 `usePlugins` 是 `true`，则它会在编译和发送任何类型的图像请求之前自动运行，包括：

* 所有页面查看(`t`)调用
* 所有链接跟踪(`tl`)调用，包括自动下载链接和退出链接

使用该 `doPlugins` 变量调用插件代码并在编译图像请求并将其发送到Adobe之前设置最终变量值。

## Adobe Experience Platform Launch中的插件

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement中的s.doPlugins和启动自定义代码

将变量设 `s.doPlugins` 置为包含所需代码的函数。 当您进行跟踪调用时，该函数会自动运行。

```js
s.doPlugins = function() {/* Desired code */};
```

> [!NOTE] 在您的实施中，将函 `doPlugins` 数设置为变量仅一次。 如果多次设 `doPlugins` 置变量，则只使用最新的代码。

## 示例

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

> [!NOTE] AppMeasurement的先前版本的代码略有 `doPlugins()` 不同。 Adobe建议将上述格式作为最佳实践。
