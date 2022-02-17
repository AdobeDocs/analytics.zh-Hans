---
title: 分类概述
description: 自定义维度项目的分组。
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 100%

---

# 分类概述

分类是在生成报表时对 Analytics 变量数据进行分类，然后以不同的方式显示数据的方法。

有关 [Analytics 分类](https://video.tv.adobe.com/v/16853/)的视频概述。

**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > *`<Traffic or Conversion>`*

在分类时，您会在变量以及与该变量相关的元数据之间建立关系。分类最常用在促销活动中。通过将元数据应用到变量中收集的值，可以汇总使用变量（eVar、prop 和事件）信息收集的数据。

![步骤信息](assets/sub_class_create.png)

分类后，任何可使用关键变量生成的报表也可通过关联的属性来生成。例如，您可以使用其他产品属性（如产品名称、颜色、大小、描述和 SKU）对[!UICONTROL 产品 ID] 进行分类。以其他属性增强 Reports &amp; Analytics 数据，可让您生成更深入、更复杂的报表。

在创建分类后，您可以在 Adobe Analytics 中使用新的数据属性。

以下是一段关于 Adobe Analytics 分类的概述视频：

>[!VIDEO](https://video.tv.adobe.com/v/16853/?quality=12)

## 跟踪代码示例

假设您不通过跟踪代码来查看促销活动，而是要按照搜索引擎、关键词和促销活动渠道来查看促销活动结果。为此您不必费心研究上述每个项目的转化变量，而是可以为促销活动变量创建三个分类，以分别代表搜索引擎、关键词和促销活动渠道。使用这个策略，您可以按照所有四个变量来查看网站成功事件，而无需额外标记。

Reports &amp; Analytics 包含针对跟踪代码变量的预定义分类，从而提供以分类为基础的报表（名为“创作元素”和“促销活动”）。您必须针对其他所有转化和流量变量手动配置分类。

请参阅[流量分类](/help/admin/admin/c-traffic-variables/traffic-classifications.md)和[转化分类](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html?lang=zh-Hans)。

下表说明了各种可用的分类类型，以及支持这些分类的变量类型。请在上载数据文件之前，查看[通用文件结构](/help/components/classifications/importer/c-saint-data-files.md)中的相关信息。

<table id="table_279728C28D9C40EE832ACC9F211B5F17"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>类型 </p> </th> 
   <th colname="col2" class="entry"> <p>可用性 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 文本</span> </p> </td> 
   <td colname="col2"> <p>转化变量和流量变量 </p> </td> 
   <td colname="col3"> <p>文本分类所定义的类别，可让您为了报告目的将变量数据分组。 </p> <p>例如，如果您销售衬衫，可能会想按颜色、大小和样式将衬衫销售
（转化）分类，以便生成可让您查看按这些类别分组的衬衫销售报表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 启用日期的文本</span> </p> <p>注意：在 2018 年 5 月 10 日的 Analytics 维护版本中，Adobe 已开始限制启用日期的分类的功能。这些分类类型已从管理员和分类导入器界面中删除。无法添加新的启用日期的分类。现有的分类仍可以通过标准分类工作流程进行管理（上传、删除），并将继续在报表中可用。 </p> </td> 
   <td colname="col2"> <p>转化变量 </p> </td> 
   <td colname="col3"> <p>启用日期功能的文本分类，允许您为文本分类指定日期范围。该分类通常与促销活动分类一起使用，以便您充分利用<span class="wintitle">促销活动</span>报表中的“甘特图”视图。 </p> <p>您可以在填充分类数据的数据文件中，包含实际的促销活动日期。 </p> <p>即使促销活动结束日期已过，Reports &amp; Analytics 仍会收集促销活动跟踪代码，但是在促销活动结束日期之后收集的促销活动数据不会与促销活动产生关联。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 数值</span> <p>注意：在 2018 年 5 月 10 日的 Analytics 维护版本中，Adobe 已开始限制数字分类的功能。这些分类类型已从管理员和分类导入器界面中删除。无法添加新的数字分类。现有的分类仍可以通过标准分类工作流程进行管理（上传、删除），并将继续在报表中可用。 </p> </p> </td> 
   <td colname="col2"> <p>转化变量 </p> </td> 
   <td colname="col3"> <p>数值分类可让您将固定数值应用到<span class="wintitle">转化</span>报表。这些分类在报表中显示为量度。 </p> <p>考虑是否要添加<span class="wintitle">数值</span>分类时，数值必须是固定的，而且不会随着时间改变。 </p> </td> 
  </tr> 
 </tbody> 
</table>
