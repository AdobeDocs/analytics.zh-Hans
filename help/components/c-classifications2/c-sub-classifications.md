---
description: Adobe Analytics 支持单级别和多级别分类模型。使用分类层次结构可以将分类应用到分类。
subtopic: Classifications
title: 关于子分类
topic: Admin tools
uuid: 48bd7fc1-54a1-40ef-bc55-395338522f2d
translation-type: tm+mt
source-git-commit: 0e97e28ffb2bf94acfb382c3f97ff30b31321467

---


# 关于子分类

Adobe Analytics支持单级和多级分类模型。 使用分类层次结构可以将分类应用到分类。

> [!NOTE] 子分类是指创建分类的分类的功能。However, this is not the same as a [!UICONTROL Classification Hierarchy] used to create [!UICONTROL Hierarchy] reports. 有关分类层次结构的详细信息，请参阅[分类层次结构](classification-hierarchies.md)。

例如：

![](assets/single-level-popup-C.png)

此模型中的每个分类都是独立的，并且对应于所选报表变量的新子报表。 此外，每个分类在数据文件中构成一个数据列，其中以分类名称为列标题。 例如：

| KEY | 属性1 | 属性2 |
|---|---|---|
| 123 | ABC | A12B |
| 456 | DEF | C3D4 |

For more information about the data file, see [Classification Data Files](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md).

多级分类由父级和子级分类组成。 例如：

![](assets/Multi-Level-Class-popup.png)

**父项分类：**&#x200B;父项分类是指具有一个关联子项分类的任何分类。分类可以是父分类和子分类。 顶级父分类与单级分类相对应(请参 [阅单级分类](/help/components/c-classifications2/c-sub-classifications.md))。

**子项分类：**&#x200B;子项分类是以其他分类而非变量做为其父项的分类。子分类提供有关其父分类的其他信息。 例如，某个分类可 [!UICONTROL Campaigns] 能具有“营销活动所有者”子分类。 [!UICONTROL Numeric] 分类在分类报告中也起到指标的作用。

每个分类（父类或子类）都构成数据文件中的一个数据列。 使用以下命名格式的子分类的列标题：

`<parent_name>^<child_name>`

有关数据文件格式的详细信息，请参阅[分类数据文件](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)。

例如：

| KEY | 属性1 | 属性 1&amp;Hat;属性 1-1 | 属性 1&amp;Hat;属性 1-2 | 属性 2 |
|---|---|---|---|---|
| 123 | ABC | 绿色 | 小 | A12B |
| 456 | DEF | 红色 | 大 | C3D4 |

尽管多级分类的文件模板更复杂，但多级分类的强大之处在于可以将不同级别上传为单独的文件。 此方法可以通过将数据分组为随时间变化的分类级别，而不是不随时间变化的分类级别，来使需要定期（每日、每周等）上传的数据量最小化。

> [!NOTE] 如果数 [!UICONTROL Key] 据文件中的列为空，Adobe会为每个数据行自动生成唯一的键。 要避免在上传包含二级或更高级分类数据的数据文件时可能发生文件损坏，请在列的每行中填入星号( [!UICONTROL Key] *)。

如需疑难解答帮助，请参阅[常见分类上载问题](https://marketing.adobe.com/resources/help/en_US/home/index.html#kb-common-saint-upload-issues)。

## 示例

![](assets/sample-product-classifications.png)

>[!NOTE] 产品分类数据仅受与产品直接相关的数据属性的限制，数据不限于产品在网站上的分类或销售方式。 销售类别、站点浏览节点或销售项目等数据元素不是产品分类数据。 相反，这些元素会在报表转换变量中捕获。

上传此产品分类的数据文件时，您可以将分类数据作为单个文件或多个文件上传（请参阅下文）。 通过将文件1中的颜色代码和文件2中的颜色名称分开，只有在创建新的颜色代码时，才需要更新颜色名称数据（可能只有几行）。 这会从更新较为频繁的文件 1 中消除颜色名称（代码&amp;Hat;颜色）字段，从而缩减在生成数据文件时的文件大小并降低复杂性。

### 产品分类 - 单个文件 {#section_E8C5E031869C449F9B636F5EB3BFEC17}

| KEY | 产品名称 | 产品详细信息 | 性别 | 大小 | 代码 | 代码&amp;Hat;颜色 |
|---|---|---|---|---|---|---|
| 410390013 | Polo-SS | Men&#39;s Polo Shirt, Short Sleeve(M,01) | 一 | 一 | 01 | Stone |
| 410390014 | Polo-SS | Men&#39;s Polo Shirt, Short Sleeve(L,03) | 一 | L | 03 | 希瑟 |
| 410390015 | Polo-LS | Women&#39;s Polo Shirt, Long Sleeve(S,23) | 五 | S | 23 | 水 |

### 产品分类——多个文件（文件1） {#section_A99F7D0F145540069BA4EEC0597FF13F}

| KEY | 产品名称 | 产品详细信息 | 性别 | 大小 | 代码 |
|---|---|---|---|---|---|
| 410390013 | Polo-SS | Men&#39;s Polo Shirt, Short Sleeve(M,01) | 一 | 一 | 01 |
| 410390014 | Polo-SS | Men&#39;s Polo Shirt, Short Sleeve(L,03) | 一 | L | 03 |
| 410390015 | Polo-LS | Women&#39;s Polo Shirt, Long Sleeve(S,23) | 五 | S | 23 |

### 产品分类——多个文件（文件2） {#section_19ED95C33B174A9687E81714568D56A3}

| KEY | 代码 | 代码&amp;Hat;颜色 |
|---|---|---|
| * | 01 | Stone |
| * | 03 | 希瑟 |
| * | 23 | 水 |
