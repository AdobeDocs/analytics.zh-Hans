---
description: 未分类键在分类报表中分组为单行项目，标记为“无”。 可用于将“无”重命名为更具描述性的某些项目。
subtopic: Classifications
title: 未分类键值
feature: 管理工具
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
translation-type: tm+mt
source-git-commit: f52baf97efe20b209f51108995a0620b6c19bec0
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 62%

---

# 未分类键值

未分类键在分类报表中分组为单行项目，标记为“无”。 可用于将“无”重命名为更具描述性的某些项目。

## 未分类键值 {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

未分类键在分类报表中分组为标有&#x200B;*`None`*&#x200B;的单行项。 可用于将 *`None`* 重命名为更具描述性的某些项目。

例如，假设您的跟踪代码包含的信息可以勾勒跟踪代码所关联的移动活动的类型。 您正在使用分类（移动设备促销活动类型）将这些跟踪代码分到不同的类别中，如移动设备 Web、iOS 应用程序、Android 应用程序等等。某些促销活动可能不是移动设备促销活动，因此不会使用移动设备促销活动类型进行分类。所有未分类的跟踪代码将分到&#x200B;*`None`*（在[!UICONTROL 移动设备促销活动类型]报表中）。

## 重命名“无”分类键值 {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

描述如何对报表中显示为 *`none`* 的未分类键值进行重命名的步骤。

1. 使用导入器，将分类导入到本地文件。
1. 向文件中添加一行，然后在“键值”列中键入 `~none~`。
1. 在添加的行中，在相应的分类列中键入更具描述性的名称。

   要按照本文档中的示例进行操作，您可以在名为[!UICONTROL Mobile 活动 Type]的列中键入“非移动活动”。

   此条目将[!UICONTROL 移动活动类型]报表中的&#x200B;*`None`*&#x200B;重命名为&#x200B;*`non-mobile campaign`*。

   ![非分类键的示例](/help/components/classifications/importer/assets/non-classified-key.png)

1. [将数据导入](/help/components/classifications/importer/import-file.md)回系统中。
