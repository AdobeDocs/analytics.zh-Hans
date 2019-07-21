---
description: 记录您的页面在浏览器中处于活动选项卡状态的秒数，并将该值传递到下一页面查看的量度中。
keywords: Analytics 实施
seo-description: 记录您的页面在浏览器中处于活动选项卡状态的秒数，并将该值传递到下一页面查看的量度中。
seo-title: getPageVisibility
solution: Analytics
title: getPageVisibility
topic: 开发人员和实施
uuid: 3891e2aa-d5 c1-4a2 b-8522-eb2 Bae39 ea2 e
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getPageVisibility

记录您的页面在浏览器中处于活动选项卡状态的秒数，并将该值传递到下一页面查看的量度中。

>[!NOTE]
>
>这是插件的测试版，可能会即将更新其他更新。

This plug-in requires [getVisitStart](../../../implement/js-implementation/plugins/getvisitstart.md#concept_1C3CD25A87094A498A1D8A455963FBD8).

此插件还可记录页面在浏览器内停留的总秒数（包括主动和被动查看时间）。它要求使用 getPreviousValue 插件以便跟踪与页面可见性事件关联的上一页面名称。跟踪这些值可帮助您更好地了解访客参与程度，并更精确地跟踪访客在网站上的行为。

它要求使用 getPreviousValue 插件以便跟踪与页面可见性事件关联的上一页面名称。跟踪这些值可帮助您更好地了解访客参与程度，并更精确地跟踪访客在网站上的行为。

>[!NOTE]
>
>以下说明要求您更改站点上的数据收集代码。此操作会影响您网站上的数据收集，且只应由具有使用和实施 Analytics 经验的开发人员完成。This plug-in is compatible only with [!DNL AppMeasurement] tracking libraries.

## 所需的支持插件 {#section_0CA7624F4A7B4B5F851A4300937887AD}

* appendList
* getPreviousValue
* getVisitStart

## 插件代码和实施 {#section_543ABD8B3E6A48A5AFD86CFEDE144696}

**配置区域**

`s.pvel` 变量应包含您希望使用的三个事件：

| 事件 | 定义 |
|---|---|
| 页面可见性总秒数（数值） | 页面在浏览器内处于活动状态的时间 |
| 页面总秒数（数值） | 页面在浏览器中加载的时间，不考虑它的可见性状态 |
| 页面可见性实例总数（计数器） | 针对前两个事件记录值的总次数 |

**示例调用**

```
//Page Visibility Event List (total page visibility seconds, total page seconds, total page visibility instances) 
s.pvel='event7,event8,event9' 
```

**doPlugins 区域**

要初始化此插件，则需要在 s_code 的 `doPlugins` 区域中加入两行代码，最好是在已指定 `s.pageName` 变量之后。

**示例调用**

```
/* Page Visibility */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.getPageVisibility(); 
```

**插件区域**

```
/* Page Visibility Plugin 0.1 (BETA) */ 
s.getPageVisibility=new Function("","" 
+"var s=this;if(s.getVisitStart()){s.Util.cookieWrite('s_pvs','');s.U" 
+"til.cookieWrite('s_tps','');}if(s.Util.cookieRead('s_pvs')&&s.pvt<1" 
+"){if(parseInt(s.Util.cookieRead('s_pvs'))<=parseInt(s.Util.cookieRe" 
+"ad('s_tps'))){s.pve=s.pvel.split(',');s.events=s.apl(s.events,s.pve" 
+"[0]+'='+(parseInt(s.Util.cookieRead('s_pvs'))),',',2);s.Util.cookie" 
+"Write('s_pvs','');s.events=s.apl(s.events,s.pve[1]+'='+(parseInt(s." 
+"Util.cookieRead('s_tps'))),',',2);s.Util.cookieWrite('s_tps','');s." 
+"events=s.apl(s.events,s.pve[2],',',2);}}s.pvi=setInterval(s.pvx,100" 
+"0);s.wpvi=setInterval(s.wpvc,5000);"); 
s.gbp=new Function("","" 
+"if('hidden'in document){return null;}var bp=['moz','ms','o','webkit" 
+"'];for(var i=0;i<bp.length;i++){var p=bp[i]+'Hidden';if(p in docume" 
+"nt){return bp[i];}}return null;"); 
s.hp=new Function("p","" 
+"if(p){return p+'Hidden';}else{return'hidden';}"); 
s.vs=new Function("p","" 
+"if(p){return p+'VisibilityState';}else{return'visibilityState';}"); 
s.ve=new Function("p","" 
+"if(p){return p+'visibilitychange';}else{return'visibilitychange';}"); 
s.pvx=new Function("","" 
+"s.pvt+=1;"); 
s.wpvc = function(){var tempDate = Date.now();s.Util.cookieWrite('s_tps', 
Math.ceil((tempDate - s.totalTime)/1000));s.Util.cookieWrite('s_pvs', s.pvt)} 
document.addEventListener('visibilitychange',function(event){if(document.hidden){s.visibility = false;clearTimeout(s.pvi);}else{s.visibility=true;s.pvi=setInterval(s.pvx,1000);}});s.totalTime=new Date();s.pvt=0;s.prefix=s.gbp;s.hidden=s.hp(s.prefix);s.visibility=true;s.visibilityState=s.vs(s.prefix);s.visibilityEvent=s.ve(s.prefix); 
```

## 注释 {#section_47964BB9D0A24BFEB4B2498A41D8B017}

* 在生产环境中进行部署之前，请务必对插件安装进行测试，以确保可按预期进行数据收集。
* 由于与上一页面关联的插件传递页面可见性秒数和总秒数，因而不会收集与访问的最终页面查看有关的数据。
* 要使用此插件，需要在用户的网页浏览器中设置 Cookie。如果用户不接受第一方 Cookie，则此插件不会将数据传递到 Analytics。
* The plug-in creates its own first-party cookies named `s_tps` and `s_pvs`.

* 只有很少一部分用户会因为浏览器限制而无法传递页面查看数据的百分比，而且逻辑包含于插件中以确保数据的准确性不会因此而受到影响。不过，此插件已在 IE、Firefox、Chrome 和 Safari 中测试成功。
* 依据插件测量总秒数并将该值与上一页面名称关联的方式，在页面量度和总秒数量度上逗留的默认时间之间存在差别。
* [!UICONTROL 可创建计算指标] 以帮助汇总和了解与这些指标关联的访客行为：

   * **页面可见性比率**(页面可见性秒/总页面秒数)
   * **隐藏隐藏秒**(页面总秒数-页面可见性秒)
   * **平均页面可见性秒**(页面可见性秒/总页面可见性实例)
   * **平均页面隐藏秒数**（（页面总秒数 - 页面可见性总秒数）/ 页面可见性实例总数）

* 依据插件舍入秒数的方式，在页面可见性总秒数和总秒数之间可能存在 1 到 2 秒的差别，其中总秒数会高一些。（将在未来的更新中解决）
* 使用 getVisitStart 插件时应当考虑到访客在处于非活动状态 30 分钟以上之后开始新访问的情况。这并非正常情况，不过，当我们在未来新版本的插件中加入“总活动秒数”时，可能会提供相应的解决方法。

## 常见问题 {#section_1ED9391D3BAA4208817F0DF69ABBB25E}

**此增效工具是否会进行额外的服务器调用？**

此插件只记录后续页面查看服务器调用中的页面可见性值。没有任何其他的服务器调用与它一起使用。

**如果我不想捕获总页面数或总页面可见性实例，是否可以将这些实例保留在活动列表中？**

是的，页面总秒数和可见性实例总数是可选事件，因此可在必要时将它们排除在列表之外。

**如果我将这些活动用于除“上一页名称”以外的报告，是否会有任何意义？**

由于插件记录后续图像请求中的值，因此只有已在“上一页面”上下文中捕获的其他 eVar 才适用，例如“上一页面 URL”。

**插件将发送 s.tl() 调用中的可见性时间，还是只发送 s.t() 调用中的可见性时间？**

可见性时间只通过 s.t() 调用记录。
