---
title: doPlugins
description: 在编译点击并将其发送到 Adobe 之前配置逻辑。
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---

# doPlugins

`doPlugins` 变量会用作“最后一次调用”，以便在您的实施中设置值。如果启用了 [`usePlugins`](../config-vars/useplugins.md)，它将在编译任何类型的图像请求并将其发送到 Adobe 之前自动运行，包括：

* 所有页面查看 ([`t()`](t-method.md)) 调用
* 所有链接跟踪 ([`tl()`](tl-method.md)) 调用，包括自动下载链接和退出链接

在编译图像请求并将其发送到 Adobe 之前，使用 `doPlugins` 变量调用插件代码并设置最终变量值。

## 使用 Adobe Experience Platform 中的标记的“插件”

数据收集 UI 中没有专门的字段来使用此变量。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和自定义代码编辑器中的 s.doPlugins

将 `s.doPlugins` 变量设置为包含所需代码的函数。当您进行跟踪调用时，该函数会自动运行。

```js
s.doPlugins = function() {/* Desired code */};
```

>[!NOTE]
>
>在您的实施中仅一次将函数设置为 `doPlugins` 变量。如果多次设置 `doPlugins` 变量，则仅会使用最新的代码。

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

>[!NOTE]
>
>AppMeasurement 的先前版本具有的 `doPlugins()` 代码略有不同。Adobe 建议将上述格式作为最佳实践。
