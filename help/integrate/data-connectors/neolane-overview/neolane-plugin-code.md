---
description: 如果选择了JavaScript插件数据收集方法，请复制以下代码行并将其添加到页面上的Adobe Analytics代码中。
seo-description: 如果选择了JavaScript插件数据收集方法，请复制以下代码行并将其添加到页面上的Adobe Analytics代码中。
seo-title: Adobe Analytics插件代码
title: Adobe Analytics插件代码
uuid: b10345ba-1e80-4e5c-af87-6e6 a9 dc87 c00
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Adobe Analytics Plug-In Code{#adobe-analytics-plug-in-code}

如果选择了JavaScript插件数据收集方法，请复制以下代码行并将其添加到页面上的Adobe Analytics代码中。

`/*`

`* Plugin: getQueryParam 2.3`

`*/ s.getQueryParam=new Function("p","d","u","" +"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" +"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" +".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" +"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" +"=p.length?i:i+1)}return v"); s.p_gpv=new Function("k","u","" +"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" +"=s.pt(q,'&','p_gvf',k)}return v"); s.p_gvf=new Function("t","k","" +"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" +"rue':t.substring(i+1);if(p.toLowerCase()==k. oLowerCase())return s." +"epa(v)}return ''");`

`/*in the s_doPlugins function`

`s.campaign=s.getQueryParam("ET_CID"); //places query param value from cid in campaign variable s.eVar2=s.getQueryParam("ET_RID"); //places query param value from rid in eVar2 variable`

>[!NOTE]
>
>以上插件假定某些自定义商务变量(eVar)可用。如果上述插件中指定的变量在您的Adobe Analytics部署中不可用，只需将它们替换为可用的变量。

