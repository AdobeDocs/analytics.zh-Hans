---
title: linkName
description: 设置自定义链接点击的名称。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 80%

---


# linkName

Use the `linkName` variable to determine the dimension item of custom links, download links, or exit links when running the next [`tl()`](../functions/tl-method.md) method.

如果此变量为空，则 AppMeasurement 会还原为该 [`linkURL`](linkurl.md) 变量。

## Adobe Experience Platform Launch 中的“链接名称”

在配置发送信标的规则时，可以设置链接名称字段。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击“+”图标
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为“发送信标”。
6. 单击 `s.tl()` 单选按钮，此时会显示[!UICONTROL 链接名称]字段。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkName

The `s.linkName` variable is a string that determines the dimension item for custom links, download links, or exit links (depending on what [`s.linkType`](linktype.md) is). 它最多可包含 100 字节。

>[!TIP]
>
> 此变量是 `tl()` 方法的第三个参数，通常不需要设置为独立变量。但是，如果不想在 `linkName` 方法中将值设置为参数，则可以使用该 `tl()` 变量。

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
