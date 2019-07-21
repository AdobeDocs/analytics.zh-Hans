---
description: getAndPersistValue 插件可获取您选择的值，并在确定的时间段内用该值填充某个 Analytics 变量。通常用于了解一个促销活动在点进之后共产生多少次页面查看，这样能让您很容易知道每个促销活动中最常被查看的页面。
keywords: Analytics 实施
seo-description: getAndPersistValue 插件可获取您选择的值，并在确定的时间段内用该值填充某个 Analytics 变量。通常用于了解一个促销活动在点进之后共产生多少次页面查看，这样能让您很容易知道每个促销活动中最常被查看的页面。
seo-title: getAndPersistValue
solution: Analytics
subtopic: 插件
title: getAndPersistValue
topic: 开发人员和实施
uuid: ddeab80c-260e-44b6-8483-8b8b369ec19b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getAndPersistValue

getAndPersistValue 插件可获取您选择的值，并在确定的时间段内用该值填充某个 Analytics 变量。通常用于了解一个促销活动在点进之后共产生多少次页面查看，这样能让您很容易知道每个促销活动中最常被查看的页面。

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).

For example, you might use this plug-in to set a campaign tracking code from the *`campaign`* variable into a Custom Traffic ( *`s.prop`*) variable on each visitor's page view made for the next 30 days. 通过该示例可以确定最初的点进导致跟踪代码产生了多少次页面查看。

>[!NOTE]
>
>以下说明要求您更改站点上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 [!DNL Analytics] 经验的开发人员完成。

## 插件代码和实施 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**配置区域**：无需对此区域进行任何更改。

**插件配置**

将以下代码置于 *`s_doPlugins()`* 函数，它位于标签为 *`s_code.js`**Plugin Config*&#x200B;的文件区域。选取一个自定义流量 (s.prop) 变量或一个自定义转化 (s.eVar) 变量，以便用于捕获保留值数据。这应该是一个已经通过“管理控制台”启用的变量，且当前未做其他任何使用。您可以使用以下示例并根据需要对它进行更新。

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`*&#x200B;具有三个参数：

1. Currently populated variable or value to persist ( *`s.campaign`* shown above).
1. Cookie name, used to store the value ( *`s_getval`* shown above).
1. 保留周期，以天为单位。如上所示，设为“30”会使得在接下来 30 天内，用户每次进行页面查看时该值都会被填充到所选变量。如果忽略，则默认设置为 *session*。

**插件区域**：添加以下代码到 [!DNL s_code.js] 文件中标记为“PLUGINS SECTION”的区域。请勿对此部分的插件代码进行任何更改。

```js
/* 
 * Plugin: getAndPersistValue 0.3 - get a value on every page 
 */ 
s.getAndPersistValue=new Function("v","c","e","" 
+"var s=this,a=new Date;e=e?e:0;a.setTime(a.getTime()+e*86400000);if(" 
+"v)s.c_w(c,v,e?a:0);return s.c_r(c);");
```

在生产环境中进行部署之前，请务必对插件安装进行广泛地测试，以确保可按预期进行数据收集。
