---
description: 有关数据馈送中使用的特殊字符的信息。
keywords: Data Feed;job;special characters;hit_data;multi-valued variables;events_list;products_list;mvvars
subtopic: data feeds
title: 数据馈送中的特殊字符
topic: Reports and analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 数据馈送中的特殊字符

Adobe使用转义逻辑确保发送到数据收集服务器的值不会损坏或为负数据馈送文件。 Adobe保留以下字符用于以下目的 `hit_data.tsv`。

## 任意列中的特殊字符

| 字符 | 描述 |
|--- |--- |
| `\t` | 表示选项卡。 标记列或数据字段的结尾。 |
| `\n` | 表示换行符。 标记行或点击的结尾。 |
| `\` | 反斜线. 作为数据收集的一部分发送时对字符进行转义。 |

当这些保留值前面有反斜杠时，这些值将作为数据收集的一部分发送。

| 字符 | 描述 |
|--- |--- |
| `\\t` | 值“`\t`”在数据收集期间发送，由Adobe转义。 |
| `\\n` | 值“`\n`”在数据收集期间发送，由Adobe转义。 |
| `\\` | 值“`\`”在数据收集期间发送，由Adobe转义。 |

例如，您网站的访客使用内部搜索和搜索“search\nstring”。 您用“search\nstring”填充eVar1，并将该值发送给Adobe。 Adobe接收此点击，并转义字符串中包含的换行符。 原始数据中的实际值是“search\\nstring”。

## 多值变量（events_list、products_list、mvvar）中的特殊字符

以下字符在可包含多个值的列中具有特殊含义。

| 字符 | 描述 |
|--- |--- |
| `,` | 逗号. 表示单个值的结尾。 分隔产品字符串、事件ID或其他值。 |
| `;` | 分号。 表示中单个值的结尾 `product_list`。 在单个产品字符串中分隔字段。 |
| `=` | 等号。 Assigns a value to an event in `product_list`. |
| `^` | 脱字符号. 作为数据收集的一部分发送时对字符进行转义。 |

当这些保留值前面有尖号时，它们将作为数据收集的一部分发送。

| 字符 | 描述 |
|--- |--- |
| `^,` | 值“`,`”在数据收集期间发送，由Adobe转义。 |
| `^;` | 值“`;`”在数据收集期间发送，由Adobe转义。 |
| `^=` | 值“`=`”在数据收集期间发送，由Adobe转义。 |
| `^^` | 值“`^`”在数据收集期间发送，由Adobe转义。 |
