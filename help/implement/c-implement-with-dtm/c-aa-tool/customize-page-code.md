---
description: 部署 Analytics 时，动态标签管理中用于自定义页面代码的字段描述。
keywords: Dynamic Tag Management;自定义页面代码;打开编辑器;执行
seo-description: 部署 Analytics 时，动态标签管理中用于自定义页面代码的字段描述。
seo-title: 自定义页面代码
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 自定义页面代码
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 自定义页面代码

部署 Analytics 时，动态标签管理中用于自定义页面代码的字段描述。

添加插件以确保该代码与 Analytics 工具同时运行。有关 Analytics 插件的更多信息，请参阅 [实施插件](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**[!UICONTROL *`Property`*]** &gt; **[!UICONTROL   ![](assets/settings_gear.png)

编辑工具]** &gt; **[!UICONTROL 自定义页面代码]**

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
   <td colname="col2"> <p>您可以插入必须在最终 <code>s.t()</code> 调用（包含在 <code>s_code</code> 中）之前触发的任何 JavaScript 调用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>执行 </p> </td> 
   <td colname="col2"> <p> <b>在 UI 设置之前</b>：界面设置具有高于自定义代码的优先权（例如，当您要覆盖某个 eVar 且启用了界面中的某个设置时）。 </p> <p> <b>在 UI 设置之后</b>：自定义代码具有高于界面设置的优先权。 </p> </td> 
  </tr> 
 </tbody> 
</table>

