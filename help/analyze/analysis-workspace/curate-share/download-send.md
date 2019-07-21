---
description: 您可以下载 PDF 和 CSV 格式的已保存和未保存项目。
seo-description: 您可以下载 PDF 和 CSV 格式的已保存和未保存项目。
seo-title: 下载 PDF 或 CSV 文件
title: 下载 PDF 或 CSV 文件
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290 a48 ef5 f
translation-type: tm+mt
source-git-commit: b9e57162fae605719d7d85aad52a29165cb63fe4

---


# 下载 PDF 或 CSV 文件

您可以下载 PDF 和 CSV 格式的已保存和未保存项目。

PDF 或 CSV 文件的名称与项目的当前名称匹配。对于未保存的项目，已下载的文件包含项目中未保存的更改。请注意，无法计划 PDF 或 CSV 格式的未保存项目。

>[!NOTE]
>
>我们还支持CSV格式的流失可视化。

>[!NOTE]
>
>当我们将项目渲染到PDF时，我们只渲染页面上的内容。如果项目具有自定义大小的可视化和面板，则需要将它们更改为自动调整大小（右上角的按钮），以便内容将不会被截断。

1. 创建或打开一个项目。
1. Click **[!UICONTROL Project]** &gt; **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* 千位分隔符将不再包含在内。(The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components &gt; Report Settings &gt; Thousands Separator]**).
* 不显示货币符号。
* 不显示百分比符号。
* 百分比采用小数点形式；例如，75%表示为0.75。
* 时间以秒为单位显示。
* 同期表仅显示原始值；删除百分比。
* 如果某个数字无效，则会显示一个空单元格。

>[!Nte：]
>
> 将继续在导出的CSV中引述使用逗号作为小数点分隔符的数值。