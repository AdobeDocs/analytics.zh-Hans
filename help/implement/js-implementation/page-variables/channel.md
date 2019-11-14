---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: ea6109f2f9aa421001fde6d7bec65b82beda883c

---


# channel

 变量最常用于识别网站的区域。

<!-- 

channel.xml

 -->

例如，某商家的网站可能设有电器、玩具或服装等区域。某个媒体网站可能设有新闻、体育或商业信息等区域。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | CH | 网站内容 &gt; 网站区域 | "" |

Adobe 建议填充每个页面的渠道变量。您还可以启用&#x200B;*`channel`*&#x200B;和[!UICONTROL 页面名称]变量之间的关联。

当区域有一个或多个级别的子区域时，您可以在 *`channel`* 变量中显示这些区域，或以不同的变量标识这些级别。

**语法和可能值**

```js
s.channel="value"
```

*`channel`* 变量的值没有其他特别限制。

**示例** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**缺陷、问题和提示** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

如果您的网站包含多个级别，您可以使用 *`hierarchy`* 或其它变量指定这些级别。*`channel`* 值不是永久性的，但是在同一页面上触发的成功事件将被归结到此 *`channel`* 值。
