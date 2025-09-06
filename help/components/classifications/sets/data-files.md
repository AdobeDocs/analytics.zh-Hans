---
description: 分类集支持的文件格式
title: 分类集文件格式
feature: Classifications
source-git-commit: 2d9eb9179ace40a8d333883cea78dd67329078ab
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 0%

---

# 分类集文件格式

分类集支持多种文件格式来批量上传分类数据。 每种格式对于成功的数据上传都有特定的要求。

按照这些规范正确格式化文件后，即可通过分类集界面或API上传文件。 有关详细的上传说明：

* **浏览器上传**：请参阅[架构](manage/schema.md)
* **API上载**：请参阅[Analytics分类API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/)

分类集支持以下文件格式：

* **JSON**：包含结构化数据的JavaScript对象表示法文件
* **CSV**：逗号分隔值文件
* **TSV/TAB**：以制表符分隔的值文件

## 一般文件要求

所有文件格式都必须符合以下要求：

* **文件编码**：使用不带字节顺序标记的UTF-8。 还支持Latin1编码。
* **字符限制**：单个分类值的最大限制为255字节。
* **键要求**：键值不得为空或仅包含空格。 如果存在重复的键，则使用最后一个匹配项。

+++**JSON格式详细信息**

JSON文件格式遵循JSON行(JSONL)的约定。 文件每行必须包含一个JSON对象，其中每个对象表示单个分类记录。

>[!NOTE]
>
>尽管遵循JSON行的约定，但所有上传仍使用`.json`文件扩展名。 使用`.jsonl`扩展可能会导致错误。

### JSON结构

每个JSON对象必须包含：

* `key` （必需）：分类记录的唯一标识符
* `data` （更新时必需）：包含分类列名称及其值的对象
* `action` （可选）：要执行的操作。 支持的值包括：
   * `update` （默认）
   * `delete-field`
   * `delete-key`
* `enc` （可选）：数据编码规范。 支持的值包括：
   * `utf8`或`UTF8` （默认）
   * `latin1` 或 `LATIN1`

所有JSON字段名称(`key`、`data`、`action`、`enc`)都区分大小写，且必须为小写。

### JSON示例

**基本更新记录：**

```json
{"key": "product123", "data": {"Product Name": "Basketball Shoes", "Brand": "Brand A", "Category": "Sports"}}
```

**使用指定的编码更新：**

```json
{"key": "product456", "enc": "utf8", "data": {"Product Name": "Running Shoes", "Brand": "Brand B"}}
```

**删除特定字段：**

```json
{"key": "product789", "action": "delete-field", "data": {"Brand": null, "Category": null}}
```

**删除整个键：**

```json
{"key": "product999", "action": "delete-key"}
```

### JSON验证规则

* `key`字段为必填，不能为null或为空。
* 对于`update`操作，`data`字段为必填项，不能为空。
* 对于`delete-field`操作，`data`字段必须包含要删除的字段。
* 对于`delete-key`操作，`data`字段不得存在。
* 支持的编码值不区分大小写，并包含标准字符集名称。

+++

+++**CSV格式详细信息**

CSV（逗号分隔值）文件使用逗号分隔分类数据字段。

### CSV结构

* **标题行**：第一行必须包含列标题，第一列必须是键列。 后续列应与您的分类集架构中的名称匹配
* **数据行**：每个后续行都包含分类数据
* **分隔符**：字段用逗号分隔
* **引号**：包含逗号、引号或换行符的字段应包含在双引号中

### CSV示例

**基本分类数据：**

```csv
Key,Product Name,Brand,Category,Price
product123,"Basketball Shoes",Brand A,Sports,89.99
product456,"Running Shoes",Brand B,Sports,79.99
product789,"Winter Jacket",Brand C,Clothing,149.99
```

**删除整个键：**

```csv
Key,Product Name,Brand,Category,Price
product999,~deletekey~,,,
```

**删除特定字段（混合了更新）：**

```csv
Key,Product Name,Brand,Category,Price
product123,"Updated Product Name",Brand A,Sports,89.99
product456,,~empty~,~empty~,79.99
```

### CSV格式规则

* 包含逗号的字段必须用双引号引住
* 包含双引号的字段必须通过将其加倍(`""`)来进行转义
* 空字段表示该分类的null值
* 字段周围的前导空格和尾随空格会自动裁剪
* 带引号的字段内的特殊字符（制表符、换行符）将被保留

**删除操作：**
* 在任意字段中使用`~deletekey~`删除整个键及其所有分类数据
* 在特定字段中使用`~empty~`以仅删除这些分类值（保留其他字段不变）
* 使用`~empty~`时，可以在同一文件中将删除与更新混合使用

+++

+++**TSV/TAB格式详细信息**

TSV（制表符分隔值）和TAB文件使用制表符字符来分隔分类数据字段。

### TSV/选项卡结构

* **标题行**：第一行必须包含列标题，第一列必须是键列。 后续列应与您的分类集架构中的名称匹配
* **数据行**：每个后续行都包含分类数据
* **分隔符**：字段由制表符分隔(`\t`)
* **引用**：通常不需要引用，但某些实现支持引用字段

### TSV/选项卡示例

**基本分类数据：**

```tsv
Key    Product Name    Brand    Category    Price
product123    Basketball Shoes    Brand A    Sports    89.99
product456    Running Shoes    Brand B    Sports    79.99
product789    Winter Jacket    Brand C    Clothing    149.99
```

**删除整个键：**

```tsv
Key    Product Name    Brand    Category    Price
product999    ~deletekey~            
```

**删除特定字段（混合了更新）：**

```tsv
Key    Product Name    Brand    Category    Price
product123    Updated Product Name    Brand A    Sports    89.99
product456        ~empty~    ~empty~    79.99
```

### TSV/选项卡格式规则

* 字段由单个制表符分隔
* 空字段（连续选项卡）表示null值
* 通常不需要特别报价
* 保留前导空格和尾随空格
* 应避免在字段中使用换行符

**删除操作：**
* 在任意字段中使用`~deletekey~`删除整个键及其所有分类数据
* 在特定字段中使用`~empty~`以仅删除这些分类值（保留其他字段不变）
* 使用`~empty~`时，可以在同一文件中将删除与更新混合使用

+++

## 错误处理

常见上传问题和解决方案：

### 一般文件格式错误

* **文件格式无效**：验证文件扩展名是否与内容格式(.json、.csv、.tsv或.tab)匹配。
* **“未知标头”**：列名称必须与您的分类集架构匹配（适用于所有格式）。

### CSV/TSV特定错误

* **“第一列必须为键”**：请确保您的CSV/TSV文件具有正确的标题行，键列在前。
* **“至少需要两个标题项”**： CSV/TSV文件必须至少有一个“键”列和一个分类列。
* **“第一个标头列必须命名为&#39;Key&#39;”**：第一个列标头必须完全为&#39;Key&#39;（大写K，区分大小写）。
* **“不允许使用空白标头”**：所有CSV/TSV列标头都必须有名称。
* **“列数与标头不匹配”**：每个CSV/TSV数据行的字段数必须与标头行的字段数相同。
* **“格式错误的文档”**：检查CSV引号、TSV文件中的正确制表符分隔等。

### JSON特定错误

* **“键为必填字段”**：所有JSON记录都必须有一个非空`"key"`字段（小写，区分大小写）。
* 使用action=update&quot;**时，**&quot;数据是必填字段： JSON更新操作必须包括`"data"`字段。
* 使用action=delete-field“**”时，**“数据是必填字段： JSON删除字段操作必须指定在`"data"`字段中要删除的字段。
* **&quot;使用action=delete-key&quot;**&#x200B;时，数据不得存在： JSON delete-key操作不能包含`"data"`字段。
* **“不受支持的编码”**：仅在`"enc"`字段(utf8、UTF8、latin1、LATIN1)中使用受支持的编码值。
* **无效的JSON语法**：请确保JSON文件的格式符合JSONL约定。 另外，还要检查常规JSON格式、缺少引号、逗号、括号等。

### 大小限制错误

* **“密钥超出最大大小”**：单个密钥不能超过255字节。
* **“列值超出最大大小”**：单个分类值不能超过255字节。

## 最佳实践

* **文件大小**： 50MB是浏览器和API上传的最大文件大小。
* **批次处理**：对于较大的数据集，请考虑拆分为较小的文件。
* **数据验证**：在上传大型数据集之前，使用小样例文件进行测试。
* **备份**：保留源数据文件的副本。
* **增量更新**：使用JSON格式精确控制个别记录的更新和删除。
