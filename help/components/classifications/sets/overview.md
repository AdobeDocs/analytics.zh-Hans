---
title: 分类集概述
description: 了解如何使用分类集管理分类数据。了解分类集与旧版分类有何不同。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: e1ccd006336f10b8f843d59cfdcd220064524349
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 100%

---

# 分类集概述

分类集提供单一界面来管理分类和规则。此工作流将[报告包设置](/help/admin/tools/manage-rs/report-suites-admin.md)中的分类创建与[分类导入器](/help/components/classifications/sets/manage-sets.md)结合起来。结果是一个用于创建和管理分类数据的直观界面。


## 分类集与旧版分类

分类集和旧版分类的主要区别在于，分类集将所有功能集中在一个界面中，而旧版分类需要三个界面。

### 旧版分类

![旧版分类](/help/components/classifications/sets/assets/classifications-legacy.svg)

在旧版分类中，每一个分类![架构](/help/assets/icons2/Schema.svg)（如流量、转化、营销渠道等的架构）都有自己的维度（键 ![键](/help/assets/icons2/Key.svg)）。您将这些分类定义为[报告包设置](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)的一部分。

在规则集中，您将规则 ![BidRule](/help/assets/icons/BidRule.svg) 单独定义为[分类规则生成器](/help/components/classifications/crb/classification-rule-builder.md)界面的一部分。在这个界面中，您将一个规则集与一个或多个报告包相关联。

您使用[分类导入器](/help/components/classifications/importer/c-working-with-saint.md)下载模板 ![DocumentFragment](/help/assets/icons/DocumentFragment.svg)，导入 ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) 分类，或从报告包-键（数据集）组合中导出![下载](/help/assets/icons/Download.svg)分类。



### 分类集

![分类集](./assets/classifications-sets.svg)

分类集将所有的旧版分类界面组合成为一个界面。每个分类集定义了：

* 一个或多个订阅，这是报告包![数据](/help/assets/icons2/Data.svg)和您想分类的维度![键](/help/assets/icons2/Key.svg)（key）的组合。如果您要根据产品 SKU 对产品分类，可以定义所有具有合适产品 SKU 维度的报告包。您不必像在旧版分类界面中那样在各报告包中复制分类。
* 此键的分类![模式](/help/assets/icons2/Schema.svg) （schema）的列表。例如，您可以为产品分类指定类别、颜色、大小、性别等。定义分类后，您可以下载模板 ![DocumentFragment](/help/assets/icons/DocumentFragment.svg)，上传 ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) 分类数据，下载![下载](/help/assets/icons/Download.svg)分类数据等。
* 一个或多个支持分类的规则 ![BidRule](/help/assets/icons/BidRule.svg)。


要从 Adobe Analytics 界面中的&#x200B;**[!UICONTROL 组件]**&#x200B;菜单访问&#x200B;**[!UICONTROL 分类集]**，您必须是产品管理员或属于一个包含权限项[!UICONTROL 报告包工具] > [!UICONTROL 分类]的产品轮廓。请注意，可通过&#x200B;**[!UICONTROL 管理员]**&#x200B;菜单使用旧版分类管理界面。

分类集由三个功能区组成：

* [**[!UICONTROL 分类集]**](manage-sets.md)：创建、编辑和删除分类集。
* [**[!UICONTROL 作业]**](job-manager.md)：查看分类集作业的状态。
* [**[!UICONTROL 合并]**](consolidations/manage.md)：将多个分类集合并为一个分类集。


## 工作流

分类集的工作流通常涉及以下步骤：

1. 考虑您想为哪些报告包和维度组合创建分类集。例如，您可以为任何报告包定义一个产品分类集，以便对产品进行更详细的分类。例如，类别和颜色等详细信息。
1. [创建一个分类集](/help/components/classifications/sets/create-set.md)，其中包含一个或多个报告包的订阅和用于识别产品的键维度组合。例如：

   | 报告包 | 关键维度 |
   |---|---|
   | 报告包 1 | 产品 ID |
   | 报告包 2 | 产品 SKU |

1. [将您已标识的分类](/help/components/classifications/sets/manage/schema.md#add)添加到分类集模式中。例如：

   | 分类名称 | 标识名称 |
   |---|---|
   | 类别 | 类别 |
   | 颜色 | 颜色 |

1. 手动创建一个包含分类数据的文件。[使用模板](/help/components/classifications/sets/manage/schema.md#template)，以确保您为此文件使用[受支持的文件格式](data-files.md#classification-set-file-formats)和列。然后将数据添加到模板文件中。

   或者，您也可以直接从产品目录中将数据导出为[受支持的文件格式](data-files.md#classification-set-file-formats)，其中的列符合模板。例如 CSV 文件，如：

   ```
   Key,Category,Color
   Adobe Nike Tech Fleece Full-Zip Hoodie - Men's,Men,Black
   Adobe Nike Tech Fleece Full-Zip Hoodie - Women's,Women,Black
   Men's North Face Adobe Jacket,Men,Black
   Nike Air Hybrid 2 Golf Bag,Equipment,Blue
   STITCH&reg; Ultimate Garment Bag,Equipment,Brown
   Adobe Analytics Training Tee - Navy,Men,Navy
   AirPods Pro 2,Electronics,White
   Adobe Analytics Training Tee - Green,Men,Green
   Women's North Face Adobe Jacket,Women,Blue
   Adobe Analytics Training Tee - Grey,Men,Gray
   Adobe Analytics One Million Views - Grey,Equipment,Grey
   Adobe and MGM Tee - White,Women,White
   Adobe and MGM Tee - Charcoal,Women,Charcoal
   ```

   在分类数据文件中，您引用`Key`每个报告包的键维度（例如：**[!UICONTROL 产品 ID]** 和&#x200B;**[!UICONTROL 产品 SKU]**）。您用&#x200B;**[!UICONTROL 分类名称]**&#x200B;引用每个分类（例如 `Category` 或 `Color`）。

1. 将包含分类数据的文件[上传](/help/components/classifications/sets/manage/schema.md#upload)到分类集模式中。

1. 设置用于自动对进入的数据和过去的数据进行分类的[规则](manage/rules.md)。

1. 通过使用云位置，[自动](/help/components/classifications/sets/manage/schema.md#automate)更新您希望反映在分类数据中的产品目录。

1. [下载](/help/components/classifications/sets/manage/schema.md#download)您的分类数据以验证内容。

1. [检查作业历史记录](/help/components/classifications/sets/job-manager.md)，以查看您对分类操作的结果（上传、下载、模板等）。
1. 如果您从旧版分类功能迁移后产生了多个相似的分类集，请[合并](consolidations/manage.md)这些分类集。



## 改进

与分类集一起发布的后端架构包含几项改进：

* 减少处理时间（从 72 小时减少到 24 小时）。
* 重新设计了用于管理分类的用户界面。
* 通过[适用于分类数据的 Adobe Analytics 源连接器](https://experienceleague.adobe.com/cn/docs/experience-platform/sources/connectors/adobe-applications/classifications)在 Adobe Experience Platform 中使用分类数据的选项。

与分类集一起发布的后端架构还包含几项更改：

* 使用浏览器或自动导入时，会始终启用&#x200B;**[!UICONTROL 冲突时覆盖]**&#x200B;功能。
* 使用浏览器或自动导入时，不再支持导入后立即导出的选项。“导出”必须单独启动。
* Analytics 2.0 `GetDimensions` API 端点现在会返回用于分类的字符串标识符，而不是数值标识符。数值标识符仍然可以使用，但建议尽可能使用新的字符串标识符。可以使用 `?expansion=hidden` 查询字符串参数检索数字标识符。

>[!IMPORTANT]
>
>分类集的性能主要取决于包含数据的唯一键值的数量。当您使用的变量包含大量唯一值时，请务必谨慎。将多个报告包中的这类变量和维度合并到一个分类集中时，尤其要注意这一点。
