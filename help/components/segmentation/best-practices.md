---
title: 分段最佳实践
description: 创建可高效返回数据的最佳区段。
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 62%

---

# 分段最佳实践

要获得理想的数据，通常需要复杂的区段。如果复杂的区段效率低下并应用于大型报表包，则可能需要很长时间来运行报表。在创建或编辑区段时，请考虑使用以下资源来最大限度地降低复杂性。

## 仅使用`Contains`运算符作为最后手段

[**[!UICONTROL Contains &#x200B;]**&#x200B;运算符](/help/components/segmentation/seg-reference/seg-operators.md)是分段中处理最密集的功能之一，因为该运算符必须分析每个值的全部内容。 如果所需值位于字符串的开头或结尾，请考虑使用其他运算符，如&#x200B;**[!UICONTROL &#x200B; Starts with &#x200B;]**&#x200B;或&#x200B;**[!UICONTROL &#x200B; Ends with &#x200B;]**。

如果区段中的&#x200B;**[!UICONTROL Contains]**&#x200B;运算符返回大量结果，报表通常会超时。 例如，如果您创建了一个区段，其中&#x200B;**[!UICONTROL 反向链接]** **[!UICONTROL 等于]** `"."`，则该区段会搜索每个值的内容。 请考虑改用&#x200B;**[!UICONTROL 存在]**&#x200B;运算符。

## 使用分类对维度项目进行分组

如果您有许多区段条件，它们会快速降低区段性能。例如，**[!UICONTROL Page]** **[!UICONTROL equals]** `X` **[!UICONTROL OR]** **[!UICONTROL Page]** **[!UICONTROL equals]** `Y` **[!UICONTROL OR]** **[!UICONTROL Page]** **[!UICONTROL equals]** `Z`重复了数百个不同的值。 可将所有所需值分类到某个区段，然后在区段中使用分类值，而不是写出数百个条件。

1. 为要处理的变量创建分类。
2. 下载分类模板，然后在所需的电子表格或文本编辑器中打开该模板。
3. 为要包含在区段中的每个维度项目指定相同的值。
4. 使用分类导入器将电子表格导回到 Adobe Analytics
5. 分类处理完成后，使用分类值创建一个区段。

这种方法可极大地提高性能，也是修改区段条件的一种简便方式。您可以在分类中添加或删除维度项目，而不是使用不同的值编辑区段。
