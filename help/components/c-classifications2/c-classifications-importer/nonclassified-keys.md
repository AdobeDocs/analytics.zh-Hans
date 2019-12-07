---
description: 未分类键值在分类报表中分在一起，作为标记为“无”的一行项目。可用于将“无”重命名为更具描述性的某些项目。
subtopic: Classifications
title: 未分类键值
topic: Admin tools
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 未分类键值

未分类键值在分类报表中分在一起，作为标记为“无”的一行项目。可用于将“无”重命名为更具描述性的某些项目。

## 未分类键值 {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

未分类键值在分类报表中分在一起，作为标记为 *`None`* 的一行项目。可用于将 *`None`* 重命名为更具描述性的某些项目。

例如，假设跟踪代码包含的信息描述了与跟踪代码关联的移动设备促销活动的类型。您正在使用分类（移动设备促销活动类型）将这些跟踪代码分到不同的类别中，如移动设备 Web、iOS 应用程序、Android 应用程序等等。某些促销活动可能不是移动设备促销活动，因此不会使用移动设备促销活动类型进行分类。所有未分类的跟踪代码将分到&#x200B;*`None`*（在[!UICONTROL 移动设备促销活动类型]报表中）。

## 重命名“无”分类键值 {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

描述如何对报表中显示为 *`none`* 的未分类键值进行重命名的步骤。

1. 使用导入器，将分类导入到本地文件。
1. 向文件中添加一行，然后在“键值”列中键入 [!DNL ~none~]。
1. 在添加的行中，在相应的分类列中键入更具描述性的名称。

   要遵循此文档中的示例，您可能要在名为[!UICONTROL 移动设备促销活动名称]的列中键入“非移动设备促销活动”。

   此条目会将“*移动设备促销活动类型`None`”报表中的**`non-mobile campaign`重命名为*。
1. [将数据导入](/help/components/c-classifications2/c-classifications-importer/import-file.md)回系统中。
