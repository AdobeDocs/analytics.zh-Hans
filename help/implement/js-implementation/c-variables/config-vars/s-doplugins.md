---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---



# s.doPlugins

 变量是 函数的一个引用，允许在 JavaScript 文件内的合适位置调用 函数。

出现以下任何情况时，都会调用 *`s_doPlugins`* 函数：

* 调用 *`t()`* 函数
* 调用 *`tl()`* 函数
* 点击退出或下载链接时
* 点击由访客 ClickMap 跟踪的任意页面元素时

The *`doPlugins`*&#x200B;函数用于运行自定义例程，以收集或更改数据。如果您使用“s”以外的对象名称，请确保正确重命名 *`s_doPlugins`*。例如，如果对象名为 s_mc，则 *`s_doPlugins`* 函数应称为 s_mc_doPlugins。

## 语法和可能值

*`s_doPlugins`* 函数不能用引号括起来，且应始终为 *`doPlugins`* 分配 *`s_doPlugins`* 函数的确切名称（如果该函数已重命名）。

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

* 只有当您与其他客户共享内容或提取其他客户的内容时，才需要更改对象名称（例如从 s 更改为 s_mc）。重命名 *`s_doPlugins`* 函数为 [!UICONTROL s_mc_doPlugins]，以确保其他客户的 JavaScript 文件不会覆盖您的 *`doPlugins`* 函数。

* 如果您意外地开始从其他 Adobe 客户提取内容，且您的 *`s_doPlugins`* 函数被覆盖，则只需简单地重命名 *`s_doPlugins`* 函数即可，而无需更改对象名称。最好的解决方案是在同一页面上使用与 JavaScript 文件不同的其他对象名称，但并不要求这样做。