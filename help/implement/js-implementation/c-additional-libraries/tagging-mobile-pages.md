---
description: 移动跟踪代码以服务器生成的图像标记形式置于页面上。
keywords: Analytics实施；移动跟踪；移动协议；防止缓存；alt标记；默认图像类型
seo-description: 移动跟踪代码以服务器生成的图像标记形式置于页面上。
seo-title: 为移动协议添加标记页面
solution: Analytics
title: 为移动协议添加标记页面
topic: 开发人员和实施
uuid: 5788beat-f309-4918-a99 c-a3 e591668205
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 为移动协议添加标记页面

移动跟踪代码以服务器生成的图像标记形式置于页面上。

移动跟踪代码以服务器生成的图像标记形式置于页面上。由于移动设备通常不支持 JavaScript 和 WMLScript 等脚本语言，因而无法通过脚本语言动态生成跟踪信标。

因为移动信标图像的大小实际上只有 2x2 像素，所以为了确保所有移动设备都支持，应当将高度和宽度属性设置为 5。例如：

```
<img sr c="https://metric.mydomain.com/b/ss/<Report_Suite_Name>/5/<random_number>?pageName=" alt="" width="5" height="5"/>
```

## 使用随机数防止缓存 {#section_BF5C344A16034C439C8704632CF673A7}

虽然 Adobe 服务器指示浏览器不缓存跟踪信标，但并不保证所有浏览器都遵从这些指令。为了进一步防止缓存信标，建议 Web 服务器在图像 URL 路径中动态生成一个随机数。这样做可以提高报表的准确度。随机数应在路径的最后部分，如下所示：

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" />.
```

## 包含 ALT 标记 {#section_FBD8B2FD1EA0429580C2B933DA300B07}

有些移动设备浏览器要求所有图像的图像标记中包含 alt 文本。下面显示了 ALT 属性应如何出现在图像标记中：

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" alt=""/>.
```

/5/ 应始终正确出现在路径中。Adobe 使用此值来标识移动设备。如果使用标准 /1/，Adobe 服务器将尝试在移动设备上设置 Cookie。

## 更改默认图像类型 {#section_2F969909010D4A64BF6E092A32ABADB7}

如果默认图像类型在某个特定设备上不受支持，那么将不会返回任何数据。要避免此情况，您可以强制 Adobe 数据收集服务器返回一种移动设备支持的特定图像类型。报表包名称后的代码指定了图像类型：

* `/5/` 返回默认图像类型。
* `/5.1/` 或 `/1/` 始终返回GIF图像。

* `/5.5/` 始终返回WBMP图像。

See [Identifying Visitors using Mobile Protocols](../../../implement/js-implementation/c-unique-visitors/visid-mobile.md#concept_8C5557634014440AA3588FBB0CF6BB49).
