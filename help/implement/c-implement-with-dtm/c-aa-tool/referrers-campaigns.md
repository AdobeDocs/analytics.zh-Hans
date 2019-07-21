---
description: 在 Adobe Analytics 中部署动态标签管理时，动态标签管理中用于反向链接和促销活动选项的字段描述。
keywords: 动态标签管理；引介；营销活动；referrer override；campaign variable；query param
seo-description: 在 Adobe Analytics 中部署动态标签管理时，动态标签管理中用于反向链接和促销活动选项的字段描述。
seo-title: 引介和营销活动
solution: Marketing Cloud、Analytics、动态标签管理
title: 引介和营销活动
uuid: 56580206-a382-4993-9bba-a488 da65 cf89
translation-type: tm+mt
source-git-commit: e271cf73e7fd31d8893ed57112f2f3bb7821fbdd

---


# 引介和营销活动

Field descriptions in [!UICONTROL Dynamic Tag Management] for referrers and campaign options when deploying [!UICONTROL Dynamic Tag Management] in Adobe [!DNL Analytics].

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png)**[!UICONTROL 编辑工具]** &gt; **[!UICONTROL 引介和营销活动]**

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
   <td colname="col2"> <p>覆盖<span class="varname"> s. referrer</span> 变量，通常由浏览器中的引介设置填充。 </p> <p>请参阅[页面变量](/help/implementation/js-implementation/c-variables/page-variables. md)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 促销活动 </td> 
   <td colname="col2"> <p>一种变量，可识别将访客吸引到您网站的市场营销活动。促销活动的值通常取自查询字符串参数。 </p> <p>请参阅[页面变量](/help/implementation/js-implementation/c-variables/page-variables. md)。 </p> </td> 
  </tr> 
 </tbody> 
</table>

使用 DTM 界面选择您要使用查询字符串，还是要使用值（可从数据元素中提取）：

![](assets/dtm-queryparam.png)

您可以在界面中直接输入查询字符串，或者如果您通过其他方式跟踪促销活动，则可以引用单独的数据元素。
