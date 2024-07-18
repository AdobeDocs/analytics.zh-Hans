---
description: 导入器允许您将文件中的分类数据批量上载至分析报告。导入要求使用特定文件格式，才能成功上载数据。
title: 分类数据文件
feature: Classifications
exl-id: aa919a03-d461-4d12-adc1-6441fb467e63
source-git-commit: eb6703dc4079678020954984905ee210cbcbbf8f
workflow-type: tm+mt
source-wordcount: '1787'
ht-degree: 100%

---

# 分类数据文件

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
* 包含制表符、换行符和引号在内的特殊字符可以嵌入在单元格内，前提是指定了 v2.1 文件格式，并且该单元格已被正确[转义](/help/components/classifications/importer/t-classifications-escape-data.md)。特殊字符包括：

  ```text
  \t     tab character 
  \r     form feed character 
  \n    newline character 
  "       double quote
  ```

  逗号不属于特殊字符。

* 分类不得包含脱字符 (^)，因为此字符用来表示子分类。
* 请小心使用连字符。例如，如果您在 Social 术语中使用连字符 (-)，则 Social 会将连字符识别为 [!DNL Not] 运算符（减号）。例如，如果您使用导入指定 *`fragrance-free`* 作为术语，则 Social 会将该术语识别为 fragrance *`minus`* free，并收集提及 *`fragrance`*，但未提及 *`free`* 的帖子。
* 在对报告数据进行分类时必须执行字符限制。例如，如果上载产品名称长度超过 100 个字符（字节）的产品的分类文本文件 (*`s.products`*)，将不会在报告中显示这些产品。跟踪代码和所有自定义转化变量（eVar）允许 255 字节。此策略还扩展到分类和子分类列值，它们同样受到 255 字节的限制。
* 以制表符分隔的数据文件（可以使用任一款电子表格应用程序或文本编辑器来创建模板文件）。
* 使用 [!DNL .tab] 或 [!DNL .txt] 作为文件扩展名。
* 在行前添加井号 (#) 表示此行为用户注释。Adobe 会忽略所有以 # 开头的行。
* 双井号后面接 SC (## SC) 表示此行为报告所使用的预处理标题注释。请不要删除这些行。
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

>[!MORELIKETHIS]
>
>* [常见上载问题](https://helpx.adobe.com/cn/analytics/kb/common-saint-upload-issues.html)

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

此外，数据文件支持下列其他标题规范，用于标识子分类和其他特殊数据列：

### 子分类标题

例如，[!UICONTROL 促销活动^所有者]是包含[!UICONTROL 促销活动所有者]值的列的列标题。同样地，[!UICONTROL 创作元素^大小]是包含[!UICONTROL 创作元素]分类的[!UICONTROL 大小]子分类的列的列标题。

### 分类量度标题

例如，[!UICONTROL 促销活动^~成本]指的是[!UICONTROL 促销活动]分类中的[!UICONTROL 成本]量度。

### PER 修饰符标题

*`Per Modifier`* 标题的表示方式为将 *`~per`* 添加到分类量度标题。例如，如果 *`Metric`* 标题为 *`Campaigns^~Cost`*，则 PER 修饰符标题为 *`Campaigns^~Cost~per`*。Adobe 支持以下 *`PER Modifier`* 关键词：

这些字符在数据文件中有其特殊含义。因此，请尽量避免在属性名称或数据中使用这些字词。

**FIXED：**&#x200B;固定值。不进行任何缩放。

**DAY：**&#x200B;将该值乘以报告中的天数。

**ORDER：**&#x200B;将该值乘以报告中行项目的订单数。

**CHECKOUT：**&#x200B;将该值乘以报告中行项目的结账金额。

**UNIT：**&#x200B;将该值乘以报告中行项目的件数。

**REVENUE：**&#x200B;将该值乘以报告中行项目的收入金额。

**SCADD：**&#x200B;将该值乘以报告中每个行项目出现[!UICONTROL 购物车加货]事件的次数。

**SCREMOVE：**&#x200B;将该值乘以报告中每个行项目出现[!UICONTROL 购物车减货]事件的次数。

**INSTANCE：**&#x200B;将该值乘以报告中行项目的实例数。

**CLICK：**&#x200B;将该值乘以报告中行项目的点击数。

**EVENT：**&#x200B;将该值乘以报告中每个行项目出现特定客户事件的次数。

**示例：**&#x200B;如果促销活动 A 的成本为 $10,000，[!UICONTROL 促销活动^~成本]列包含的值为 10000，而[!UICONTROL 促销活动^~成本~per] 列包含 [!UICONTROL FIXED]。在报告中显示促销活动 A 的成本时，会将 $10,000 显示为日期范围内促销活动 A 的固定成本。

**示例：**&#x200B;如果每次单击促销活动 B 花费大约 $2，[!UICONTROL 促销活动^~成本]列包含 2，而&#x200B;**[!UICONTROL 促销活动^~成本~per]** 列包含 [!UICONTROL CLICK]。在报告中显示促销活动 B 的成本时，Adobe 会随时计算报告日期范围内的成本（2 &#42; [点击次数]）。 这样即可根据促销活动 B 的点击次数计算出总成本。

### 页面

促销活动日期通常是与各个促销活动关联的范围（开始日期和结束日期）。日期的格式应当为 YYYY/MM/DD。例如，2013/06/15-2013/06/30。

有关详细信息，请参阅[转化分类](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html)。

>[!NOTE]
>
>在 2018 年 5 月 10 日的 [!DNL Analytics] 维护版本中，Adobe 已开始限制启用日期的分类和数值分类的功能。这些分类类型已从管理员和分类导入器界面中删除。无法添加新的启用日期的分类和数值分类。现有的分类仍可以通过标准分类工作流程进行管理（上传、删除），并将继续在报告中可用。

## 将日期与[!UICONTROL 分类]一起使用 {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL 分类]可用于将日期范围分配给您的促销活动或其他转化[!UICONTROL 分类]，从而让促销活动测量更准确。指定值的日期范围后，该日期范围外任何匹配的值都不会进行分类。这对希望利用促销活动为“有效”，并且不是所有点击都与该促销活动本身匹配的具体日期的促销活动测量而言非常有用。要成功地用日期范围对值进行分类，必须满足以下条件：

* [!UICONTROL 分类]必须以转化变量为基础。
* 使用的[!UICONTROL 分类]必须设置为“启用日期”或“数值 2”。
* 涉及的日期范围必须包含开始日期和（可选）结束日期。

根据日期范围分类促销活动：

>[!IMPORTANT]
>此选项不适用于启用新分类架构的报告包。

1. 登录 [!DNL Analytics]，然后转到“管理员”>“分类”。
1. 单击&#x200B;**[!UICONTROL 浏览器导出]**&#x200B;选项卡，确保启用日期的分类的设置均正确，然后单击“导出文件”。
1. 在 Microsoft Excel 或您熟悉的其他电子表格编辑器中打开此文件。
1. 其中一列将以下面的内容结尾：

   ^~period~，
在该列中输入日期范围。
1. 在此列下，按下面的格式输入每个值的日期范围：

   `YYYY/MM/DD - YYYY/MM/DD`。请务必遵循以下原则：

   * 在短划线的两侧保留空格。
   * 使用连字符 (-) 分开多个范围，而不要使用短划线或长划线。
   * 如果某月或某天是单个数字，则在其前面添加零。
   * 日期范围必须有一个开始日期，而结束日期是可选的。

1. 保存文件，然后转到“管理员”|“分类”|“导入文件”，将文件上载至 [!DNL Analytics]。

>[!NOTE]
>
>特定键值不得包含多个日期范围。

## 有关分类的疑难解答

* [常见 上载问题](https://helpx.adobe.com/cn/analytics/kb/common-saint-upload-issues.html)：知识库文章，描述由于文件格式以及文件内容不正确导致的问题。
