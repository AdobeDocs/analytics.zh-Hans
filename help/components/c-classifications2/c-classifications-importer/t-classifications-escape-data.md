---
description: 描述如何转义分类文件中的分类数据的步骤。
solution: Analytics
subtopic: Classifications
title: 转义分类数据
topic: Admin tools
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 转义分类数据

描述如何转义分类文件中的分类数据的步骤。

<!--Meike, please check this page against orginal. It might be missing information. -->

1. 确保分类文件格式为 v2.1。

   如果已启用 v2.1，则会看到一行，类似于：

   >[!NOTE]
   >
   >To specify a format of v2.1, enable **[!UICONTROL Quoted Output]** when exporting the file on the [!UICONTROL Classification Importer] page ( [!UICONTROL Browser Export] or [!UICONTROL FTP Export]).

1. Surround the field containing special characters in double quotes (`"`).

A double quote character can appear in an escaped cell by replacing it with two double quote characters (`" "`). 例如：

```
My String "of data"
```

转义后将是：

```
"My String ""of data"""
```
