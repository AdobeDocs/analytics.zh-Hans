---
description: 如果使用常用变量（如 q）填充搜索词，则可以使用处理规则向内部搜索词 eVar 填充这些值。
subtopic: Processing rules
title: 使用查询字符串参数填充内部搜索词
topic: Admin tools
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
translation-type: ht
source-git-commit: cd2225ec00190af6b616f313b419935c4f8dfafd
workflow-type: ht
source-wordcount: '115'
ht-degree: 100%

---


# 使用查询字符串参数填充内部搜索词

如果使用常用变量（如 q）填充搜索词，则可以使用处理规则向内部搜索词 eVar 填充这些值。

查询字符串值必须以 Unicode 或 UTF-8 编码才能由处理规则读取。

| 规则集 | 值 |
|---|---|
| 条件 | 如果设置为查询字符串参数 q |
| 操作 | 将内部搜索词的值覆盖为查询字符串参数 q |

例如：

![](assets/populate-internal-search-terms.png)

