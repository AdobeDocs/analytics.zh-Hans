---
title: linkName
description: 设置自定义链接点击的名称。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkName

Use the `linkName` variable to determine the dimension value of custom links, download links, or exit links when running the next [`tl()`](../functions/tl-method.md) method.

如果此变量为空，则 AppMeasurement 会还原为该 [`linkURL`](linkurl.md) 变量。

## Adobe Experience Platform Launch 中的“链接名称”

在配置发送信标的规则时，可以设置链接名称字段。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. 在 [!UICONTROL Actions]下，单击“+”图标
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button which reveals the [!UICONTROL Link Name] field.

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkName

`s.linkName` 变量是用于确定自定义链接、下载链接或退出链接维度值（具体取决于 [`s.linkType`](linktype.md) 的内容）的字符串。它最多可包含 100 字节。

>[!TIP] 此变量是方法的第三个参 `tl()` 数，通常不需要设置为独立变量。 However, you can use the `linkName` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkName = "Example custom link";
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
