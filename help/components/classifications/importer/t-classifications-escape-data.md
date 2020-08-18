---
description: 描述如何转义分类文件中的分类数据的步骤。
subtopic: Classifications
title: 转义分类数据
topic: Admin tools
uuid: 724edcc5-4990-4f24-afbb-9aef301791a7
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 100%

---


# 转义分类数据

描述如何转义分类文件中的分类数据的步骤。

<!--Meike, please check this page against orginal. It might be missing information. -->

1. 确保分类文件格式为 v2.1。

   如果已启用 v2.1，则会看到一行，类似于：

   >[!NOTE]
   >
   >要指定 v2.1 格式，请在“**[!UICONTROL 分类导入器]**”页面中导出文件时启用[!UICONTROL 为输出加引号]（“[!UICONTROL 浏览器导出]”或“[!UICONTROL FTP 导出]”）。

1. 为包含特殊字符的字段加上双引号 (`"`)。

可通过将一个双引号字符替换为两个双引号字符 (`" "`) 的方式，让其显示在已转义的单元格内。例如：

```
My String "of data"
```

转义后将是：

```
"My String ""of data"""
```
