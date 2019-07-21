---
description: 使用 APL（或 appendList）插件，您可以为任意分隔值列表附加更多的值，同时还可选择是否执行区分大小写（或不区分大小写）检查以确保附加的值不会已存在于列表中。此 APL 插件由多个标准插件引用，但在多种情况下也可直接使用。
keywords: Analytics 实施
seo-description: 使用 APL（或 appendList）插件，您可以为任意分隔值列表附加更多的值，同时还可选择是否执行区分大小写（或不区分大小写）检查以确保附加的值不会已存在于列表中。此 APL 插件由多个标准插件引用，但在多种情况下也可直接使用。
seo-title: appendList
solution: Analytics
subtopic: 插件
title: appendList
topic: 开发人员和实施
uuid: e923c86c-ea6-4e17 a3 a4-0e08 af886674
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# appendList

使用 APL（或 appendList）插件，您可以为任意分隔值列表附加更多的值，同时还可选择是否执行区分大小写（或不区分大小写）检查以确保附加的值不会已存在于列表中。此 APL 插件由多个标准插件引用，但在多种情况下也可直接使用。

此插件可用于：

* 添加事件到当前事件变量
* 添加值到列表变量，且不重复列表中的值
* 基于某些页面逻辑添加产品到当前产品变量
* 添加值到参数&#x200B;*`linkTrackVars`* 并且 *`linkTrackEvents`*

**使用案例 1**

<table id="table_5AAC1D9892CD4E5C9060E119EE4E7DC8"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>方案 </p> </td> 
   <td colname="col2"> <p>添加<span class="term"> event1 </span> ，并确保活动不重复。 </p> <p>s.events="scCheckout" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代码 </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>结果 </p> </td> 
   <td colname="col2"> <p>s.events="scCheckout,event1" </p> </td> 
  </tr> 
 </tbody> 
</table>

**使用案例 2**

<table id="table_C4356C9AB95948F3929A7B75E07AE9E7"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>方案 </p> </td> 
   <td colname="col2"> <p>添加<span class="term"> 历史记录 </span> 到列表变量 <span class="varname"> prop1 </span>， <span class="term"> 历史记录 </span> 和 <span class="term"> 历史记录 </span> 被视为相同的值。 </p> <p>s.prop1="Science,History" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>代码 </p> </td> 
   <td colname="col2"> <p>s.prop1=s.apl(s.prop1,"history",",",2) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>结果 </p> </td> 
   <td colname="col2"> <p>s.prop1="Science,History" </p> <p> <span class="term"> 历史记录 </span> 不会添加，因为 <span class="term"> 历史记录 </span> 已在列表中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>以下说明要求您更改站点上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 [!DNL Analytics] 经验的开发人员完成。

## 实施 {#section_F4C91CA2037F478C9F7B53F357E6A5F0}

按照以下步骤实施 APL 插件。

1. 向客户关怀部门或当前指定的 Adobe 顾问请求插件代码。
1. Add call(s) to the API function as needed within the *`s_doPlugins`* function

此代码在您网站上大致如下所示：

```js
/* Plugin Config */ 
 
s.usePlugins=true 
 
function s_doPlugins(s) { 
 
/* Add calls to plugins here */ 
 
s.events=s.apl(s.events,"event1",",",1) 
 
} 
 
s.doPlugins=s_doPlugins
```

**支持的浏览器**

此插件要求浏览器支持 JavaScript 1.0 版本。

**插件信息**

<table id="table_7B9EDD616C164D6B8B53558337DF12C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 插件信息 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>参数 </p> </td> 
   <td colname="col2"> <p>apl((L,v,d,u) </p> <p>L = 源列表，可接受空列表 </p> <p> v = 附加的值 </p> <p> d = 列表分隔符 </p> <p> u（可选，默认为 0）唯一值检查。0 = 不进行唯一值检查，始终附加该值。1 = 执行不区分大小写检查，仅当列表中没有该值时才附加。2 = 执行区分大小写检查，仅当列表中没有该值时才附加。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>返回值 </p> </td> 
   <td colname="col2"> <p>原始列表，并包含附加的值（如果已添加） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用示例 </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1); </p> </td> 
  </tr> 
 </tbody> 
</table>

此源列表 L 可以为空，例如 *`L=""`*。返回的值将为空列表或只含一个值的列表。

**插件代码**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin Utility: apl v1.1 
 */ 
s.apl=new Function("l","v","d","u","" 
+"var s=this,m=0;if(!l)l='';if(u){var i,n,a=s.split(l,d);for(i=0;i<a." 
+"length;i++){n=a[i];m=m||(u==1?(n==v):(n.toLowerCase()==v.toLowerCas" 
+"e()));}}if(!m)l=l?l+d+v:v;return l"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
  
 Not Applicable - Utility function only 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 s.split
```

