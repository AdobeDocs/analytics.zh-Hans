---
title: linkType
description: 使用 linkType 变量确定点击所属的链接跟踪维度。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '239'
ht-degree: 100%

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
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击“+”图标
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为“发送信标”。
6. 单击 `s.tl()` 单选按钮，将显示[!UICONTROL 链接类型]字段。

您可以将此下拉菜单设置为[!UICONTROL 自定义链接]、[!UICONTROL 下载链接]或[!UICONTROL 退出链接]。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkType

`s.linkType` 变量是接受以下三个单字符值之一的字符串：`o`、`d` 或 `e`。如果在未指定链接类型的情况下调用 `tl()` 方法，则该方法将默认为自定义链接。

* `o` - 自定义链接
* `d` - 下载链接
* `e` - 退出链接

>[!TIP]
>
>此变量是 `tl()` 方法的第二个参数，通常不需要设置为独立变量。但是，如果不想在 `linkType` 方法中将值设置为参数，则可以使用该 `tl()` 变量。

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
