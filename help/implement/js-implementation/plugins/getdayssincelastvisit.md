---
description: 确定用户自最近一次访问您的网站后经过的天数，并在 Analytics 变量中捕获此信息。
keywords: Analytics 实施
seo-description: 确定用户自最近一次访问您的网站后经过的天数，并在 Analytics 变量中捕获此信息。
seo-title: getDaysSinceLastVisit
solution: Analytics
subtopic: 插件
title: getDaysSinceLastVisit
topic: 开发人员和实施
uuid: design95882-3bd0-4f94-a0 c3-4e7 b6058 d246
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getDaysSinceLastVisit

确定用户自最近一次访问您的网站后经过的天数，并在 Analytics 变量中捕获此信息。

>[!IMPORTANT]
>
>[Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) 现在包括 **[!UICONTROL 自上次访问]** 维度起的天数，因此可消除对此插件的需求。

此回访频度数据可用于解答以下问题：

* 用户再次访问我的网站的频率是多久？
* 回访频度与转化有何关联？重复购买者是否经常访问？
* 点击我的促销活动的用户之后是否经常回访？

插件还可以生成用于划分区段的值。例如，您可以创建一个区段，仅查看 30 天或更久未访问的客户的所有访问数据。

>[!NOTE]
>
>以下说明要求您更改站点上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 [!DNL Analytics] 经验的开发人员完成。

## 插件代码和实施 {#section_5600DBB819F143D59527A73BD94418DE}

**配置区域**

无需更改。

**插件配置**

Place the following code within the `s_doPlugins()` function, which is located in the area of the [!DNL s_code.js] file labeled *Plugin Config*. 选取一个自定义流量 (s.prop) 变量和/或一个自定义转化 (s.eVar) 变量，以便用于捕获回访频度数据。它应该是一个已经通过“管理控制台”启用的变量，且当前未做其他任何使用。下面给出了一个示例，您可以根据需要进行相应的更新。

```js
s.prop1=s.getDaysSinceLastVisit(Cookie_Name);
```

**插件区域**&#x200B;将以下代码添加到 [!DNL s_code.js] 文件中标记为 *PLUGINS SECTION*（插件区域）的部分。请勿对此部分的插件代码进行任何更改。

```js
/* 
 * Plugin: Days since last Visit 1.1 - capture time from last visit 
 */ 
s.getDaysSinceLastVisit=new Function("c","" 
+"var s=this,e=new Date(),es=new Date(),cval,cval_s,cval_ss,ct=e.getT" 
+"ime(),day=24*60*60*1000,f1,f2,f3,f4,f5;e.setTime(ct+3*365*day);es.s" 
+"etTime(ct+30*60*1000);f0='Cookies Not Supported';f1='First Visit';f" 
+"2='More than 30 days';f3='More than 7 days';f4='Less than 7 days';f" 
+"5='Less than 1 day';cval=s.c_r(c);if(cval.length==0){s.c_w(c,ct,e);" 
+"s.c_w(c+'_s',f1,es);}else{var d=ct-cval;if(d>30*60*1000){if(d>30*da" 
+"y){s.c_w(c,ct,e);s.c_w(c+'_s',f2,es);}else if(d<30*day+1 && d>7*day" 
+"){s.c_w(c,ct,e);s.c_w(c+'_s',f3,es);}else if(d<7*day+1 && d>day){s." 
+"c_w(c,ct,e);s.c_w(c+'_s',f4,es);}else if(d<day+1){s.c_w(c,ct,e);s.c" 
+"_w(c+'_s',f5,es);}}else{s.c_w(c,ct,e);cval_ss=s.c_r(c+'_s');s.c_w(c" 
+"+'_s',cval_ss,es);}}cval_s=s.c_r(c+'_s');if(cval_s.length==0) retur" 
+"n f0;else if(cval_s!=f1&&cval_s!=f2&&cval_s!=f3&&cval_s!=f4&&cval_s" 
+"!=f5) return '';else return cval_s;");
```

**注意**

* 在生产环境中进行部署之前，请务必对插件安装进行广泛地测试，以确保可按预期进行数据收集。
* 此插件根据回访频度将用户分类为以下群组：

   * 首次访问
   * 不到 1 天
   * 少于 7 天
   * 多于 7 天
   * 多于 30 天

* 此插件依赖 Cookie 来标记用户之前是否进行过访问。如果浏览器不接受 Cookie，则此插件将返回值“*Cookies Not Supported*”（Cookie 不受支持）。

