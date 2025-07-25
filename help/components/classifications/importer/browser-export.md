---
title: 浏览器导出
description: 使用浏览器导出功能，您可以将分类数据导出到以制表符分隔的文件中。
feature: Classifications
exl-id: f4c709b2-f707-4e3c-82ba-6b43def3e698
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 99%

---

# 浏览器导出（旧版）

使用浏览器导出功能，您可以将分类数据导出到以制表符分隔的文件中。

[!UICONTROL 管理员] > [!UICONTROL 分类导入器]

数据集文件是以制表符分隔的数据文件（文件扩展名为 .tab），大多数电子表格应用程序都支持这种文件。

>[!NOTE]
>浏览器导出具有 30 个列的限制。

## 字段描述

| 元素 | 描述 |
| --- | --- |
| 选择报表包 | 选择要从中导出报表数据的报表包。 |
| 要分类的数据集 | 从下拉菜单中，选择要分类的数据集。 |
| 选择行数 | 指定要导出多少行数据。<ul><li>选择&#x200B;**[!UICONTROL 全部]**&#x200B;可下载所有报表数据（至多 50,000 行）。</li><li>如果您要指定要下载的特定行数，请选择&#x200B;**[!UICONTROL 将数据行数限制为]**。</li></ul>如果您要下载的数据行数超过 50,000，请使用 FTP 下载选项。 |
| 按接收日期过滤 | （可选）根据收到数据的日期来过滤数据。指定要下载数据的日期范围。 |
| 应用数据过滤器 | （可选）根据数据标准来过滤数据集。可过滤下载的数据，以加入其中包括特定值的数据行或其中有列（分类）值未分配的数据行。在应用数据过滤器时，请考虑以下问题：<ul><li>您可以在定义数据过滤器时使用通配符。使用星号可匹配零个或多个字符，使用问号 `?` 可完全匹配一个字符。使用 `?*` 可匹配一个或多个字符。</li><li>通常，将两种类型的数据过滤器应用于下载内容时，系统只会下载两种规则都符合的行。但是，存在以下特例：<ul><li>如果带有空列的行 = 所有列，则除了第一个规则中指定的列以外，系统会检查所有列是否空白。此特例可确保系统下载符合下列情况的所有行：有一列符合第一个规则，而其他所有列都空白。</li><li>根据空白列下载数据行时，除了第一个规则中指定的列以外，系统会检查所有列是否空白。</li><li>如果为同一个列指定了两种过滤器规则（几乎不可能同时符合两个条件），则系统只会下载符合第一个规则的行。</li></ul></ul> |
| 数据过滤器 | （可选）根据促销活动数据来过滤数据。您可以仅下载来自处于活动状态的促销活动的数据，或选择在特定的日期范围内开始（或结束）的促销活动。<br>**重要说明**：此选项不适用于启用新分类架构的报表包。 |
| 导出数值 2 | 您可以使用导入器将数值 2 分类导入系统。数值 2 分类很适合用于针对不同项目（例如营销渠道报表的成本与预算值）随时间变化的变量。请参阅“数值 2 分类”，了解有关使用数值 2 分类上传数据的信息。 |
| 编码 | 选择数据文件的字符编码。默认的编码格式为 UTF-8 或 ISO-8859-1，具体情况取决于用来分类而上传的编码。UTF-8 到 UTF-16 可将您的使用 UTF-8 编码的分类转换为 UTF-16 编码。ISO-8859-1 到 UTF-16 可将您的使用 ISO-8859-1 编码的分类转换为 UTF-16 编码。<br>**注意：**&#x200B;如果您选择转换为 UTF-16，那么源编码必须与最初上传的编码相匹配，否则会出现意外结果。我们建议使用不带 BOM 的 UTF-8 格式编码所有已上传的文件。 |
| 为输出加引号 | 为分类文件指定版本 2.1。此设置将在特殊字符两端加上引号，以确保当 eVar 值中存在换行符时，导出的内容在 Excel 中有效。您可以通过打开已下载的文件确定分类文件是否为 2.1 版本。您将在标题中看到 v2.1。例如：`## SC SiteCatalyst SAINT Import File v:2.1` |

## 使用浏览器导出分类数据

1. 单击[!UICONTROL 管理员] > [!UICONTROL 分类导入器]。
1. 单击[!UICONTROL 浏览器导出]选项卡。
1. 指定数据集详细信息。
1. 单击[!UICONTROL 导出文件]。
1. 将数据集保存到您的本地系统中。
