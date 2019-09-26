---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.doPlugins

 变量是 函数的一个引用，允许在 JavaScript 文件内的合适位置调用 函数。

The *`s_doPlugins`* function is called each time any of the following occurs:

* 函 *`t()`* 数被调用
* The  function is called *`tl()`*
* 点击退出或下载链接时
* 点击由访客 ClickMap 跟踪的任意页面元素时

The *`doPlugins`*&#x200B;函数用于运行自定义例程，以收集或更改数据。If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. For example, if your object name is s_mc, the  function should be called s_mc_doPlugins.*`s_doPlugins`*

## 语法和可能值

The  function should not be in quotes, and  should always be assigned to the exact name of the  function (if that function is renamed).*`s_doPlugins`**`doPlugins`**`s_doPlugins`*

```js
s.doPlugins=s_doPlugins;
```

## 示例

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

## 配置设置

无

## 缺陷、问题和提示

* 只有当您与其他客户共享内容或提取其他客户的内容时，才需要更改对象名称（例如从 s 更改为 s_mc）。重命名 *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* 如果您意外地开始从其他Adobe客户处提取内容，并且您的 *`s_doPlugins`* 函数正被覆盖，则可以只重命名该函数，而不更改 *`s_doPlugins`* 对象名称。 最好的解决方案是在同一页面上使用与 JavaScript 文件不同的其他对象名称，但并不要求这样做。