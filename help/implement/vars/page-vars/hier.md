---
title: (hier)
description: 在 Adobe Analytics 中实施层级变量。
translation-type: ht
source-git-commit: cd2225ec00190af6b616f313b419935c4f8dfafd
workflow-type: ht
source-wordcount: '185'
ht-degree: 100%

---


# (hier)

层级变量是自定义变量，可让您查看网站的结构。

>[!TIP]
>
>此变量在 Adobe Analytics 的先前版本中比较常见。Adobe 建议改用 [eVar](evar.md) 和分类。

此变量适用于网站结构超过三层的网站。例如，媒体网站的“体育”部分可以有 4 个级别：`Sports`、`Local Sports`、`Baseball` 以及 `Team name`。如果有人访问“棒球”页面，则“体育”、“地方体育”和“棒球”这几个级别都会反映此访问。

Adobe 最多为实施中的 5 个层级变量提供支持。启用层级后，请决定变量的分隔符以及层级的最大级别数目。例如，如果分隔符为逗号，则层级类似于以下内容：

```js
s.hier1 = "Sports,Local Sports,Baseball";
```

请确保您的所有区域名称中没有分隔符。例如，如果某个部分叫做 `Coach Griffin, Jim`，请选择使用逗号以外的分隔符。变量总限制为 255 字节。分隔符可以包含多个字符，例如 `||` 或 `/|\`，这些字符不太可能出现在变量值中。

## 示例

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub";
```

```js
s.hier4="Sports/Local Sports/Baseball";
```
