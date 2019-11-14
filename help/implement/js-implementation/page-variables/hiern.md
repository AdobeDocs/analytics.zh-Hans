---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---



# hierN

[!UICONTROL 层级]变量确定页面在网站层级中的位置。

<!-- 

hierN.xml

 -->

该变量最适用于网站结构超过三层的网站。例如，某媒体网站的“体育”区域可能有 4 个级别：体育、地方体育、棒球、红袜队 (Red Sox)。如果有人访问“棒球”页面，则“体育”、“地方体育”和“棒球”这几个级别都会反映此访问。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 255 字节 | H1-H5 | 层级 | "" |

有五个可用的[!UICONTROL 层级]变量，它们都必须由 Adobe 客户关怀部门启用。启用层级后，您需要决定变量的分隔符以及层级的最大级别数目。例如，如果使用逗号作为分隔符，则体育层级可能显示如下。

```js
s.hier1="Sports,Local Sports,Baseball"
```

请确保您的所有区域名称中没有分隔符。例如，如果您有一个名为“Coach Griffin, Jim”的区域，则您需要选择逗号以外的其他分隔符。每个层级区域限制在 255 字节以内，且全部变量限制也是 255 字节。分隔符一旦选定（即在层级创建时），便不易更改。

若要更改现有层级的分隔符，请联系 Adobe 客户关怀部门。分隔符也可由多个字符组成，如 || 或 /|\，这些字符组合在层级区域中出现的概率较低。

**语法和可能值** {#section_0739948A68A2420DAB1CBEA3115A5A66}

请不要在分隔符间插入空格。在以下示例语法中，N 是一个介于 1 至 5 之间的数值。

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

除了用于分隔层级的级别外，请不要在其他时候使用分隔符。分隔符可以是您选择的任何字符或字符集。

**示例** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**配置设置** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

无

**缺陷、问题和提示** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* 一旦设置了层级，便不可更改分隔符。若必须更改层级的分隔符，请联系 Adobe 客户关怀部门。
* 层级一旦设置好后，便不可更改级别数。

> [!NOTE]更改层级可能需要收取服务费。

