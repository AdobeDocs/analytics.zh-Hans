---
title: (hier)
description: 在 Adobe Analytics 中实施层级变量。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# (hier)

层级变量是自定义变量，可让您查看网站的结构。

>[!TIP] 此变量在Adobe Analytics的早期版本中更为常见。 Adobe建议改 [用eVar](evar.md) 和分类。

此变量对于站点结构中具有三个以上级别的站点很有用。 例如，媒体站点的“体育”部分可以有4个级别： `Sports`、 `Local Sports`、 `Baseball`和 `Team name`。 如果有人访问“棒球”页面，则“体育”、“地方体育”和“棒球”这几个级别都会反映此访问。

Adobe在您的实施中最多支持5个层次结构变量。 在启用层次时，确定变量的分隔符以及层次的最大级别数。 例如，如果分隔符为逗号，则层次结构将类似于：

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

请确保您的所有区域名称中没有分隔符。例如，如果调用了某个部分，请选 `Coach Griffin, Jim`择逗号以外的分隔符。 总变量限制为255字节。 分隔符可以由多个字符组成， `||` 如 `/|\`或，这些字符不太可能出现在变量值中。

## 示例

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
