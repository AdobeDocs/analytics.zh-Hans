---
description: 在 Adobe Analytics 中部署动态标签管理时，动态标签管理中用于反向链接和促销活动选项的字段描述。
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics
title: 反向链接和促销活动
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 100%

---


# 反向链接和促销活动

在 Adobe [!DNL Analytics] 中部署 [!UICONTROL Dynamic Tag Management] 时，[!UICONTROL Dynamic Tag Management] 中用于反向链接和促销活动选项的字段描述。

**[!UICONTROL *`Property`*]**> ![齿轮图标](assets/settings_gear.png)**[!UICONTROL &#x200B;编辑工具&#x200B;]**>**[!UICONTROL &#x200B;反向链接和促销活动&#x200B;]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 元素 </th>
   <th colname="col2" class="entry"> 描述 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 反向链接覆盖 </td>
   <td colname="col2"> <p>覆盖 <span class="varname">s.referrer</span> 变量中设置的值，它通常由浏览器中设置的反向链接填充。 </p> <p>请参阅 <a href="../../../vars/page-vars/referrer.md">referrer</a>。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 促销活动 </td>
   <td colname="col2"> <p>一种变量，可识别将访客吸引到您网站的市场营销活动。促销活动的值通常取自查询字符串参数。 </p> <p>请参阅 <a href="../../../vars/page-vars/campaign.md">campaign</a>。 </p> </td>
  </tr>
 </tbody>
</table>

使用 DTM 界面选择您要使用查询字符串，还是要使用值（可从数据元素中提取）：

![查询参数](assets/dtm-queryparam.png)

您可以在界面中直接输入查询字符串，或者如果您通过其他方式跟踪促销活动，则可以引用单独的数据元素。
