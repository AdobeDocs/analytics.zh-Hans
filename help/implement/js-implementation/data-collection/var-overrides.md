---
description: 通过变量覆盖，您可以更改单个跟踪的变量值或跟踪链接调用。
keywords: Analytics 实施
seo-description: 通过变量覆盖，您可以更改单个跟踪的变量值或跟踪链接调用。
seo-title: 变量覆盖
solution: Analytics
subtopic: 变量
title: 变量覆盖
topic: 开发人员和实施
uuid: 3ec09ae8-b9df-426f-8065-42b4518e6c5f
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 变量覆盖

通过变量覆盖，您可以更改单个跟踪的变量值或跟踪链接调用。

要覆盖变量，请创建一个新对象，指定变量值，然后将此对象作为第一个参数传递给 `s.t()`，或者作为第四个参数传递给 `s.tl()`：

```js
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
  
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
  
s.t(overrides);  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

```js
s.linkTrackVars="eVar1,eVar2,eVar3,events"; 
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
 
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
 
s.tl(this,'e','AnotherSite',overrides,'navigate')  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

