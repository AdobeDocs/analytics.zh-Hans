---
description: 部署 Analytics 时，动态标签管理中用于自定义页面代码的字段描述。
keywords: Dynamic Tag Management;customize page code;open editor;execute
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 自定义页面代码
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# 自定义页面代码

部署 Analytics 时，动态标签管理中用于自定义页面代码的字段描述。

**[!UICONTROL *`Property`*]**> **[!UICONCONTROL![](assets/settings_gear.png)

编辑工具]** > **[!UICONTROL 自定义页面代码]**

<table id="table_A4676A5FEE814DF9A05DA0E56F8B4C6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>打开编辑器 </p> </td> 
   <td colname="col2"> <p>您可以插入必须在最终 <code> s.t()</code> 调用（包含在 <code> s_code</code> 中）之前触发的任何 JavaScript 调用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>执行 </p> </td> 
   <td colname="col2"> <p> <b>在 UI 设置之前</b>：界面设置具有高于自定义代码的优先权（例如，当您要覆盖某个 eVar 且启用了界面中的某个设置时）。 </p> <p> <b>在 UI 设置之后</b>：自定义代码具有高于界面设置的优先权。 </p> </td> 
  </tr> 
 </tbody> 
</table>

