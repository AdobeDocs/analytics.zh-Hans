---
description: 分类是在生成报表时对 Analytics 变量数据进行分类，然后以不同的方式显示数据的方法。
subtopic: Classifications
title: 关于分类
topic: Admin tools
uuid: abc1a1be-8e37-4b7e-81fd-3e99ac27fc6a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 关于分类

分类是在生成报表时对 Analytics 变量数据进行分类，然后以不同的方式显示数据的方法。

有关 [Analytics 分类](https://video.tv.adobe.com/v/16853/?captions=chi_hans)的视频概述。

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > *`<Traffic or Conversion>`*

在分类时，您将在变量和与该变量相关的元数据之间建立关系。 分类在活动中最常用。 通过使用变量(eVar、prop和事件)信息收集的数据可以通过将元数据应用到变量中收集的值来累积起来。

![步骤信息](assets/sub_class_create.png)

分类后，您可以使用关键变量生成的任何报告也可以使用关联的属性生成。 例如，您可以使用其 [!UICONTROL Product IDs] 他产品属性（如产品名称、颜色、大小、说明和SKU）进行分类。 利用其他属性来增强报告和分析数据提供了更深入、更复杂的报告机会。

>[!IMPORTANT]
>
>已从代码库中移除了导入数字 2 分类和启用日期的分类的功能。此更改将在2019年6月维护版本中生效。 如果您的导入文件中包含“数字”或“启用日期”列，则这些单元格会被静默忽略，同时该文件中的任何其他数据均会正常导入。现有的分类仍可以通过标准分类工作流程导出，并将继续在报表中可用。

>[!NOTE] 在 2018 年 5 月 10 日的 Analytics 维护版本中，Adobe 已开始限制启用日期的分类和数值分类的功能。这些分类类型已从管理员和分类导入器界面中删除。不能添加新的启用日期和数字分类。 现有的分类仍可以通过标准分类工作流程进行管理（上传、删除），并将继续在报表中可用。

在创建分类后，您可以在 Adobe Analytics 中使用新的数据属性。

**跟踪代码示例**

假定您希望按搜索引擎、关键字和活动活动来查看活动结果，而不是只按跟踪代码查看渠道。 您不必为其中的每个变量分配活动变量，而是可以创建用于表示搜索引擎、关键字和活动渠道的三个分类。 此策略允许您通过所有四个变量查看网站成功事件，无需添加标签。

报告和分析包括跟踪代码变量的预定义分类，这些基于优惠分类的报告称为创作元素和活动。 您必须为所有其他转化和流量变量手动配置分类。

请参 [阅流量分类](/help/admin/admin/c-traffic-variables/traffic-classifications.md) 和转 [化分类](https://marketing.adobe.com/resources/help/zh_CN/reference/conversion_classifications.html)。

下表描述了可用的不同分类类型以及支持这些分类的变量类型。 在上传数据文件之 [前，请查看“常规文件结构](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) ”中的信息。

<table id="table_279728C28D9C40EE832ACC9F211B5F17"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>类型 </p> </th> 
   <th colname="col2" class="entry"> <p>可用性 </p> </th> 
   <th colname="col3" class="entry"> <p>说明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 文本</span> </p> </td> 
   <td colname="col2"> <p>转换和流量变量 </p> </td> 
   <td colname="col3"> <p>文本分类定义了类别，允许您为报告目的对变量数据进行分组。 </p> <p>例如，如果您销售衬衫，您可能希望按颜色、大小和样式对衬衫销售（转换）分类，以便生成报告，以便查看按这些类别组织的衬衫销售。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 启用日期的文本</span> </p> <p>注意：在 2018 年 5 月 10 日的 Analytics 维护版本中，Adobe 已开始限制启用日期的分类的功能。这些分类类型已从管理员和分类导入器界面中删除。无法添加新的启用日期的分类。现有的分类仍可以通过标准分类工作流程进行管理（上传、删除），并将继续在报表中可用。 </p> </td> 
   <td colname="col2"> <p>转化变量 </p> </td> 
   <td colname="col3"> <p>通过启用日期的文本分类，您可以为文本分类分配日期范围。 该分类通常与促销活动分类一起使用，以便您充分利用<span class="wintitle">促销活动</span>报表中的“甘特图”视图。 </p> <p>您可以在填充分类数据的数据文件中，包含实际的促销活动日期。 </p> <p>即使促销活动结束日期已过，Reports &amp; Analytics 仍会收集促销活动跟踪代码，但是在促销活动结束日期之后收集的促销活动数据不会与促销活动产生关联。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 数值</span> <p>注意：在 2018 年 5 月 10 日的 Analytics 维护版本中，Adobe 已开始限制数字分类的功能。这些分类类型已从管理员和分类导入器界面中删除。无法添加新的数字分类。现有的分类仍可以通过标准分类工作流程进行管理（上传、删除），并将继续在报表中可用。 </p> </p> </td> 
   <td colname="col2"> <p>转化变量 </p> </td> 
   <td colname="col3"> <p>数值分类可让您将固定数值应用到<span class="wintitle">转化</span>报表。这些分类在报表中显示为量度。 </p> <p>考虑是否要添加<span class="wintitle">数值</span>分类时，数值必须是固定的，而且不会随着时间改变。 </p> </td> 
  </tr> 
 </tbody> 
</table>

