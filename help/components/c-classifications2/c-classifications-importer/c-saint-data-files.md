---
description: 导入程序允许您将分类数据批量上传到文件中的分析报告。 导入需要特定文件格式才能成功上传数据。
subtopic: Classifications
title: 分类数据文件
topic: Admin tools
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 分类数据文件

导入程序允许您将分类数据批量上传到文件中的分析报告。 导入需要特定文件格式才能成功上传数据。

为了帮助您创建有效的数据文件，您可以下载一个模板文件，该模板文件提供了可粘贴分类数据的文件结构。 有关详细信息，请参阅[下载分类模板](/help/components/c-classifications2/c-classifications-importer/c-download-saint-data.md)。

请参阅[通用文件结构](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)，以了解有关分类中字符限制的详细信息。

请参阅[数值 2 分类](/help/components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md)，以了解有关使用数值 2 分类上载数据的信息。

## 通用文件结构

下图是示例数据文件：

![](assets/completed-saint-file.png)

数据文件必须遵循以下结构规则：

* 分类的值不能为0（零）。
* Adobe 建议您将导入和导出列的数量限制为 30。
* 上传的文件应使用UTF-8而不使用BOM字符编码。
* 特殊字符（如制表符、新行和引号）可以嵌入到单元格中，前提是指定了v2.1文件格式并正确转义该单元 [格](/help/components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md)。 特殊字符包括：

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   逗号不是特殊字符。

* 分类不能包含尖角(^)，因为此字符用于表示子分类。
* 使用连字符时要小心。 例如，如果您在 Social 术语中使用连字符 (-)，则 Social 会将连字符识别为 [!DNL Not] 运算符（减号）。例如，如果您使用导入指定 *`fragrance-free`* 作为术语，则 Social 会将该术语识别为 fragrance *`minus`* free，并收集提及 *`fragrance`*，但未提及 *`free`* 的帖子。
* 在对报表数据进行分类时必须执行字符限制。例如，如果上载产品名称长度超过 100 个字符（字节）的产品的分类文本文件 (*`s.products`*)，将不会在报表中显示这些产品。跟踪代码和所有自定义转化变量 (eVar) 允许 255 字节。
* 以制表符分隔的数据文件（可以使用任一款电子表格应用程序或文本编辑器来创建模板文件）。
* 使用 [!DNL .tab] 或 [!DNL .txt] 作为文件扩展名。
* 井号(#)将该行标识为用户评论。 Adobe将忽略以#开头的任何行。
* 多次-英镑符号后跟SC(## SC)将该行标识为报告使用的预处理标题注释。 请勿删除这些行。
* 分类导出可以具有重复键，因为键中有换行符。 在FTP或浏览器导出中，可通过打开FTP帐户的报价来解决此问题。 这将在每个键周围放置引号，并带有换行符。
* 导入文件第一行中的单元格C1包含一个版本标识符，它决定了分类如何处理在文件的其余部分中使用引号的问题。

   * v2.0会忽略引号，并假定它们都是指定键和值的一部分。 例如，请考虑以下值：“这是“某些值””。 v2.0会将其解释为：“这是“某些值””。
   * v2.1告诉分类假定引号是Excel文件中使用的文件格式的一部分。 因此，v2.1会将上述示例的格式设置为：这是“一些价值”。
   * 在文件中指定v2.1但实际需要v2.0时，可能会出现问题——即，当引号以Excel格式下非法的方式使用时。 例如，如果您有一个值：“VP NO REPS” S/l Dress with Overlay。 对于v2.1，这是不正确的格式（值应用开始和结束引号括起来，作为实际值一部分的引号应用引号转义），分类不会超出此范围。
   * 确保您执行下列操作之一：通过更改上传文件中的标题（单元格C1），将文件格式更改为v2.0，或在整个文件中正确实施Excel报价。

* 数据文件的第一行（非注释）包含用于标识该列中的分类数据的列标题。 导入程序需要列标题的特定格式。 有关详细信息，请参阅[列标题格式](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)。
* 数据文件中紧跟标题行的是数据行。 每行数据应包含每个列标题的数据字段。
* 该数据文件支持以下控制代码，Adobe使用这些代码为文件提供结构，并正确导入分类数据：

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 控制代码 </th> 
   <th colname="col2" class="entry"> 说明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;新行&gt; </p> </td> 
   <td colname="col2"> <p>新行字符是数据文件中数据行／记录之间唯一支持的分隔符。 通常，您只需在编写项目时专门插入这些字符即可自动生成数据文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>请求Adobe自动为此元素生成唯一ID。 </p> <p>在活动上下文中，此控制值指示Adobe为每个创作元素分配一个标识符。 请参阅 <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > 密钥 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>指定数据列表示与项目关联的日期范围。 请参阅 <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  > 日期 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>空字段 </p> </td> 
   <td colname="col2"> <p>表示当前字段的NULL值。 如果特定数据列不应用于当前记录，则使用此选项。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER修饰符 </p> </td> 
   <td colname="col2"> <p>指定此数据列代表 <span class="wintitle">PER 修饰符</span>字段。请参阅 <a href="/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md"  >PER 修饰符标题</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [常见上载问题](https://helpx.adobe.com/cn/analytics/kb/common-saint-upload-issues.html)


## 列标题格式

>[!NOTE]Adobe 建议您将导入和导出列的数量限制为 30。

分类文件支持以下列标题：

### 键

在整个系统中，此值必须唯一。此字段中的值对应于在您网站的 [!DNL JavaScript] 信标中分配给 [!DNL Analytics] 变量的值。该列中的数据可能包含 ~autogen~ 或任何其他唯一跟踪代码。

### 分类列标题

例如，报告和分析自动包括两个变量 [!UICONTROL Campaign] 分类： [!UICONTROL Campaigns] 和 [!UICONTROL Creative Elements]。 要向分类中添 [!UICONTROL Campaigns] 加数据，分类数据文件中的列标题应为 [!UICONTROL Campaigns]。

>[!NOTE] 列标题中的 [!UICONTROL Classifications] 值必须与分类的命名约定完全匹配，否则导入将失败。 例如，如果管理员在 [!UICONTROL Campaigns] 中更 [!UICONTROL Internal Campaign Names] 改为 [!UICONTROL Campaign Set-up Manager]，则文件列标题必须更改为匹配。

此外，该数据文件还支持以下其他标题惯例，以标识子分类和其他专用数据列：

### 子分类标题

例如， [!UICONTROL Campaigns^Owner] 是包含值的列的列标 [!UICONTROL Campaign Owner] 题。 同样， [!UICONTROL Creative Elements^Size] 该列的列标题也包含该分 [!UICONTROL Size] 类的子分 [!UICONTROL Creative Elements] 类。

### 分类量度标题

例如， [!UICONTROL Campaigns^~Cost] 引用分类 [!UICONTROL Cost] 中的度 [!UICONTROL Campaigns] 量。

### PER 修饰符标题

*`Per Modifier`* 标题的表示方式为将 *`~per`* 添加到分类量度标题。例如，如果 *`Metric`* 标题为 *`Campaigns^~Cost`*，则 PER 修饰符标题为 *`Campaigns^~Cost~per`*。Adobe 支持以下 *`PER Modifier`* 关键词：

这些字符在数据文件中具有特殊含义。 尽可能避免在属性名称和数据中使用这些词。

**修复：** 固定值。 请勿执行任何缩放。

**日：** 将该值乘以报表中的天数。

**订单：** 将该值乘以报表中行项目的订单数。

**结帐：** 将该值乘以报表中行项目的结帐次数。

**单位：** 将该值乘以报表中行项目的单位数。

**收入：** 将该值乘以报表中行项目的收入金额。

**SCADD:** 将该值乘以报表中每行项目 [!UICONTROL Shopping Cart Add] 调用事件的次数。

**屏幕移动：** 将该值乘以报表中每行项目 [!UICONTROL Shopping Cart Remove] 调用事件的次数。

**实例：** 将该值乘以报表中行项目的实例数。

**单击：** 将该值乘以报表中行项目的单击次数。

**事件:** 将该值乘以报表的每行项目出现指定自定义事件的次数。

**示例：** 如果活动A的费用为$10,000, [!UICONTROL Campaigns^~Cost] 则列包含值10000，而 [!UICONTROL Campaigns^~~Costper] 列包含 [!UICONTROL FIXED]。 在报表中显示促销活动 A 的成本时，会将 $10,000 显示为日期范围内促销活动 A 的固定成本。

**示例：** 如果活动B的每次点击费用约为$2，则列 [!UICONTROL Campaigns^~Cost] 包含2，而 **[!UICONTROL Campaigns^~~Costper]** 列包含 [!UICONTROL CLICK]。 在报表中显示促销活动 B 的成本时，Adobe 会随时计算报表日期范围内的成本（2 * [点击次数]）。这样即可根据促销活动 B 的点击次数计算出总成本。

### 页面

活动日期通常是与单个活动关联的范围(开始日期和结束日期)。 日期应以YYYY/MM/DD格式显示。 例如，2013/06/15-2013/06/30。

有关详细信息，请参阅 [转化分类](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications)。

>[!NOTE] 在 2018 年 5 月 10 日的 [!DNL Analytics] 维护版本中，Adobe 已开始限制启用日期的分类和数值分类的功能。这些分类类型已从管理员和分类导入器界面中删除。不能添加新的启用日期和数字分类。 现有的分类仍可以通过标准分类工作流程进行管理（上传、删除），并将继续在报表中可用。

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL Classifications] 可用于为活动或其他转换指定日期范围，这 [!UICONTROL classifications]样可以更准确地测量活动。 在指定值的日期范围后，不会对日期范围以外的任何匹配值进行分类。 这对于希望利用活动为“实时”的确切日期的活动度量很有用，而不是所有与活动本身匹配的点击。 要成功地将某个日期范围的值分类，必须满足以下条件：

* The [!UICONTROL classification] must be based on a conversion variable.
* The [!UICONTROL classification] used must be set as Date-Enabled or Numeric 2.
* 涉及的日期范围必须包含开始日期和（可选）结束日期。

要根据日期范围对活动进行分类，请执行以下操作：

1. 登录 [!DNL Analytics]，然后转到“管理员”>“分类”。
1. Click the **[!UICONTROL Browser Export]** tab, ensure the settings to your date-enabled classification are correct, then click Export File.
1. 在 Microsoft Excel 或您熟悉的其他电子表格编辑器中打开此文件。
1. 其中一列将以下面的内容结尾：

   ^~period~，
在该列中输入日期范围。
1. 在此列下，按下面的格式输入每个值的日期范围：

   `YYYY/MM/DD - YYYY/MM/DD`。请确保：

   * 在短划线的两侧保留空格。
   * 使用连字符(-)分隔范围，而不是短划线或短划线。
   * 如果月份或日期是一个数字，则表示前导零。
   * 日期范围必须有一个开始日期，而结束日期是可选的。

1. 保存文件，然后转到“管理员”|“分类”|“导入文件”，将文件上载至 [!DNL Analytics]。

>[!NOTE] 特定键值不得包含多个日期范围。

## 有关分类的疑难解答

* [常见 上载问题](https://helpx.adobe.com/cn/analytics/kb/common-saint-upload-issues.html)：知识库文章，描述由于文件格式以及文件内容不正确导致的问题。

