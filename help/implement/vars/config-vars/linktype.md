---
title: linkType
description: 使用linkType变量确定点击属于哪个链接跟踪维。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkType

链接跟踪点击可以填充以下三个维之一：

* 自定义链接
* 退出链接
* 下载链接

使用变 `linkType` 量可确定运行下一个函数时要填充的维 `tl()` 度。

## Adobe Experience Platform Launch中的链接类型

在配置规则以发送信标时设置链接类型。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击“+”图标
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型”设置为] “发送信标”。
6. 单击显示 `s.tl()` “链接类型”下拉 [!UICONTROL 框的单选按钮] 。

您可以将此下拉列表设 [!UICONTROL 置为“自定义链接]”、“ [!UICONTROL 下载链接]”或“ [!UICONTROL 退出链接”]。

## s.linkType在AppMeasurement中和启动自定义代码编辑器

该 `s.linkType` 变量是接受三个单字符值之一的字符串： `o`、 `d`或 `e`。 如果调用 `tl()` 的函数没有链接类型，则默认为“自定义”链接。

* `o` -自定义链接
* `d` -下载链接
* `e` -退出链接

> [!TIP] 此变量是函数的第二个参 `tl()` 数，通常无需设置为独立变量。 但是，如果不想 `linkType` 在函数中将值设置为参数，则可以使用该 `tl()` 变量。

```js
s.linkType = "e";
```

## 示例

以下两个示例链接跟踪调用的功能相同。 它们是实现相同链接跟踪点击的不同方法。

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
