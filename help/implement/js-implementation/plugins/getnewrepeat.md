---
description: 确定访客是新访客还是回访者，并在 Analytics 变量中捕获此信息。
keywords: Analytics 实施
seo-description: 确定访客是新访客还是回访者，并在 Analytics 变量中捕获此信息。
seo-title: getNewRepeat
solution: Analytics
subtopic: 插件
title: getNewRepeat
topic: 开发人员和实施
uuid: e3e9f362-e0 b1-4a2 b-bb5 b-98eddaa0 a7 f4
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getNewRepeat

确定访客是新访客还是回访者，并在 Analytics 变量中捕获此信息。

使用此插件可解答以下问题：

* 我的访客中新访客（相对于回访者）所占的百分比是多少？
* 回访者产生的人均转化率是否比新访客高？该比率是多少？
* 我的促销活动是否有助于持续保持访问量？例如，点击我的促销活动的用户是否在以后又进行了回访？

>[!NOTE]
>
>以下说明要求您更改站点上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 [!DNL Analytics] 经验的开发人员完成。

## 插件代码和实施 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**配置区域**：无需对此区域进行任何更改。

**插件配置**

将以下代码置于 *`s_doPlugins()`* 函数，它位于标签为 *`s_code.js`**Plugin Config*&#x200B;的文件区域。选取一个自定义流量 (s.prop) 变量或一个自定义转化 (s.eVar) 变量，以便用于捕获保留值数据。这应该是一个已经通过“管理控制台”启用的变量，且当前未做其他任何使用。您可以使用以下示例并根据需要对它进行更新。

`s.prop1=s.getNewRepeat(30,'s_getNewRepeat');`

*`s.getNewRepeat`*&#x200B;具有两个可选参数：

1. 第一个可选参数是 Cookie 应保存的天数。如果忽略此参数，则默认值为 30 天。
1. 第二个可选参数是 Cookie 名称。如果忽略此参数，则使用默认值。

**插件区域**：添加以下代码到 [!DNL s_code.js] 文件中标记为“PLUGINS SECTION”的区域。请勿对此部分的插件代码进行任何更改。

```js
/* 
 * Plugin: getNewRepeat 1.2 - Returns whether user is new or repeat 
 */ 
s.getNewRepeat=new Function("d","cn","" 
+"var s=this,e=new Date(),cval,sval,ct=e.getTime();d=d?d:30;cn=cn?cn:" 
+"'s_nr';e.setTime(ct+d*24*60*60*1000);cval=s.c_r(cn);if(cval.length=" 
+"=0){s.c_w(cn,ct+'-New',e);return'New';}sval=s.split(cval,'-');if(ct" 
+"-sval[0]<30*60*1000&&sval[1]=='New'){s.c_w(cn,ct+'-New',e);return'N" 
+"ew';}else{s.c_w(cn,ct+'-Repeat',e);return'Repeat';}"); 
/* 
* Utility Function: split v1.5 (JS 1.0 compatible) 
*/ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a");
```

在生产环境中进行部署之前，请务必对插件安装进行广泛地测试，以确保可按预期进行数据收集。
