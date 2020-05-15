---
description: 有关数据馈送中使用的特殊字符的信息。
keywords: Data Feed;job;special characters;hit_data;multi-valued variables;events_list;products_list;mvvars
subtopic: data feeds
title: 数据馈送中的特殊字符
topic: Reports and analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 数据馈送中的特殊字符

Adobe 使用转义逻辑确保发送到数据收集服务器的值不会损坏或对数据馈送文件造成负面影响。Adobe 在 `hit_data.tsv` 中出于以下目的保留了以下字符。

## 任意列中的特殊字符

| 字符 | 描述 |
|--- |--- |
| `\t` | 表示制表符。标记列或数据字段的结尾。 |
| `\n` | 表示换行符。标记行或点击的结尾。 |
| `\` | 反斜线. 作为数据收集的一部分发送时的转义字符。 |

当这些保留值前面有反斜线时，将作为数据收集的一部分发送它们。

| 字符 | 描述 |
|--- |--- |
| `\\t` | “`\t`”值在数据收集期间发送，由 Adobe 转义。 |
| `\\n` | “`\n`”值在数据收集期间发送，由 Adobe 转义。 |
| `\\` | “`\`”值在数据收集期间发送，由 Adobe 转义。 |

例如，您网站的访客使用内部搜索并搜索“search\nstring”。您用“search\nstring”填充 eVar1，并将该值发送给 Adobe。Adobe 接收该点击，并对字符串中包含的换行符进行转义处理。原始数据中的实际值是“search\\nstring”。

## 多值变量（events_list、products_list、mvvar）中的特殊字符

以下字符在可包含多个值的列中具有特殊含义。

| 字符 | 描述 |
|--- |--- |
| `,` | 逗号。表示单个值的结尾。用于分隔产品字符串、事件 ID 或其他值。 |
| `;` | 分号。表示 `product_list` 中单个值的结尾。用于分隔单个产品字符串中的字段。 |
| `=` | 等号。将值分配到 `product_list` 中的事件。 |
| `^` | 脱字符号。作为数据收集的一部分发送时的转义字符。 |

当这些保留值前面有脱字符号时，将作为数据收集的一部分发送它们。

| 字符 | 描述 |
|--- |--- |
| `^,` | “`,`”值在数据收集期间发送，由 Adobe 转义。 |
| `^;` | “`;`”值在数据收集期间发送，由 Adobe 转义。 |
| `^=` | “`=`”值在数据收集期间发送，由 Adobe 转义。 |
| `^^` | “`^`”值在数据收集期间发送，由 Adobe 转义。 |
