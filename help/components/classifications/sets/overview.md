---
title: 分类集概述
description: 了解如何使用分类集管理分类数据。 了解分类集与旧版分类有何不同。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: b3616a8667ce35dbfd856244a24b8b552528946c
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 9%

---

# 分类集概述

分类集提供单一界面来管理分类和规则。此工作流将在报告包设置中创建的分类与[分类导入器](/help/components/classifications/sets/manage/set-manager.md)相结合。 结果是创建和管理分类数据的单一直观界面。


## 分类集与旧版分类

分类集和旧版分类的主要区别在于，分类集将所有功能整合到一个界面中，而旧版分类依赖于三个界面。

### 旧版分类

![旧分类](./assets/classifications-legacy.svg)

在旧版分类中，分类![架构](/help/assets/icons2/Schema.svg)（如流量、转化、营销渠道等）都有各自的维度（键![键](/help/assets/icons2/Key.svg)）。 将这些分类定义为[报表包设置](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)的一部分。

在规则集中将规则![BidRule](/help/assets/icons/BidRule.svg)单独定义为[分类规则生成器](/help/components/classifications/crb/classification-rule-builder.md)界面的一部分。 在该界面中，您将规则集与一个或多个报表包关联。

您使用[分类导入器](/help/components/classifications/importer/c-working-with-saint.md)下载模板![DocumentFragment](/help/assets/icons/DocumentFragment.svg)，将![UploadToCloud](/help/assets/icons/UploadToCloud.svg)分类导入报表包，或从报表包中导出![下载](/help/assets/icons/Download.svg)分类 — 键（数据集）组合。


### 分类集

![分类集](./assets/classifications-sets.svg)

分类集将所有的旧版分类界面组合在一起。 每个分类集定义：

* 您要分类的一个或多个订阅，是报表包![Data](/help/assets/icons2/Data.svg)和维度![键](/help/assets/icons2/Key.svg) （键）的组合。 如果您要根据产品SKU对产品进行分类，则可以定义所有具有适用产品SKU维度的报表包。 您也不必像在旧版分类界面中那样跨报表包复制分类。
* 键的分类![架构](/help/assets/icons2/Schema.svg) （架构）列表。 例如，对于产品分类，您可以指定类别、颜色、大小、性别等。 定义分类后，您可以下载模板![DocumentFragment](/help/assets/icons/DocumentFragment.svg)、上传![UploadToCloud](/help/assets/icons/UploadToCloud.svg)分类数据、下载![下载](/help/assets/icons/Download.svg)分类数据等。
* 一个或多个规则![竞价规则](/help/assets/icons/BidRule.svg)支持分类。


要从Adobe Analytics界面的&#x200B;**[!UICONTROL 组件]**&#x200B;菜单访问&#x200B;**[!UICONTROL 分类集]**，您必须是产品管理员或属于包含权限项[!UICONTROL 报表包工具] > [!UICONTROL 分类]的产品配置文件。 请注意，旧版分类管理界面可从&#x200B;**[!UICONTROL 管理员]**&#x200B;菜单使用。

分类集包括三个功能领域：

* [**[!UICONTROL 分类集]**](manage/set-manager.md)：创建、编辑和删除分类集。
* [**[!UICONTROL 作业]**](job-manager.md)：查看分类集作业的状态。
* [**[!UICONTROL 合并]**](consolidations/manage.md)：将多个分类集合并为单个分类集。


## 工作流

分类集的工作流通常涉及以下步骤：

1. 考虑要创建分类集的报表包和维度组合。 例如，定义您为任何要为其分类产品的报告包创建的产品分类集，其中包含更多详细信息。 例如，类别和颜色等详细信息。
1. [创建一个分类集](/help/components/classifications/sets/manage/create.md)，该分类集包含用于标识产品的一个或多个报表包和键维度组合的订阅。 例如：

   | 报告包 | 关键维度 |
   |---|---|
   | 报告包1 | 产品 ID |
   | 报告包2 | 产品 SKU |

1. [将已识别的分类](/help/components/classifications/sets/manage/schema.md#add)添加到分类集架构中。 例如：

   | 分类名称 | 标识名称 |
   |---|---|
   | 类别 | 类别 |
   | 颜色 | 颜色 |

1. 手动创建包含分类数据的文件。 [使用模板](/help/components/classifications/sets/manage/schema.md#template)以确保使用支持的[文件格式](data-files.md#classification-set-file-formats)和文件列。 然后，将数据添加到模板文件中。

   或者，您可以直接从产品目录中以[支持的文件格式](data-files.md#classification-set-file-formats)导出数据，其列符合模板。 例如，CSV文件，如：

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

   在分类数据文件中，使用&#x200B;**[!UICONTROL 引用每个报表包的键维度（例如：]**&#x200B;产品ID **[!UICONTROL 和]**&#x200B;产品SKU`Key`）。 您使用&#x200B;**[!UICONTROL 分类名称]**&#x200B;引用每个分类（例如`Category`或`Color`）。

1. [将包含分类数据的文件上传](/help/components/classifications/sets/manage/schema.md#upload)到分类集架构中。

1. 设置[规则](manage/rules.md)以自动对传入数据和过去的数据进行分类。

1. [自动](/help/components/classifications/sets/manage/schema.md#automate)通过使用云位置对要显示在分类数据中的产品目录进行更新的过程。

1. [下载](/help/components/classifications/sets/manage/schema.md#download)分类数据以验证内容。

1. [检查作业历史记录](/help/components/classifications/sets/job-manager.md)以查看分类操作的结果（上传、下载、模板等）。
1. 如果由于从旧版分类功能迁移而产生了多个相似的分类集，请[合并](consolidations/manage.md)这些分类集。



## 改进

随分类集一起发布的后端架构包含多项改进：

* 缩短处理时间（从72小时缩短到24小时）。
* 重新设计了用于管理分类的用户界面。
* 用于通过[Adobe Experience Platform源连接器在Adobe Analytics中使用分类数据](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/adobe-applications/classifications)的选项。

随分类集一起发布的后端架构还包含几项更改：

* 使用浏览器或自动导入时，始终启用&#x200B;**[!UICONTROL 在冲突时覆盖]**。
* 使用浏览器或自动导入时，不再支持导入后立即导出的选项。“导出”必须单独启动。
* Analytics 2.0 `GetDimensions` API端点现在返回分类的字符串标识符，而不是数值标识符。 仍可使用数字标识符，但建议尽可能使用新的字符串标识符。 可以使用 `?expansion=hidden` 查询字符串参数检索数字标识符。

>[!IMPORTANT]
>
>分类集的性能主要取决于包含数据的唯一键值的数量。当您的变量包含大量唯一值时，请务必谨慎。 特别是当您将来自多个报告包和维度的此类变量组合到一个分类集中时。

## 限制

* 分类集尚不支持规则。 在[旧版规则生成器](/help/components/classifications/crb/classification-rule-builder.md)功能不可用之前，已将规则功能添加到分类集界面。
* 不会将旧版分类规则和配置迁移到分类集。 在旧版分类功能变得不可用之前，迁移实用程序会添加到分类集界面中。
