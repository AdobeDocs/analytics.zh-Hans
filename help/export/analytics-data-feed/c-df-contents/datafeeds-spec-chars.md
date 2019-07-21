---
description: 有关数据馈送中使用的特殊字符的信息。
keywords: 数据馈送；工作；特殊字符；pit_ data；多值变量；events_ list；products_ list；mvvars
seo-description: 有关数据馈送中使用的特殊字符的信息。
seo-title: 特殊字符
solution: Analytics
subtopic: 数据馈送
title: 特殊字符
topic: Reports & Analytics
uuid: 5efe019b-39e6-4226-a936-88202a02 f5 e6
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 特殊字符

有关数据馈送中使用的特殊字符的信息。

* [hit_data 文件中的特殊字符](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_9759C7A6AE684EB5B4A154FB6A26B39E)
* [多值变量（events_list、products_list、mvvar）中的特殊字符](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_056F8D540FFC4F24A001DC74331C2AAC)
* [示例工作流程](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_97F8C2925A35433DA2E7E8BE60037E37)

## hit_data 文件中的特殊字符 {#section_9759C7A6AE684EB5B4A154FB6A26B39E}

以下字符在 hit_data 文件中具有特殊含义：

| 字符 | 含义 | 说明 |
|--- |--- |--- |
| \t（制表符） | 列结尾 | 标记数据字段的结尾。 |
| \n（换行符） | 行结尾 | 标记数据行的结尾。 |
| \（反斜线字符） | 转义字符 | 当制表符、换行符和反斜线字符是数据收集期间发送的值的一部分时，对这些字符进行转义。 |

当任何特殊字符之前有反斜线时，该字符表示原义字符。

| 字符 | 含义 | 说明 |
|--- |--- |--- |
| \\t | 制表符 | 原义制表符。此字符是数据收集期间发送的值的一部分。 |
| \\n | 换行符 | 原义换行符。此字符是数据收集期间发送的值的一部分。 |
| \\ | 反斜线 | 原义反斜线字符。此字符是数据收集期间发送的值的一部分。 |

## 多值变量（events_list、products_list、mvvar）中的特殊字符 {#section_056F8D540FFC4F24A001DC74331C2AAC}

以下字符在多值变量中具有特殊含义：

<table id="table_FDA13DE05A784ED4972C2955BD2642C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字符 </th> 
   <th colname="col02" class="entry"> 含义 </th> 
   <th colname="col2" class="entry"> 说明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code>,</code>（逗号字符） </td> 
   <td colname="col02"> 值结尾 </td> 
   <td colname="col2"> <p>在多值变量中隔开产品字符串、事件 ID 或其他值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>;</code>（分号字符） </td> 
   <td colname="col02"> 单个产品值中的子值的结尾 </td> 
   <td colname="col2"> <p>隔开与 <code>product_list</code> 中的单个产品关联的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>=</code>（等号字符） </td> 
   <td colname="col02"> 值分配 </td> 
   <td colname="col2"> <p>将值分配到 <code>event_list</code> 中的事件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

当任何特殊字符之前有脱字符号时，该字符表示原义字符。

| 字符 | 含义 | 说明 |
|--- |--- |--- |
| ^, | 逗号 | 原义逗号字符。此字符是数据收集期间发送的值的一部分。 |
| ^; | 分号 | 原义分号字符。此字符是数据收集期间发送的值的一部分。 |
| ^= | 等号 | 原义等号字符。此字符是数据收集期间发送的值的一部分。 |
| ^^ | 脱字符号 | 原义脱字符号。此字符是数据收集期间发送的值的一部分。 |

## 示例工作流程 {#section_97F8C2925A35433DA2E7E8BE60037E37}

如果数据馈送中的某些列包含用户提交的数据，在通过使用 `split`、`readLine` 或类似方法按列或行来分隔数据之前，您应该检查特殊字符。

请仔细研究以下数据：

| 浏览器宽度 | 浏览器高度 | eVar1 | prop1 |
|---|---|---|---|
| 1680 | 1050 | search\nstring | en |
| 800 | 600 | search\tstring | en |

导出期间，eVar1 值中的换行符和制表符会进行转义。这些行的数据馈送如下所示：

```
1680\t1050\tsearch\\nstring\ten\n 
800\t600\tsearch\\tstring\ten\n
```

Calling `readLine()` on the first row returns the following partial string:

```
800\t600\tsearch\
```

Calling `split("\t")` on the second row returns the following string array:

```
800 
600 
search\ 
string 
en
```

为避免这样，请使用如下解决方案：

1. 在文件的开头开始读取，直到您找到制表符、换行符、反斜线或脱字符号字符。
1. 根据遇到的特殊字符，执行下列某项操作：

   * 制表符 - 将该点以上的字符串插入数据存储单元，然后继续。
   * 换行符 - 完成数据存储行。
   * 反斜线 - 读取下一个字符，插入适当的原义字符串，然后继续。
   * 脱字符号 - 读取下一个字符，插入适当的原义字符串，然后继续。

