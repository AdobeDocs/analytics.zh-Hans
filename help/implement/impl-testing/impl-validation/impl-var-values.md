---
description: 确保通过服务器脚本或代码填充的变量不能输出任何影响值的引号。
keywords: Analytics 实施
seo-description: 确保通过服务器脚本或代码填充的变量不能输出任何影响值的引号。
seo-title: 变量和值
solution: Analytics
title: 变量和值
topic: 开发人员和实施
uuid: ff4857a-9451-4794-9146-f417 ab1 d1 ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 变量和值

确保通过服务器脚本或代码填充的变量不能输出任何影响值的引号。

例如：

```js
s.pageName="Article: "Article Name"" 
s.pageName='Company's Information' 
```

确保变量的值不超过本文档中指定的最大限制。额外的字符会在数据收集服务器中被裁剪掉。它们可能会干扰总长度，增加不必要的带宽消耗，还可能导致其他问题。

请不要在产品变量中使用 $、™、®、© 或逗号 (,)。一般来说，它们在 [!DNL Analytics] 变量中不但没有用处，而且可能还会干扰解译或导出字段的功能。最好是将字符限制在头 127 个 ASCII 字符内。

Ensure that the events variable is populated with an appropriate value ( [!UICONTROL prodView], [!UICONTROL purchase], [!UICONTROL scAdd], [!UICONTROL scRemove], [!UICONTROL scOpen], or event1-event5) whenever *`products`* is populated. 请确保所有 [!DNL Analytics] 变量和函数的大小写保持不变，如下所示。

```js
s.pageName 
s.server 
s.channel 
s.pageType 
s.prop1 - s.prop20 
s.campaign 
s.state 
s.zip 
s.events 
s.products 
s.purchaseID 
s.eVar1 - s.eVar20 
var s_code=s.t();if(s_code)document.write(s_code)//--> 
```

页面名称须区分大小写，若有不同会创建其他页面记录。“Home”和“home”是 [!DNL Analytics] 内两个不同的页面。

>[!NOTE]
>
>多个页面记录无法合并到报告中。

验证链接是否在[!UICONTROL 自定义链接]报表中报告。确保正确的参数传递到 [!UICONTROL tl] 函数。有关[!UICONTROL 自定义链接]的详细信息，请参阅 [链接跟踪](../../../implement/js-implementation/function-tl.md#concept_EA13689CB8EE4F308FC89A1293046D5E).
