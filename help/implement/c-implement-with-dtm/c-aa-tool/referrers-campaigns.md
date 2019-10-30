---
description: 在 Adobe Analytics 中部署动态标签管理时，动态标签管理中用于反向链接和促销活动选项的字段描述。
keywords: Dynamic Tag Management;反向链接;促销活动;反向链接覆盖;促销活动变量;查询参数
seo-description: 在 Adobe Analytics 中部署动态标签管理时，动态标签管理中用于反向链接和促销活动选项的字段描述。
seo-title: 反向链接和促销活动
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: 反向链接和促销活动
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 反向链接和促销活动

在 Adobe [!DNL Analytics] 中部署 [!UICONTROL Dynamic Tag Management] 时，[!UICONTROL Dynamic Tag Management] 中用于反向链接和促销活动选项的字段描述。

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) **[!UICONTROL 编辑工具]** &gt; **[!UICONTROL 反向链接和促销活动]**

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
   <td colname="col2"> <p>覆盖 <span class="varname">s.referrer</span> 变量中设置的值，它通常由浏览器中设置的反向链接填充。 </p> <p>请参阅<a href="/help/implement/js-implementation/c-variables/page-variables.md">页面变量</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 促销活动 </td> 
   <td colname="col2"> <p>一种变量，可识别将访客吸引到您网站的市场营销活动。促销活动的值通常取自查询字符串参数。 </p> <p>See [<a href="/help/implement/js-implementation/c-variables/page-variables.md">Page Variables</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

使用 DTM 界面选择您要使用查询字符串，还是要使用值（可从数据元素中提取）：

![](assets/dtm-queryparam.png)

您可以在界面中直接输入查询字符串，或者如果您通过其他方式跟踪促销活动，则可以引用单独的数据元素。
