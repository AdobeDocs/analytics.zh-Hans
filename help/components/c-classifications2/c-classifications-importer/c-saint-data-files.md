---
description: 导入器允许您将文件中的分类数据批量上载至分析报表。导入要求使用特定文件格式，才能成功上载数据。
seo-description: 导入器允许您将文件中的分类数据批量上载至分析报表。导入要求使用特定文件格式，才能成功上载数据。
seo-title: 分类数据文件
solution: Analytics
subtopic: 分类
title: 分类数据文件
topic: 管理工具
uuid: f27bb812-56e0-472a-9993-d869 f0 fea700
translation-type: tm+mt
source-git-commit: c0c4a3f42a7236c6f9e5001f5ca0ef9173dbaa66

---


# 分类数据文件

导入器允许您将文件中的分类数据批量上载至分析报表。导入要求使用特定文件格式，才能成功上载数据。

为了帮助创建有效的数据文件，可以下载模板文件，将分类数据粘贴到该模板文件所提供的文件结构中。有关详细信息，请参阅 [下载分类模板](../../../components/c-classifications2/c-classifications-importer/c-download-saint-data.md#concept_0F06847AD8D042F5BA818AE3C37E2417).

See [General File Structure](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9EFF968DF5D244A887DE94075431C1BE) for more information about character limits in classifications.

See [Numeric 2 Classifications](../../../components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md#concept_71024B7B91DF4E909076062AB1380D8B) for information about uploading data using numeric 2 classifications.

## 常规文件结构

样本数据文件的说明如下：

![](assets/completed-saint-file.png)

数据文件必须遵循以下结构规则：

* 分类不能包含 0（零）值。
* Adobe 建议您将导入和导出列的数量限制为 30。
* 上载的文件必须使用不带 BOM 字符编码的 UTF-8 格式。
* 包含制表符、换行符和引号在内的特殊字符可以嵌入在单元格内，前提是指定了 v2.1 文件格式，并且该单元格已被正确[转义](../../../components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md#task_EB47E80063F14F9CB2D186C0CAA9CBAD)。特殊字符包括：

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   逗号不属于特殊字符。

* 分类不得包含脱字符 (^)，因为此字符用来表示子分类。
* 请小心使用连字符。例如，如果您在 Social 术语中使用连字符 (-)，则 Social 会将连字符识别为 [!DNL Not] 运算符（减号）。For example, if you specify *`fragrance-free`* as a term using the import, Social recognizes the term as fragrance *`minus`* free and collects posts that mention *`fragrance`*, but not *`free`*.
* 在对报表数据进行分类时必须执行字符限制。For example, if you upload a classifications text file for products ( *`s.products`*) with product names longer than 100 characters (bytes), the products will not display in reporting. 跟踪代码和所有自定义转化变量 (eVar) 允许 255 字节。
* 以制表符分隔的数据文件（可以使用任一款电子表格应用程序或文本编辑器来创建模板文件）。
* [!DNL .tab] 文件扩展名 [!DNL .txt] 。
* 在行前添加井号 (#) 表示此行为用户注释。Adobe 会忽略所有以 # 开头的行。
* 双井号后面接 SC (## SC) 表示此行为报表所使用的预处理标题注释。请不要删除这些行。
* 分类导出可能包含重复键值，因为键值中存在换行符。在 FTP 或浏览器导出中，通过打开 FTP 帐户的引号功能可以解决此问题。该功能会在每个带有换行符的键值两边加上引号。
* 导入文件首行中的单元格 C1 包含一个版本标识符，用于决定分类如何处理文件剩余部分内引号的使用。

   * v2.0 忽略引号，并将所有引号都视为指定键和值的一部分。以下面这个值为例："This is ""some value"""。v2.0 会照字面将其解释为 "This is ""some value"""。
   * v2.1 则要求分类将引号视为 Excel 文件中使用的文件格式的一部分。因此，v2.1 将以上示例的格式解释为：This is "some value"。
   * 如果文件中指定的是 v2.1，但实际上需要的是 v2.0，也就是说，当引号的使用方式在 Excel 格式中违规时，则可能产生问题。例如，若您有以下值："VP NO REPS" S/l Dress w/ Overlay。在 v2.1 中，这是错误的格式（此值应当由左右引号括起来，并且作为实际值一部分的引号应当由额外的引号转义），而且分类也无法正常工作。
   * 请确保您执行了以下操作之一：通过更改上载文件中的标题（单元格 C1）将您的文件格式更改为 v2.0，或者在所有文件中正确实施 Excel 引号功能。

* 数据文件的第一行（非注释）包含用于标识该列中分类数据的列标题。导入器要求列标题采用特定的格式。有关详细信息，请参阅 [列标题格式](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_ADC08C783477451B959782CEA23AF5EF).
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
   <td colname="col1"> <p>&lt;新行&gt; </p> </td> 
   <td colname="col2"> <p>新行字符是在数据文件中的数据行/记录之间唯一受支持的分隔符。通常，您只需要在编写程序时专门插入这些字符，即可自动生成数据文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>要求 Adobe 自动为此元素生成唯一的 ID。 </p> <p>在促销活动环境中，此控制值会指示 Adobe 为每个创作元素指定一个标识符。请参阅 <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_0B77B3079B5C414F9956058688990443" format="dita" scope="local"> 键值 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>指定此数据列代表与此项目相关联的日期范围。请参阅 <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9ECCD5ED97764CDC90C0B7B0F9461825" format="dita" scope="local"> Date </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>空白字段 </p> </td> 
   <td colname="col2"> <p>表示当前字段的 NULL 值。如果特定数据列不适用于当前记录，则使用此控制代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER 修饰符 </p> </td> 
   <td colname="col2"> <p>指定此数据列代表 <span class="wintitle">PER 修饰符</span>字段。See <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_7E199A26E3274B31B07CCAF8DFE3B274" format="dita" scope="local"> PER Modifier Headings </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [常见上传问题](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)


## 列标题格式

>[!NOTE]
>
>Adobe 建议您将导入和导出列的数量限制为 30。

分类文件支持以下列标题：

### 键

在整个系统中，此值必须唯一。The value in this field corresponds to a value assigned to the [!DNL Analytics] variable in your Web site’s [!DNL JavaScript] beacon. Data in this column might include ~autogen~ or any other unique tracking code.

### 分类列标题

例如，Reports &amp; Analytics 自动包含两种[!UICONTROL 促销活动]变量分类：[!UICONTROL 促销活动]和[!UICONTROL 创作元素]。若要将数据添加到[!UICONTROL 促销活动]分类中，分类数据文件中的列标题应为[!UICONTROL 促销活动]。

>[!NOTE]
>
>[!UICONTROL “分类”] 列标题中的值必须与分类的命名约定完全匹配，否则导入将失败。例如，如果管理员在[!UICONTROL 促销活动设置管理器]中将[!UICONTROL 促销活动]更改为[!UICONTROL 内部促销活动名称]，则文件列标题必须随之更改。

此外，数据文件支持下列其他标题规范，用于标识子分类和其他特殊数据列：

### 子分类标题

例如，[!UICONTROL 促销活动^所有者]是包含[!UICONTROL 促销活动所有者]值的列的列标题。同样地，[!UICONTROL 创作元素^大小]是包含[!UICONTROL 创作元素]分类的[!UICONTROL 大小]子分类的列的列标题。

### 分类指标标题

例如，[!UICONTROL 促销活动^~成本]指的是[!UICONTROL 促销活动]分类中的[!UICONTROL 成本]量度。

### PER修饰符标题

*`Per Modifier`* 标题通过添加 *`~per`* 到分类量度标题表示。For example, if the *`Metric`* heading is *`Campaigns^~Cost`*, the PER modifier heading is *`Campaigns^~Cost~per`*. Adobe supports the following *`PER Modifier`* keywords:

这些字符在数据文件中有其特殊含义。因此，请尽量避免在属性名称或数据中使用这些字词。

**FIXED：**&#x200B;固定值。不进行任何缩放。

**DAY：**&#x200B;将该值乘以报表中的天数。

**ORDER：**&#x200B;将该值乘以报表中行项目的订单数。

**CHECKOUT：**&#x200B;将该值乘以报表中行项目的结账金额。

**UNIT：**&#x200B;将该值乘以报表中行项目的件数。

**REVENUE：**&#x200B;将该值乘以报表中行项目的收入金额。

**SCADD：**&#x200B;将该值乘以报表中每个行项目出现[!UICONTROL 购物车加货]事件的次数。

**SCREMOVE：**&#x200B;将该值乘以报表中每个行项目出现[!UICONTROL 购物车减货]事件的次数。

**INSTANCE：**&#x200B;将该值乘以报表中行项目的实例数。

**CLICK：**&#x200B;将该值乘以报表中行项目的点击数。

**EVENT：**&#x200B;将该值乘以报表中每个行项目出现特定客户事件的次数。

**示例：** 如果Campaign A成本$10,000， [!UICONTROL 则Campaigns^~ Cost] 列的值为10000， [!UICONTROL “营销活动”列~~] 中包含 [!UICONTROL 固定值]。在报表中显示促销活动 A 的成本时，会将 $10,000 显示为日期范围内促销活动 A 的固定成本。

**示例：** 如果Campaign B的点击价格约为$2， [!UICONTROL 则“营销活动”^~成本] 列包含2， **[!UICONTROL “营销活动”^~“每~]** 个列”列包含 [!UICONTROL 点击数]。When displaying the Cost for Campaign B in the reports, Adobe calculates (2 * [number of clicks]) on the fly for the date range of the report. 这样即可根据促销活动 B 的点击次数计算出总成本。

### 页面

促销活动日期通常是与各个促销活动关联的范围（开始日期和结束日期）。日期的格式应当为 YYYY/MM/DD。例如，2013/06/15-2013/06/30。

有关详细信息，请参阅[转化分类](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications)。

>[!NOTE]
>
>In the May 10, 2018, [!DNL Analytics] Maintenance release, Adobe started to limit the functionality of date-enabled and numeric classifications. 这些分类类型已从管理员和分类导入器界面中删除。无法添加新的启用日期的分类和数值分类。现有的分类仍可以通过标准分类工作流程进行管理（上传、删除），并将继续在报表中可用。

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL 分类] 可用于为营销活动或其他转化 [!UICONTROL 分类]分配日期范围，从而更准确地评估营销活动。指定值的日期范围后，该日期范围外任何匹配的值都不会进行分类。这对希望利用促销活动为“有效”，并且不是所有点击都与该促销活动本身匹配的具体日期的促销活动测量而言非常有用。要成功地用日期范围对值进行分类，必须满足以下条件：

* [!UICONTROL 分类] 必须基于转化变量。
* The [!UICONTROL classification] used must be set as Date-Enabled or Numeric 2.
* 涉及的日期范围必须包含开始日期和（可选）结束日期。

根据日期范围分类促销活动：

1. Log in to [!DNL Analytics] and go to Admin &gt; Classifications.
1. 单击&#x200B;**[!UICONTROL 浏览器导出]选项卡，确保启用日期的分类的设置均正确，然后单击“导出文件”。**
1. 在 Microsoft Excel 或您熟悉的其他电子表格编辑器中打开此文件。
1. 其中一列将以

   ^~period~
which is the column to enter the date range in.
1. 在此列下，按下面的格式输入每个值的日期范围：

   `YYYY/MM/DD - YYYY/MM/DD`。请务必遵循以下原则：

   * 在短划线的两侧保留空格。
   * 使用连字符 (-) 分开多个范围，而不要使用短划线或长划线。
   * 如果某月或某天是单个数字，则在其前面添加零。
   * 日期范围必须有一个开始日期，而结束日期是可选的。

1. Save the file, and upload it to [!DNL Analytics] by going to Admin | Classifications | Import File.

>[!NOTE]
>
>特定的键值不能有多个日期范围。

## 分类疑难解答

* [常见 上载问题](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)：知识库文章，描述由于文件格式以及文件内容不正确导致的问题。

