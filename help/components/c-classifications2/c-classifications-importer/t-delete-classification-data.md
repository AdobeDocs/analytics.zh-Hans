---
description: 描述如何删除或移除分类数据的步骤。
seo-description: 描述如何删除或移除分类数据的步骤。
seo-title: 删除分类数据
solution: Analytics
subtopic: 分类
title: 删除分类数据
topic: 管理工具
uuid: 5b1b0ac7-ee52-4fd8-b98 e-25283595cf0 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 删除分类数据

描述如何删除或移除分类数据的步骤。

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Browser Export]**.
1. 选择您要从中删除分类数据的报表包和数据集。
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. Once the file has been downloaded, open the file and replace any classification values you wish to delete with [!DNL ~empty~].

   Alternatively, use [!DNL ~deletekey~]. 此命令会视为指定键值从未出现过该分类。它会从查找表中完全删除该分类和任何列数据。

   **注意**：您只需要一列 [!DNL ~包含删除键~]。[!DNL ~空~] 命令可在单元格级别工作(键和列组合)，因此您需要 [!DNL ~在~] 要删除的分类列中留空。However, [!DNL ~deletekey~] works at the row level (the key and all associated metadata), so it only needs to appear in one of the columns in the row. 此命令可从行中删除所有元数据。Adobe 将此解释为从未对键值进行分类，并且将其显示在[无](../../../components/c-classifications2/c-classifications-importer/nonclassified-keys.md#concept_233E51DDF3084FF7B7EA89381C73C5FF)类别中。

1. 保存文件，并使用“[!UICONTROL 导入文件]”选项卡，将其上载。

   After you upload the file, the system recognizes [!DNL ~empty~] as a command to delete that classification value.

   **此命令的属性**

* [!DNL ~空~] 必须是不带空格的小写字母。以下输入无效：

   * [!DNL ~EMPTY~]
   * [!DNL ~ empty ~]
   * [!DNL ~Empty~]

* 您无法删除键值列中的值。这是直接传递到报表中的数据，将会永久保存。
* 如果删除具有子分类的分类值，则也会删除子分类。没有键值的分类无法存在，而子分类的父级是其键值。
* 可以在保持父分类完整的情况下，删除子分类数据。

