---
title: linkName
description: 设置自定义链接点击的名称。
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkName

运行 `linkName` 下一个函数时，使用变量确定自定义链接、下载链接或退出链接的维 `tl()` 度值。

如果此变量为空，则AppMeasurement会还原到该 `linkURL` 变量。

## Adobe Experience Platform Launch中的链接名称

在配置规则以发送信标时，可以设置链接名称字段。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击“+”图标
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型”设置为] “发送信标”。
6. 单击显 `s.tl()` 示“链接名称”字段 [!UICONTROL 的单选按钮] 。

## AppMeasurement中的s.linkName和启动自定义代码编辑器

变 `s.linkName` 量是一个字符串，它确定自定义链接、下载链接或退出链接的维度值(具体取决于 `s.linkType` 什么)。 它最多可容纳100字节。

> [!TIP] 此变量是函数的第三个参 `tl()` 数，通常不需要设置为独立变量。 但是，如果不想 `linkName` 在函数中将值设置为参数，则可以使用该 `tl()` 变量。

```js
s.linkName = "Example custom link";
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
