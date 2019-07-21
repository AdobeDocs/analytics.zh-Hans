---
description: getVisitNum 插件可以确定用户访问网站的次数，并在 Analytics 变量中捕获这一数量。
keywords: Analytics 实施
seo-description: getVisitNum 插件可以确定用户访问网站的次数，并在 Analytics 变量中捕获这一数量。
seo-title: getVisitNum
solution: Analytics
subtopic: 插件
title: getVisitNum
topic: 开发人员和实施
uuid: 27d57f92-fffb-44d0-b9 ca-9da93323 f64 c
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getVisitNum

getVisitNum 插件可以确定用户访问网站的次数，并在 Analytics 变量中捕获这一数量。

## 插件代码和实施 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**配置区域**：无需对此区域进行任何更改。

**插件配置**

将以下代码置于 *`s_doPlugins()`* 函数，它位于标签为 *`s_code.js`**Plugin Config*&#x200B;的文件区域。选择一个自定义流量 (s.prop) 变量或一个自定义转化 (s.eVar) 变量，以便用于捕获访问数量数据。这应该是一个已经通过“管理控制台”启用的变量，且当前未做其他任何使用。您可以使用以下示例并根据需要对它进行更新。

`s.prop1=s.getVisitNum();`

>[!NOTE]
>
>以下说明要求您更改站点上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 [!DNL Analytics] 经验的开发人员完成。

**插件区域**：添加以下代码到 [!DNL s_code.js] 文件中标记为“PLUGINS SECTION”的区域。请勿对此部分的插件代码进行任何更改。

```js
/* 
* Plugin: getVisitNum - version 3.0 
*/ 
s.getVisitNum=new Function("tp","c","c2","" 
+"var s=this,e=new Date,cval,cvisit,ct=e.getTime(),d;if(!tp){tp='m';}" 
+"if(tp=='m'||tp=='w'||tp=='d'){eo=s.endof(tp),y=eo.getTime();e.setTi" 
+"me(y);}else {d=tp*86400000;e.setTime(ct+d);}if(!c){c='s_vnum';}if(!" 
+"c2){c2='s_invisit';}cval=s.c_r(c);if(cval){var i=cval.indexOf('&vn=" 
+"'),str=cval.substring(i+4,cval.length),k;}cvisit=s.c_r(c2);if(cvisi" 
+"t){if(str){e.setTime(ct+1800000);s.c_w(c2,'true',e);return str;}els" 
+"e {return 'unknown visit number';}}else {if(str){str++;k=cval.substri" 
+"ng(0,i);e.setTime(k);s.c_w(c,k+'&vn='+str,e);e.setTime(ct+1800000);" 
+"s.c_w(c2,'true',e);return str;}else {s.c_w(c,e.getTime()+'&vn=1',e)" 
+";e.setTime(ct+1800000);s.c_w(c2,'true',e);return 1;}}"); 
s.dimo=new Function("m","y","" 
+"var d=new Date(y,m+1,0);return d.getDate();"); 
s.endof=new Function("x","" 
+"var t=new Date;t.setHours(0);t.setMinutes(0);t.setSeconds(0);if(x==" 
+"'m'){d=s.dimo(t.getMonth(),t.getFullYear())-t.getDate()+1;}else if(" 
+"x=='w'){d=7-t.getDay();}else {d=1;}t.setDate(t.getDate()+d);return " 
+"t;");
```

**参数**

* tp =（字符串，可选）跟踪时段。使用“d”表示天，“w”表示周，“m”表示月，或使用某个数字表示自定义天数。

   * 如果选择天、周或月，则将在天/周/月结束时重置访问量。
   * 如果选择自定义天数，则将在该天数后重置访问量。
   * 如果未提供任何值，则将使用“m”。

* c =（字符串，可选）指定永久性 Cookie 名称。默认值为“s_vnum”。
* c2 =（字符串，可选）指定会话 Cookie 名称。默认值为“s_invisit”。

**返回结果**

* 返回访问的访问量（1、2、3 等）。该数字仅在每次访问第一个页面时递增。
* 如果插件无法识别访问量（Cookie 被阻止），则返回“未知访问量”。

**示例**

```js
s.prop1=s.getVisitNum(365); //custom length, 365 days. Default cookie names 
s.prop1=s.getVisitNum('w'); //resets weekly 
s.prop1=s.getVisitNum('m','s_vmonthnum','s_monthinvisit'); //resets montly, custom cookie names 
s.prop1=s.getVisitNum('d'); //resets daily
```

**注意**

* 在生产环境中进行部署之前，请务必对插件安装进行广泛地测试，以确保可按预期进行数据收集。
* 要使用此插件，需要在用户的网页浏览器中设置 Cookie。如果用户不接受 Cookie，则所有访问次数将显示为首次访问次数。

