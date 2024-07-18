---
description: 未分类键值在分类报告中作为标记为 None 的单个行项目分组。将 None 重命名为更具描述性的名称可能很有用。
title: 未分类键值
feature: Classifications
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 94%

---

# 未分类键值

未分类键值在分类报告中作为标记为 None 的单个行项目分组。将 None 重命名为更具描述性的名称可能很有用。

## 未分类键值 {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

未分类键值在分类报告中作为标记为 *`None`* 的单个行项目分组。将 *`None`* 重命名为更具描述性的名称可能很有用。

例如，假设跟踪代码包含的信息描述与跟踪代码关联的移动营销活动的类型。您正在使用分类（移动设备促销活动类型）将这些跟踪代码分到不同的类别中，如移动设备 Web、iOS 应用程序、Android 应用程序等等。某些促销活动可能不是移动设备促销活动，因此不会使用移动设备促销活动类型进行分类。在[!UICONTROL 移动设备促销活动类型]报表中，所有未分类的跟踪代码都将分组到&#x200B;*`None`*&#x200B;下。

## 重命名 None 分类键值 {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

重命名报告中显示为 *`none`* 的未分类键值：

1. 使用导入器，将分类导入到本地文件。
1. 向文件中添加一行，然后在“键值”列中键入 `~none~`。
1. 在添加的行中，在相应的分类列中键入更具描述性的名称。

   要遵循此文档中的示例，您可能要在名为[!UICONTROL 移动营销活动类型]的列中键入“非移动营销活动”。

   此条目会将[!UICONTROL 移动营销活动类型]报告中的 *`None`* 重命名为 *`non-mobile campaign`*。

   ![未分类键值示例](/help/components/classifications/importer/assets/non-classified-key.png)

1. [将数据导入](/help/components/classifications/importer/import-file.md)回系统中。
