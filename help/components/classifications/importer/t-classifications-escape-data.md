---
description: 描述如何转义分类文件中的分类数据的步骤。
title: 转义分类数据
feature: Classifications
exl-id: 0d3a0e91-5537-43ee-bd28-9907ee6eb331
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: ht
source-wordcount: '100'
ht-degree: 100%

---

# 转义分类数据

转义分类文件中的分类数据：

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
