---
description: 您可以使用浏览器导入（上载）分类数据。此方法仅限将分类数据上载到单个报表包。
seo-description: 您可以使用浏览器导入（上载）分类数据。此方法仅限将分类数据上载到单个报表包。
seo-title: 浏览器导入
solution: Analytics
subtopic: 分类
title: 浏览器导入
topic: 管理工具
uuid: 56dfbf4c-36e6-49f4-b5 cb-8ab714432825
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 浏览器导入

您可以使用浏览器导入（上载）分类数据。此方法仅限将分类数据上载到单个报表包。

## Browser import {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

您可以使用浏览器导入（上载）分类数据。此方法仅限将分类数据上载到单个报表包。

**[!UICONTROL 管理员]** &gt; **[!UICONTROL 分类导入程序]**

## 分类浏览器导入 - 字段描述 {#section_F628C47081DA4026A4D30E3D3454B1DA}

<table id="table_7FC7E510E7E74C2D9E8F316C5C6B66DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 选择报表包 </td> 
   <td colname="col2"> <p>您要将分类数据导入其中的报表包。导入数据文件必须与报表包中数据集的格式相匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 要分类的数据集 </td> 
   <td colname="col2"> <p>要接收分类的数据集。该下拉列表包含报表包中针对分类配置的所有报表。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 选择文件以导入 </td> 
   <td colname="col2"> <p>让您浏览以查找要上载的导入数据文件。 </p> <p>注意：上载文件大小限制为 1 MB。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 覆盖冲突的数据 </td> 
   <td colname="col2"> <p>自动覆盖与导入的数据存在冲突的现有数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完成导入后自动下载分类文件 </td> 
   <td colname="col2"> <p>自动下载以制表符分隔的文件，该文件代表具有新上载的分类数据的数据集。如果导入操作创建了任何唯一的 ID，或者发生了任何错误，则 Adobe 会自动为您生成此文件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 通过浏览器导入分类 {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

<!-- 

t_upload_a_saint_data_file_via_web_browser.xml

 -->

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**.
1. Configure the **[!UICONTROL Browser Import]** fields.
1. Click **[!UICONTROL Import File]**.
1. 查看状态窗口以了解处理消息。
1. (Conditional) If you selected **[!UICONTROL Automatically Download Classification File After Upload is Complete]**, specify where you want to store the resulting file when processing completes.
>成功的导入操作会立即在导出操作中显示相应的更改。但是，使用浏览器导入时，报表中的数据更改至多需要 4 个小时完成，而使用 FTP 导入时，则需要长达 24 小时才能完成。

