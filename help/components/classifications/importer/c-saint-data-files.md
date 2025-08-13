---
description: 导入器允许您将文件中的分类数据批量上载至分析报告。导入要求使用特定文件格式，才能成功上载数据。
title: 分类数据文件
feature: Classifications
exl-id: aa919a03-d461-4d12-adc1-6441fb467e63
source-git-commit: 4eea524bf95c9b6bc9ddc878c8c433bc1e60daee
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 90%

---

# 分类数据文件（旧版）

{{classification-importer-deprecation}}

导入器允许您将文件中的分类数据批量上载至分析报告。导入要求使用特定文件格式，才能成功上载数据。

为了帮助创建有效的数据文件，可以下载模板文件，将分类数据粘贴到该模板文件所提供的文件结构中。有关详细信息，请参阅[下载分类模板](/help/components/classifications/importer/c-download-saint-data.md)。

请参阅[通用文件结构](/help/components/classifications/importer/c-saint-data-files.md)，以了解有关分类中字符限制的详细信息。

## 通用文件结构

样本数据文件的说明如下：

![](assets/completed-saint-file.png)

数据文件必须遵循以下结构规则：

* 分类不能包含 0（零）值。
* Adobe 建议您将导入和导出列的数量限制为 30。
* 上载的文件必须使用不带 BOM 字符编码的 UTF-8 格式。
* 包含制表符、换行符和引号在内的特殊字符可以嵌入在单元格内，前提是指定了 v2.1 文件格式，并且该单元格已被正确[转义](/help/components/classifications/importer/importer-faq.md)。特殊字符包括：

  ```text
  \t     tab character 
  \r     form feed character 
  \n    newline character 
  "       double quote
  ```

  逗号不属于特殊字符。

* 分类名称不能包含脱字符号(^)，因为此字符用于表示子分类。
* 请小心使用连字符。例如，如果您在 Social 术语中使用连字符 (-)，则 Social 会将连字符识别为 [!DNL Not] 运算符（减号）。例如，如果您使用导入指定 *`fragrance-free`* 作为术语，则 Social 会将该术语识别为 fragrance *`minus`* free，并收集提及 *`fragrance`*，但未提及 *`free`* 的帖子。
* 在对报告数据进行分类时必须执行字符限制。例如，如果上载产品名称长度超过 100 个字符（字节）的产品的分类文本文件 (*`s.products`*)，将不会在报告中显示这些产品。跟踪代码和所有自定义转化变量（eVar）允许 255 字节。此策略还扩展到分类和子分类列值，这些值受相同的255字节限制的约束。
* 以制表符分隔的数据文件（可以使用任一款电子表格应用程序或文本编辑器来创建模板文件）。
* 使用 `.tab` 或 `.txt` 作为文件扩展名。
* 在行前添加井号 (#) 表示此行为用户注释。Adobe 会忽略所有以 # 开头的行。
* 双井号后面接SC (`## SC`)表示该行是报告使用的预处理标题注释。 请不要删除这些行。
* 分类导出可能包含重复键值，因为键值中存在换行符。在 FTP 或浏览器导出中，通过打开 FTP 帐户的引号功能可以解决此问题。该功能会在每个带有换行符的键值两边加上引号。
* 导入文件首行中的单元格 C1 包含一个版本标识符，用于决定分类如何处理文件剩余部分内引号的使用。

   * v2.0 忽略引号，并将所有引号都视为指定键和值的一部分。以下面这个值为例：&quot;This is &quot;&quot;some value&quot;&quot;&quot;。v2.0 会照字面将其解释为 &quot;This is &quot;&quot;some value&quot;&quot;&quot;。
   * v2.1 则要求分类将引号视为 Excel 文件中使用的文件格式的一部分。因此，v2.1 将以上示例的格式解释为：This is &quot;some value&quot;。
   * 如果文件中指定的是 v2.1，但实际上需要的是 v2.0，也就是说，当引号的使用方式在 Excel 格式中违规时，则可能产生问题。例如，若您有以下值：&quot;VP NO REPS&quot; S/l Dress w/ Overlay。在 v2.1 中，这是错误的格式（此值应当由左右引号括起来，并且作为实际值一部分的引号应当由额外的引号转义），而且分类也无法正常工作。
   * 请确保您执行了以下操作之一：通过更改上载文件中的标题（单元格 C1）将您的文件格式更改为 v2.0，或者在所有文件中正确实施 Excel 引号功能。

* 数据文件的第一行（非注释）包含用于标识该列中分类数据的列标题。导入器要求列标题采用特定的格式。有关详细信息，请参阅[列标题格式](/help/components/classifications/importer/c-saint-data-files.md)。
* 在数据文件中，紧接标题行的是数据行。每行数据都应包含各列标题的数据字段。
* 数据文件支持以下控制代码，Adobe 可以使用这些代码为文件提供结构以及正确导入分类数据：

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 控制代码 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;New Line&gt; </p> </td> 
   <td colname="col2"> <p>新行字符是在数据文件中的数据行/记录之间唯一受支持的分隔符。通常，您只需要在编写程序时专门插入这些字符，即可自动生成数据文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>要求 Adobe 自动为此元素生成唯一的 ID。 </p> <p>在促销活动环境中，此控制值会指示 Adobe 为每个创作元素指定一个标识符。请参阅<a href="/help/components/classifications/importer/c-saint-data-files.md"  >密钥</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>指定此数据列代表与此项目相关联的日期范围。请参阅<a href="/help/components/classifications/importer/c-saint-data-files.md"  >日期</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>空白字段 </p> </td> 
   <td colname="col2"> <p>表示当前字段的 NULL 值。如果特定数据列不适用于当前记录，则使用此控制代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER 修饰符 </p> </td> 
   <td colname="col2"> <p>指定此数据列代表 <span class="wintitle">PER 修饰符</span>字段。请参阅 <a href="/help/components/classifications/importer/c-saint-data-files.md"  >PER 修饰符标题</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 列标题格式

>[!NOTE]
>
>Adobe 建议您将导入和导出列的数量限制为 30。

分类文件支持以下列标题：

### 键

在整个系统中，此值必须唯一。此字段中的值对应于在您网站的 [!DNL JavaScript] 信标中分配给 [!DNL Analytics] 变量的值。该列中的数据可能包含 ~autogen~ 或任何其他唯一跟踪代码。

### 分类列标题

>[!NOTE]
>
>[!UICONTROL 分类]列标题中的值必须完全符合分类的命名规范，否则会导致导入失败。例如，如果管理员在[!UICONTROL 促销活动设置管理器]中将[!UICONTROL 促销活动]更改为[!UICONTROL 内部促销活动名称]，则文件列标题必须随之更改。“Key”是保留的分类（标头）值。不支持名为“Key”的新分类。

此外，数据文件支持以下附加标题约定，以确定子分类和其他专门的数据列：

### 子分类标题

例如，`Campaigns^Owner`是包含`Campaign Owner`值的列的列标题。 同样，`Creative Elements^Size`是包含`Size`分类的`Creative Elements`子分类的列的列标题。

## 有关分类的疑难解答

* [常见 上载问题](https://helpx.adobe.com/cn/analytics/kb/common-saint-upload-issues.html)：知识库文章，描述由于文件格式以及文件内容不正确导致的问题。
