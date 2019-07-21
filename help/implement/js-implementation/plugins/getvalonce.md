---
description: getValOnce 插件可防止指定变量被设置为之前定义的值。它使用 Cookie 来确定变量最近一次显示的值。如果当前值匹配 Cookie 值，则变量会被一个空白字符串覆盖，然后发送到 Adobe 处理服务器。此插件可有效防止在用户刷新页面或单击返回按钮时造成转化变量实例虚增。
keywords: Analytics 实施
seo-description: getValOnce 插件可防止指定变量被设置为之前定义的值。它使用 Cookie 来确定变量最近一次显示的值。如果当前值匹配 Cookie 值，则变量会被一个空白字符串覆盖，然后发送到 Adobe 处理服务器。此插件可有效防止在用户刷新页面或单击返回按钮时造成转化变量实例虚增。
seo-title: getValOnce
solution: Analytics
subtopic: 插件
title: getValOnce
topic: 开发人员和实施
uuid: 82fe0da5-3bc4-4632-8c62-7b5683f6b587
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getValOnce

getValOnce 插件可防止指定变量被设置为之前定义的值。它使用 Cookie 来确定变量最近一次显示的值。如果当前值匹配 Cookie 值，则变量会被一个空白字符串覆盖，然后发送到 Adobe 处理服务器。此插件可有效防止在用户刷新页面或单击返回按钮时造成转化变量实例虚增。

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).

**参数**

```js
s.eVar1=s.getValOnce(variable,cookie,expiration,minute);
```

* **变量 (Variable)：**&#x200B;将被检查的变量。通常与目前定义的变量相同。
* **Cookie：**&#x200B;存储了要进行对比的前一个值的 Cookie 名称。此 Cookie 可为任意值。
* （可选）**过期时间 (Expiration)：** Cookie 将在此天数后过期。如果未设置或设置为 0，则默认过期时间为浏览器会话。
* （可选）**分钟 (Minute)：**&#x200B;如果您将其设置为字符串值&#x200B;*`m`*&#x200B;过期值在几分钟内而不是数天内定义。If not set, *`days`* is the default expiration.

**属性**

* 此插件通常用于转化变量。但是，它也可用于任意 [!DNL Analytics] 变量。
* 如果 Javascript 遇到此函数，它会将定义的值与 Cookie 中存储的值进行比较。如果定义的值与 Cookie 值不同，则设置定义的值。如果定义的值与 Cookie 值相同，则返回空字符串。
* Cookie 只能存储一个值，这意味着此插件只会查对最后一个定义的值。
* 此插件不会令所有值停止定义已定义过的变量。此插件只阻止对最后一个值进行连续多次设置。
* 如果最终用户阻止或拒绝 Cookie，则始终返回原始值。
* 此插件的会话不同于由 [!DNL Analytics] 定义的会话（或访问）。[!DNL Analytics] 会在会话处于活动状态 12 小时或非活动状态 30 分钟后终止该会话。而此插件由于使用浏览器的会话定义，因此只有在用户关闭页面或退出浏览器后，它才会被终止。

   * 如果某用户关闭您的页面，在 30 分钟内又打开另一个浏览页面，并导航回到您的网站，则此插件在保持 [!DNL Analytics] 访问保持打开状态的同时，会创建一个新的会话。
   * 如果用户使浏览器窗口保持打开状态，并且超过 30 分钟没有单击链接，则 [!DNL Analytics] 访问过期，但同时浏览器会话会保持打开状态。

>[!NOTE]
>
>以下说明要求您更改站点上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 [!DNL Analytics] 经验的开发人员完成。

## 实施 {#section_177FF7F425B64FFB83CDE15A6ACC8D21}

>[!NOTE]
>
>If your organization uses Marketing Channels and has rules set up based on `s.campaign`, it is recommended that you not use the getValOnce plugin when setting the `s.campaign`value. 因为这样做可能会导致为次级促销活动点进分配错误的渠道。

要实施此插件，请在 [!DNL s_code.js] 文件中置入以下代码

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getValOnce_v1.11 
 */ 
s.getValOnce=new Function("v","c","e","t","" 
+"var s=this,a=new Date,v=v?v:'',c=c?c:'s_gvo',e=e?e:0,i=t=='m'?6000" 
+"0:86400000,k=s.c_r(c);if(v){a.setTime(a.getTime()+e*i);s.c_w(c,v,e" 
+"==0?0:a);}return v==k?'':v");
```

Once the above code is implemented, define the desired variable using the *`getValOnce`* function. 以下是几个有关如何进行实施的示例。

**如果在 Cookie 设置后的 30 天内检测到重复的值，则阻止定义相同的促销活动值：**`s.campaign=s.getValOnce(s.campaign,'s_cmp',30);`**如果在设置了cookie的30分钟内检测到重复的值，则防止定义相同的eVar值：**`s.eVar1=s.getValOnce(s.eVar1,'s_ev1',30,'m');`**防止在同一浏览器会话中多次定义同一eVar值：**`s.eVar2=s.getValOnce(s.eVar2,'s_ev2');`**Notes**

* 在生产环境中进行部署之前，请务必对插件安装进行广泛地测试，以确保可按预期进行数据收集。
* 请确保删除 Cookie 或在测试过程中使用新的唯一值，否则将不会发送变量。

