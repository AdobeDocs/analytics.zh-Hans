---
title: linkType
description: 使用 linkType 变量确定点击所属的链接跟踪维度。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkType

链接跟踪点击可以填充以下三个维度之一：

* 自定义链接
* 退出链接
* 下载链接

使用 `linkType` 变量可确定运行下一个 [`tl()`](../functions/tl-method.md) 函数时要填充的维度。

## Adobe Experience Platform Launch 中的“链接类型”

在配置发送信标的规则时设置链接类型。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. 在 [!UICONTROL Actions]下，单击“+”图标
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button which reveals the [!UICONTROL Link Type] dropdown.

您可以将此下拉列 [!UICONTROL Custom Link]表设置 [!UICONTROL Download Link]为、或 [!UICONTROL Exit Link]。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkType

`s.linkType` 变量是接受以下三个单字符值之一的字符串：`o`、`d` 或 `e`。If a `tl()` method is called without a link type, it defaults to Custom link.

* `o` - 自定义链接
* `d` - 下载链接
* `e` - 退出链接

>[!TIP] 此变量是方法的第二个参 `tl()` 数，通常无需设置为独立变量。 However, you can use the `linkType` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkType = "e";
```

## 示例

以下两个示例链接跟踪调用的功能相同。它们是实现相同链接跟踪点击的两个不同方法。

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
